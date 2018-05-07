## Week One - Module 4 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week. 

Note: When you're done, submit a PR. 

1. What's the most useful thing you learned from completing the intermission week work?
* The most useful thing I learned over the intermission week was how to iterate over arrays and objects in javascript. I am still a little hazy on the whole copy vs reference thing, but in the end, the most important thing for me is iterating over collections of data. 
2. What are some tools to help debug JavaScript code?
* debugger
* console.log()
3. What are some tools you need in order to unit test your JavaScript?
* npm
* chai
* mocha
4. What is the syntax for invoking a function? Give an example.
```javascript
const multiplier = (a, b) => { 
  return a * b
}

multiplier(2, 4)
```
5. What's `this` in JavaScript?
* This can be different things depending on where it is called from
* Globally, if you call 'this', then it refers to the global object
* If 'this' is called from within a constructor, then 'this' refers to the object being constructed.
* Within funcitons, depending on what type of function it is, 'this' could refer to different things.
  * If a function is not written in strict mode, and 'this' is called within, then 'this' refers to the global object (window).
  * If a function is written in strict mode, then 'this' refers to whatever it was set to upon entering the execution of the function.
* If 'this' is called from within an object's function, then 'this' refers to the object the function is within.
6. What is Webpack and why is it useful?
* Webpack is a build tool that minifies assets (styling, javascript, etc) into one file for each type of asset for the asset pipeline.
7. When/why do you want to use event delegation?

8. What's `npm` and what do we use it for?
* npm is a package handler for Node.js
* We mainly use it to gather all our dependencies upon booting up our app. It allows us to not have to require each and every dependent library.

#### Review  
9. What's the MVC design pattern? Describe each part of MVC.
* Model = Ruby objects that are used in relation to a table within the database. Usually these are created / manipulated through and ORM.
10. What are a few ways to optimize a Rails application?
* Caching
* Background Workers
* ActiveRecord quering vs using Ruby methods on Models
11. What's a background worker? When would we want to use a background worker?
