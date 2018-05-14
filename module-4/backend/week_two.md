## Week Two - Module 4 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week. 

Note: When you're done, submit a PR. 

1. What's one difference between ES5 and ES6?
There are a few new things introduced in ES6.
* ES6 introduced the arrow function syntax to reduce the amount of text needed to create functions
```javascript
// ES5
function greating (name) {
  return 'hello' + name
}

// ES6
const greetings = (name) => {
  return `hello ${name}`;
}

const greedting = (name) => `hello ${name}`;
```

* ES6 introduced promises and then
```javascript
fetch('/api/v1/people')
  .then((people) => people.json())
  .then((peopleJson) => doSomething(peopleJson))
  .catch((error) => console.error({error}))
```

* ES6 also introduced some changes for populating objects and arrays with spread
```javascript
const obj1 = { a: 1, b: 2 }
const obj2 = { a: 2, c: 3, d: 4}
const obj3 = {...obj1, ...obj2}

const arr1 = [1, 2, 3, 4, 5]
const arr2 = [...arr1]
```
* ES6 also gave us classes and constructors for the classes
```javascript
class Person {
  constructor(age, name, height) {
    this.age = age
    this.name = name
    this.height = height
  }
}
```

2. What's the difference between asynchronous and synchronous JavaScript? 
* Asynchonous Javascript is when certain functions or statements are run outside of the normal code flow. In other words, if there is a call to an api, and there is another simple console.log proceeding it, then before the call is completed, Javascript will run the console.log.
* Synchronous Javascript is the opposite of asynchronous. The functions and statements will follow in order of the normal code flow. Taking the asynchronous example, if the code were synchronous, the api call would have to resolve first, before the console.log would be able to run.
3. What are the four pillars of Object Oriented programming?
* Polymorphism, Encapsulation, Inheritance, Abstraction
4. What are some tools available in JavaScript to help you write object oriented code?
* In ES6 we have classes with constructors that help us instantiate new objects with behavior and state (constructor, properties, and methods)
* Along with the classes we can also allow for them to inherit from other classes using the extends syntax.
```javascript
class Mammal {
  ...
}

class Human extends Mammal {
  ...
}
```
5. What are some key concepts to be aware of when refactoring your JavaScript?
* When there is something within a callback or promise that seems rather verbose, that you can take out and place into another function, then it would be best to extract the code.
6. What's a callback function and what are some reasons when we use/need callback functions?
* A callback function is a function passed as an argument to another function, which is then invoked inside the outer function to perform an action. 
* A great example of callbacks is with api calls. When an api call is made, there is a callback function made as well that will perform its duty if the api call is taking a while. If the api call was loading, and there was no callback function then the page would seem to freeze, but with a callback function you could add in a simple loading icon that plays.
7. What are the different scopes of variables in Javascript? When would you want to define global variables?
* Local Scope = variables defined wihin a function
* Global Scope = variables assigned outside of multiple functions that rely on it.
8. What's the difference between `==` and `===` in JavaScript?
* The strict comparison (===) is only true if the operands are the same type and content, while the abstract comparison (==) will convert the operand data types to match each other before making the comparison.
9. Why do front end frameworks exist?
* Frontend frameworks exist for the same reason backend frameworks exist. They make the developers life easier by requiring dependencies that would otherwise have to be handrolled by the developer. Frontend frameworks also offer a convention for developing apps, as certain frameworks are more suited for quick and easy apps, while others are more suited for large scale apps.

#### Review  

10. Why do people say "HTTP is stateless"?
* HTTP is based upon the request/response cycle. All information within the request or response knows nothing of previous request/response cycle or the information within them. 
11. Describe a RESTful API.
* A RESTful API is an application program interface utilizing HTTP requests (GET, POST, PUT, PATCH, DELETE) to manipulate data on a server.
12. What are some main characteristics of a team following an agile workflow?
* Regular retrospectives on current goals. After determining what goals are to be met, plan out a schedule or sprint for said goals within a relatively short period of time 3-14 days. Constant testing during this period and code reviews are performed. After each test and review, determine better approaches for the feature and implement said features, till the end of the sprint. Once finished review all code, procedures, and plan accordingly for the next sprint.
13. What are some advantages **and** disadvantages to using OAuth to authenticate a user?
* Advantages:
  * OAuth is a simple way to authorize users by giving access tokens based upon the scopes of the request sent to the content providers server
  * Since OAuth2 data transfers must take place on SSL (Secure Sockets Layer) to ensure data is as safe as possible
  * OAuth is easy to implement for companies and easy to use for users
* Disadvantages:
  * It is sometimes easy to create dummy OAuth screens for phishing purposes.

