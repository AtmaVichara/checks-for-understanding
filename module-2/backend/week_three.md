## Week Three Recap

### Instructions
Fork this repository. Be sure to pull the latest changes to your local repo. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Questions

1. What is the entry at the command line to create a new rails app?
* rails new <app_name> 
2. What do Models generally inherit from in rails?
* ApplicationRecord
3. What do Controllers generally inherit from in a rails project?
* ApplicationController
4. How would I create a route if I wanted to see a specific horse in my routes file assuming I'm sticking to standard conventions and that I didn't want other CRUD functionality?
* resources :horses, only: [:show]
5. What rake task is useful when looking at routes, and what information does it give you?
* rails routes
* It gives the verb, path, action, and helper
6. What is an example of a route helper? When would you use them?
* ideas_path
* They come in handy for redirections
7. What's the difference between what `_url` and `_path` return when combined with a routes prefix?
* The `_path` will return just the path. Ex. photos_path = /photos
* The `_url` will return the path prefixed with the current host, port and path prefix
8. What are strong params and why are they necessary?
* Strong params are the parameters you have whitelisted for use, but the method itself is kept private to other users so you can protect the attributes from end-user assignment.
9. What role does `form_for` play in helping us create our forms?
* `form_for` allows us to designate what will either be edited or created by adding in the newly instantiated, but not saved, object.
10. How does `form_for` know where to submit the user's input?
* `form_for` knows where to submit based upon the action from the controller
11. Create a form using a `form_for` helper to create a new `Horse`. 
```ruby
form_for @horse do |f|
  f.label :name
  f.text_field :name
  f.submit
end
```
12. Why do we want to validate our models?
* We validate our models to ensure that we have all necessary attributes for later usage. 
