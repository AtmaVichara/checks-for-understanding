## Week Two - Module 2 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON - YOU are a web developer!!!). 

Note: When you're done, submit a PR.

1. At a high level, what is ActiveRecord? What does it do/allow you to do?
* ActiveRecord allows you to manipulate your database and the tables associated with it through ruby, instead of using SQL language. It also allows you to define relationships and create migrations.
2. Assume you have the following model:

```ruby
class Team << ActiveRecord::Base
end
```

What are some methods you can call on `Team`? If these methods aren't defined in the class, how do you have access to them?
* You could use #all to show all the teams within a database.
* #find
* #select
* #order
* #group
* If the methods aren't defined in the class you access them through ActiveRecords built in methods. These are inherited from ActiveRecord::Base.
3. Assume that in your database, a team has the following attributes: "id", "name", owner_id". How would you find the name of a team with an id of 4? Assuming your class only included the code from question 2, how could you find the owner of the same team?
* Team.find(4).name to find the name of the team.
```ruby 
team = Team.find(4)
owner = Owner.find(team.owner_id)
```

4. Assume that you added a line to your `Team` class as follows:

```ruby
class Team << ActiveRecord::Base
  belongs_to :owner
end
```

Now how would you find the owner of the team with an id of 4?

```ruby
team = Team.find(4)
team.owner.name
```

5. In a database that's holding students and teachers, what will be the relationship between students and teachers? Draw the schema diagram.

6. Define foreign key, primary key, and schema.
* A forein key is a key to link two tables together. This is usually an id of some sort.
* A primary key is the unique identifier of a record in a database
* The schema is a visual repsentation of a db tables structure. Their name and data type.
7. Describe the relationship between a foreign key on one table and a primary key on another table.
* A forein key is the unique identifier of another tables record that could be in a separate table to link them, while the primary key is the unique identifier for said tables record.
8. What are the parts of an HTTP response?
* The first part is the status line with the status code and uri
* The second part is the header. This usually has the date, server, last modified date, content_type, and content_length.
* The third part is an empty line
* The fourth part is the body


### Optional Questions

1. Name your five favorite ActiveRecord methods (i.e. methods your models inherit from ActiveRecord) and describe what they do.
2. Name your three favorite ActiveRecord rake tasks and describe what they do.
3. What two columns does `t.timestamps null: false` create in our database?
* created_at
* updated_at
4. In a database that's holding schools and teachers, what will be the relationship between schools and teachers?
* A teacher belongs_to a school and a school has_many teachers
5. In the same database, what will you need to do to create this relationship (draw a schema diagram)?
 Teacher  | School
| ------- | ----- |
| name    | name  |
| id      | id    |
| school_id |       |
6. Give an example of when you might want to store information besides ids on a join table.
7. Describe and diagram the relationship between patients and doctors.
8. Describe and diagram the relationship between museums and original_paintings.
9. What could you see in your code that would make you think you might want to create a partial?
