Questions from Week 5:
1. How do we make flash messages display on a page?
```ruby
  <% flash.each do |type, message| %>
    <%= content_tag :div, message, class: type %>
  <% end %>
```
2. Where is cart information/temporary information usually stored?
* Cart information is stored in a session you create. Usually called session[:cart].

3. What might be some reasons not to store a cart in our database? Are there any reasons why we would want to persist that information?
* Storing cart in the database can become intensive and take up unessecary space. 

4. What is the purpose of the asset pipeline?
* The asset pipeline allows for our apps to run faster by compressing our asset files, while also processing languages such as erb, coffeescript, sass into html, javascript, and css for us.

5. Why do we precompile our assets?
* We precompile to minimize the files for the browser to run faster. 

6. What do each of the following tags do?

```ruby 
<%= stylesheet_link_tag "application" %>
<%= javascript_include_tag "application" %>
<%= image_tag "rails.png" %>
```

7. What are some of the elements of a great read me? What are some of the benefits of taking the time to update a readme for our project?
* A great introduction. What does the app or gem do? Who is it for?
* A great installation guide. Step by step process with visual examples.
* A demonstration of functionality. What can you do with it? What visual examples (code snippets) are provided?
* A great edgecase or misc section. If there is a problem or something that you must do to have the gem working in production and deployment, what necessary steps must be taken?
* Links to any relevant information. How do you contribute? How do you support the creators? Further documentation.
* Updating the readme can give other people a better understanding of what the app will do, and will keep people informed on any changes that might occur over the development lifecycle.

8. What are the top four accessibility issues that we as developers should be aware of?
* visual
* cognition
* mobility
* I don't know the other. Maybe if they are colorblind.
9. `before_save` is an example of a what? Where in our Rails application would we find a `before_save`?
* It is known as a call back and is found in our models.

10. Given the following object, how would we create a scope for all users who are active?

```ruby 
User.create(name: "Happy", active: true)
```

11. What is the difference between a scope and a class method?


Review Questions:  
12. Given the following hash:  

```ruby
{cart: {"17" => 4, "204" => 52, "29" => 22}}
```

  12a. How would you add item with id of 48 with a quantity of 4?  
  ```ruby
  session[:cart]['48'] = 4
  ```
  12b. How would you increase the quantity of item 29?  
  ```ruby
  sessiont[:cart]['29'] += 1
  ```
  12c. How would you find out how many items your user is thinking about purchasing?   
  ```ruby
  sessiont[:cart].values.sum
  ```
13. What is polymorphism? How does it relate to duck-typing? What are two ways you use this in everyday Rails applications?
* Polymorphism is the concept that a model or object can take on multiple functions in an application.
14. How would you clean the string "(630) 854-5483" to "630.854.5483"?  
* num.gsub(/[()]/, '').gsub('.', '')
