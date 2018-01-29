## Week One - Module 2 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON!). 

Note: When you're done, submit a PR. 

### Week 1 Questions

1. List the five common HTTP verbs and what the purpose is of each verb.
* GET = Used to retrieve information from the server of the given URI
* POST = Used to send data to the server
* PUT = Used to update all parts of data on the server
* PATCH = Used to update a single part of data on the server
* DELETE = Used to delete data on the server
2. What is Sinatra?
* Sinatra is a lightweight web application and DSL (Domain Specific Language) used to create sites and web apps.
4. What is MVC?
* MVC stands for model view controller.
5. Why do we follow conventions when creating our actions/path names in our Sinatra routes?
6. What types of variables are accessible in our view templates without explicitly passing them?
* Instance variables
7. Given the following block of code, how would I pass an instance variable `count` with a value of `1` to my `index.erb` template?
  
  ```ruby
  get '/horses' do
    @count = 1
    erb :index :locals => {:name => 'Mr.Ed' }
  end
  ```

8. In the same code block, how would I pass a local variable `name` with a value of `Mr. Ed` to the view?
9. What's the purpose of ERB?
* ERB allows us to utilize ruby syntax for logic and performing calculations that would not normally be available within an HTML file.
10. Why do I need a development AND test database?
* Besides the fact that testing on a development database could take a while, having a test database ensures that our development database is clean and no problems or duplication will arise from the modifications our tests might run.
11. What is CRUD and why is it important?
* Create, Read, Update, Destroy
12. What does HTTP stand for? 
* HyperText Transfer Protocol
13. What are the two ways to interpolate Ruby in an ERB view template? What's the difference between these two ways?
* For dealing with ruby logic  : <% %>
* If you wanted to print the info: <%= %>
14. What's an ORM?
* Object Relational Mapping. It's a software or technique that allows you to query and manipulate data from a database as objects for a more OOP paradigm.
15. What's the most commonly used ORM in ruby (Sinatra & Rails)?
* ActiveRecord
16. Let's say we have an application with restaurants. There are seven verb + path combinations necessary to provide full CRUD functionality for our restaurant application. List each of the seven combinations, and explain what each is for.
* get + '/items'
* get + '/items/new'
* get + '/items/:id
* get + '/items/:id/edit'
* post + '/items'
* delete + '/items/:id'
* put + '/items/:id'
17. What's a migration? 
* An easy way to alter the database schema over time.
18. When you create a migration, does it automatically modify your database?
* Not unless you run rake db:migrate. 
19. How does a model relate to a database?
* They are the empty class used to create objects fromt the rows of the database. Each column will be an attribute for the object.
20. What is the difference between `#new` and `#create`?
* Create is #new and #save at the same time, while #new can be an instaniated object that could be empty or other attributes without being saved.

### Review Questions:  
21. Given a CSV file (“films.csv”) with these headers [id, title, description], how would you load these into your database to create new instances of Film?
```ruby
films = CSV.open 'films.csv', headers: true, header_converters: :symbol
films.each do |row|
  Film.create(id: row[id],
              title: row[title],
              description: row[description])
end
```
22. Given the following hash:
```
activities = {
  hiking: {cost: $0, supplies: ['hiking shoes', 'water', 'compass']},
  karaoke: {cost: $10, supplies: ['courage', 'microphone'],
  brunch: {cost: $35, supplies: ['mimosa flutes'],
  antiquing: {cost: $200, supplies: ['list of antique stores'] 
}}}}
```
How would I add 'granola bar' to things you should have when hiking?
```ruby
activities[:hiking][:supplies] << 'granola bar'
```
23. What are the 4 Principles of OOP? Give a one sentence explanation of each.
* Inheritance - The ability of passing behavior an existing class to another class.
* Polymorphism - Allowing the object or methods within an object to take on many different roles and responsibilities
* Encapsulation - Binding variables and methods in classes to achieve data integrity and ease of maintenance.
* Abstraction - It is the process of only showing essential data or necessary features of an object to the outside world.

### Self Assessment:
Choose One:
* I was able to answer a few questions independently, but relied heavily on outside resources

Choose One:
* I feel overwhelmed by the content presented this week
