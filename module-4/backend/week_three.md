## Week Three - Module 4 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week. 

Note: When you're done, submit a PR. 

1. At a high level, what is Node?
* Node is an open source run time envoironment that allows for javascript to perform actions on the server. In other words it is a tool that allows for javascript to execute on the server-side.
2. What is Express? What is Express similar to in the Ruby world?
* Express is a Javascript framework that pairs with node.js allowing for easy route handling and views, while interacting with node.js' ability to interact with the server. Express is most like Sinatra in the Ruby world.
3. How do we setup a route when creating an API with Node and Express? Please provide a code snippet.
* To create an api route in Node & Express, you need to first create the route file for the specific endpoints.
```javascript
// foods.js
var express = require('express');
var router = express.Router();
var foodsController = require('../../../controllers/api/v1/foods-controller')
var Food = require('../../../models/food')

router.get('/', (req, res) => {
  foodsController.index(req, res)
})
```
* Afterwards you specify the root route in the app.js file.
```javascript
var express = require('express');
var app = express();

var foodsRouter = require('./routes/api/v1/foods'); // requiring the routes file and saving to a variable.

app.use('/api/v1/foods', foodsRouter); // specify the root route to be used, and the file where the routes are to be defined.
```
4. What do we use Knex for?
* Knex is a nice javascript ORM that provides us with the ability to make database base queries in javascript.
5. How **could** you organize your code to follow the MVC design pattern in your Quantified Self project?
* You could create a routes directory, controller directory that deals with much of the logic for the routes, and a model directory to make calls to the database for specific tables.
* controllers/
  * food-controller.js
* models
  food.js
* routes/
  * api/
    * v1/
      * foods.js
6. How do you execute raw SQL in node?
```javascript
const environment = process.env.NODE_ENV || 'development'
const configuration = require('../knexfile')[environment]
const database = require('knex')(configuration)

const grabAllFoods = () => {
  knex.raw(`SELECT * FROM foods`);
}
```
7. What are some advantages to having your front end and back end code live in separate applications? What are some disadvantages?


#### Review  

8. Describe DNS.
* The DNS (Domain Name System) is a way to link url addresses to specific ip addresses. Without the DNS all the urls we place in the browser would be the specific IP address. 
* The way it works is, when you type in google.com into the browser, your query is sent to a DNS recursive resolver. This recursive resolver than queries a DNS root nameserver, that then responds with a TLD (Top Level Domain) DNS server that houses the information needed. After recieving the TLD DNS, the resolver makes another request to the TLD which provides it with IP address for the url provided. Lastly the resolver reponds to the browser with the returned IP address and information (ie google.com's page).
9. What does writing clean code mean to you?
* Writing clean code to me follows a few different principles. Keep it DRY, reusable methods and classes, and SRP. Limiting the amount of conditionals is nice too. If it can follow those criteria, then it also needs the ability to be easily tested. 
10. If you were building an application that models hotels, what classes would you need? What classes would be responsible for what functionality? Hint: think about what tables you would need in the database, how those records would relate to each other, and good OOP.
* Hotel Class, has many floors, has many rooms through floors
* Room Class, belongs to floors, belongs to hotel
  * Would be responsible for housing guests (possibly boolean or ENUM for availability)
* Floor Class, belongs to hotel, has many rooms
