## Week Four Recap

### Instructions
Fork this repository. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Questions

1. What is a cookie?
* It is a piece of data sent from a server and stored on the clients broswer.
2. What’s the difference between a session and a cookie?
* A session is like a cookie in that it is data stored while a user is sending requests to the server, but unlike a cookie, a session is stored server side.
3. What’s a flash and when do you want to use flashes?
4. Why do people say “HTTP is stateless”?
* Even though multiple requests can be processed by a server, the responses have no knowledge of previous responses. They are their own.
5. What’s authentication? Explain.
* Authentication is the verification of a users credentials. This could be used for signing into accounts and verifying user information, which will open a session if the user is verified.
6. What’s the difference between authentication and authorization?
* While authentication primarily deals with verifying a user is who they say they are, authorization is the process of verifying if said user has certain access to site features, such as that which an admin might have. 
7. What’s a before filter?
* A before filter is a method that is run before a given action in a controller. It can be further specified which actions are using the filter.
8. How do we keep track of a user once they’ve logged in?
* We set up a new session with the key being user_id and the value being the user's id from the params
9. When do you want to namespace a resource? When do you want to nest a resource? What's the differences between those two approaches?
* We generally namespace a resource for authorization.
* We nest resources for communicating relationships, such as a users posts (users/:id/posts)
10. At a high level, what tools can you use to implement authorization? How would you use them?
* On a high level, you would use an encryptor for the password and verification fo the password. For rails this would be a simple gem. We also use sessions and verify the session.
11. What's an enum, and what advantages does it offer? What data type needs to be in your database to use an enum? Where do you declare an enum?
* An enum is an activerecord method that takes an attribute and allows it to be set to predefined constants. An integer has to be the datatype used for an enum in our database, because the integer will represent the index of the array of predefined constants. The enum is usually decalred in the model.
12. What are some strategies you can use to keep your views DRY?
* Implementing partials, helper methods, and instance methods to keep the logic to a minimum would help.


Reviews Questions 
13. Given the following array of hashes, how would I print an alphabetical list of holidays?
```ruby
[
 {holiday: {name: "St Patrick's Day", supplies: ["Corned Beef and Cabbage"]},
 {holiday: {name: "Halloween", supplies: ["Candy", "Costume"]},
 {holiday: {name: "Hanukkah", supplies: ["Menorah"]}
]
```  
```ruby
holidays = holidays.map.sort_by { |hol| hol[:holiday][:name].downcase }
holidays.each { |hol| p hol[:holiday][:name] }
```
14. How would you clean incoming data to ensure "$300" or "300.00" is stored as 300? 
```ruby
dollars.gsub('$', '').to_i
```
