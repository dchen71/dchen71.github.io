---
layout: post
title: Devise Bootstrap Modal
---

Setup using Devise 3.5.1 and bootstrap 3.3.5. This is code snippet for setting up certain devise views in the bootstrap modals and responding to json. The controllers will have to be overridden to respond to json.

### Sign up

    <div class="modal fade" id="signup-modal" role="dialog">
      <div class="modal-dialog">
        <div class="modal-content">
          <div class="modal-header">
              <button type="button" class="close" data-dismiss="modal">&times;</button>
              <h2 class="text-center">Sign up</h2>
          </div>
          <div class="modal-body">
            <%= form_for(resource, as: resource_name, url: registration_path(resource_name),
                                   :html => {:id => "sign_up_user"},
                                   :format => :json,
                                   :remote => true ) do |f| %>
              <%= devise_error_messages! %>
            
              <div class="input-group">
                <span class="input-group-addon">
                  <span class="glyphicon glyphicon-envelope"></span>
                </span>
                <%= f.email_field :email, autofocus: true, required: true, class: "form-control", placeholder: "Email" %>
              </div>
            
              <br>

              <div class="input-group">
                <span class="input-group-addon">
                  <span class="glyphicon glyphicon-lock"></span>
                </span>
                <%= f.password_field :password, autocomplete: "off", required: true,minlength: 8, class: "form-control", placeholder: "Password(8 character minimum" %>
              </div>
            
              <br>

              <div class="input-group">
                <span class="input-group-addon">
                  <span class="glyphicon glyphicon-lock"></span>
                </span>
                <%= f.password_field :password_confirmation, autocomplete: "off", required: true, minlength: 8, class: "form-control", placeholder: "Repeat password" %>
              </div>
            
              <div class="actions">
                <br>
                <%= f.submit "Sign up", class: 'btn btn-success' %>
              </div>
            <% end %> 
          </div>
          <div class="modal-footer">
            <button type="submit" class="btn btn-danger pull-left" data-dismiss="modal"><span class="glyphicon glyphicon-remove"></span> Cancel</button>
            <div class="links pull-right">
              <button class="btn btn-info btn-small" data-toggle="modal" data-target="#login-modal" data-dismiss='modal'>Log in</button><br />
              <button class="btn btn-info btn-small" data-toggle="modal" data-target="#forgot-modal" data-dismiss='modal'>Forgot password?</button><br />
            </div>
          </div>
        </div>
      </div>
    </div>

![Signup bootstrap modal]({{ site.baseurl }}public/img/2015-11-14-signup.png)  

### Login

    <div class="modal fade" id="login-modal" role="dialog">
      <div class="modal-dialog">
        <div class="modal-content">
          <div class="modal-header">
            <button type="button" class="close" data-dismiss="modal">&times;</button>
            <h2 class="text-center">Log in</h2>
          </div>
          <div class="modal-body">
            <%= form_for(resource, as: resource_name, url: session_path(resource_name),
                                   :html => {:id => "log_in_user"},
                                   :format => :json,
                                   :remote => true ) do |f| %>
              <div class="input-group">
                <span class="input-group-addon">
                  <span class="glyphicon glyphicon-envelope"></span>
                </span>
                <%= f.email_field :email, autofocus: true, required: true, class: "form-control", placeholder:"Email" %>
              </div>
            
              <br>

              <div class="input-group">
                <span class="input-group-addon">
                  <span class="glyphicon glyphicon-lock"></span>
                </span>
                <%= f.password_field :password, autocomplete: "off", required: true, class: "form-control", placeholder: "Password" %>
              </div>
            
              <% if devise_mapping.rememberable? -%>
              <div class="checkbox col-md-12" style="padding-left:1.5em;">
                <%= f.check_box :remember_me %>
                <%= f.label :remember_me %>
              </div>
              <% end -%>
            
              <div class="actions">
                <br>
                <%= f.submit "Log in", class: 'btn btn-success', id: 'login_btn' %>
              </div>
            <% end %>
          </div>
          <div class="modal-footer">
            <button type="submit" class="btn btn-danger pull-left" data-dismiss="modal"><span class="glyphicon glyphicon-remove"></span> Cancel</button>
            <div class="links pull-right">
              <button class="btn btn-info btn-small" data-toggle="modal" data-target="#signup-modal" data-dismiss='modal'>Sign up</button><br />
              <button class="btn btn-info btn-small" data-toggle="modal" data-target="#forgot-modal" data-dismiss='modal'>Forgot password?</button><br />
            </div>
          </div>
          
        </div>
      </div>
    </div>

![Login bootstrap modal]({{ site.baseurl }}public/img/2015-11-14-login.png)  


### Forgot password

    <div class="modal fade" id="forgot-modal" role="dialog">
    	<div class="modal-dialog">
    		<div class="modal-content">
    			<div class="modal-header">
              		<button type="button" class="close" data-dismiss="modal">&times;</button>	
    				<h2>Forgot your password?</h2>	
    			</div>
    			<div class="modal-body">
            		<%= form_for(resource, as: resource_name, url: password_path(resource_name), 
            		                      			:html => {:id => "forgot_password_user"},
            		                           		:format => :json,
            		                           		:remote => true ) do |f| %>
            		  	<%= devise_error_messages! %>
            						
            			<div class="input-group">
            			  <span class="input-group-addon">
            			    <span class="glyphicon glyphicon-envelope"></span>
            			  </span>
            			  <%= f.email_field :email, autofocus: true, required:true, class: "form-control", placeholder:"Email" %>
            			</div>
            						
            		  <div class="actions">
            		    <br>
            		    <%= f.submit "Send me reset password instructions", class: 'btn btn-success' %>
            		  </div>
            		<% end %>	

    			</div>
    			<div class="modal-footer">
              		<button type="submit" class="btn btn-danger pull-left" data-dismiss="modal"><span class="glyphicon glyphicon-remove"></span> Cancel</button>
    				<div class="links pull-right">
              			<button class="btn btn-info btn-small" data-toggle="modal" data-target="#login-modal" data-dismiss='modal'>Log in</button><br />
              			<button class="btn btn-info btn-small" data-toggle="modal" data-target="#signup-modal" data-dismiss='modal'>Sign up</button><br />
    				</div>
    			</div>
    		</div>
    	</div>
    </div>

![Forgot password bootstrap modal]({{ site.baseurl }}public/img/2015-11-14-password.png)  
