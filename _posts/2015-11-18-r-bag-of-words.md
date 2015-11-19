---
layout: post
title: Bag of Words in R
tags: r, bag of words, machine learning
---

Bag of words is a technique used in working with language processing. Conceptually, it works by breaking down a sentence into an matrix of words to be able to use them as variables for machine learning models. The bag of words can further be broken down and refined to create greater variables. The *tm* is one such package that is capable of this. An example of how to use the package is in the following:

    library(tm)

    #Create a corpus from the description variable in train and test
    CorpusDescription = Corpus(VectorSource(c(train$description, test$description)))

    #Preprocessing of Corpus based on description
    ##Converts all text to lowercase
    CorpusDescription = tm_map(CorpusDescription, content_transformer(tolower), lazy=TRUE)
    ##Converts text to plain text with additional meta information
    CorpusDescription = tm_map(CorpusDescription, PlainTextDocument, lazy=TRUE)
    ##Remove any punctuation in the sentences
    CorpusDescription = tm_map(CorpusDescription, removePunctuation, lazy=TRUE) 
    ##Remove stop words(is, are, etc.) depending on language inputted(no Asian language support as far as I know)
    CorpusDescription = tm_map(CorpusDescription, removeWords, stopwords("english"), lazy=TRUE)
    ##Convert all applicable words to their stem form
    CorpusDescription = tm_map(CorpusDescription, stemDocument, lazy=TRUE)

    #Convert corpus to a DocumentTermMatrix, remove sparse terms, and turn it into a data frame. 
    ##Covert corpus to a document term matrix(matrix of terms)
    dtm = DocumentTermMatrix(CorpusDescription)
    ##Keep terms that appear 96% in the document
    sparse = removeSparseTerms(dtm, 0.96)
    DescriptionWords = as.data.frame(as.matrix(sparse))

    #Resplit entries back into training and test data sets
    DescriptionWordsTrain = head(DescriptionWords, nrow(train))
    DescriptionWordsTest = tail(DescriptionWords, nrow(test))


The end result of running that code will create a new data frame with new columns for each word stem per row. After processing, be sure to readd any necessary variables and continue to build your model. 