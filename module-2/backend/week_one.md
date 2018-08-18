## Week One - Module 2 Recap
GET: retrieve a resource from a url
POST: create a new resource
PUT: update an entire resource
PATCH: update part of a resource
DELETE: remove/destroy a resource

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON!).

Note: When you're done, submit a PR.

### Week 1 Questions

1. List the five common HTTP verbs and what the purpose is of each verb.
  a. GET: pull a resource from a web address
  b. POST: create a new resource
  c. PUT: update an entire resource
  d. PATCH: update a part of an a resource
  e. DELETE: remove a resource
  
2. What is Sinatra?
  It is a Ruby web framework that serves applications on the web and uses Rack to interact with the web. 

3. What is MVC?
  a. M = Model and represents the data logic. It interacts with the data base.
  b. V = View and represents the presentation logic. 
  c. C = Controller and represents the business logic. It coordinates the responses to http requests.

4. Why do we follow conventions when creating our actions/path names in our Sinatra routes?
  

5. What types of variables are accessible in our view templates without explicitly passing them?
  Instance variables.

6. Given the following block of code, how would I pass an instance variable `count` with a value of `1` to my `index.erb` template?

  ```ruby
  get '/horses' do
  @count = 1
    erb :index
  end
  ```

7. In the same code block, how would I pass a local variable `name` with a value of `Mr. Ed` to the view?
  A local variable in the controller wouldn't be accessable in the view. In order to pass it I would make it an instance         variable. @name = Mr. Ed
  
8. What's the purpose of ERB?
  ERB = embedded Ruby and it's used to describe how data should be used to create HTML.
  

9. Why do I need a development AND test database?
  

10. What is CRUD and why is it important?
  a. C = Create
  b. R = Read
  c. U = Update
  d. D = Destroy

11. What does HTTP stand for?
  Hypertext Transfer Protocol

12. What are the two ways to interpolate Ruby in an ERB view template? What's the difference between these two ways?
  a. <%= %> visualizes the return value of the enclosed code.
  b. <% %>  does not visualize the return value of the enclosed code.

13. What's an ORM? What does it do?
  OMR = Object Relational Map
  With an ORM framework object classes can be mapped to data tables and object instances can be mapped to rows of those tables   in a relational database allowing to relate different tables to each other.

14. What's the most commonly used ORM in ruby (Sinatra & Rails)?
  ActiveRecord

15. Let's say we have an application with restaurants. There are seven verb + path combinations necessary to provide full CRUD  functionality for our restaurant application. List each of the seven combinations, and explain what each is for.

16. What's a migration?
  Inserting data into the database (feeding the database)

17. When you create a migration, does it automatically modify your database?
  Yes. By using ActiveRecord a table gets created with the name and table elements that were entered in the migration file. 

18. How does a model relate to a database?
  The model interacts with the database. Through methods in the model we can organize and crunch the database data in order to   pass that data to the app the way we want it to be.

19. What is the difference between `#new` and `#create`?
  a. #new: creates a new onject instance, but doesn't save it.
  b. #create: creates and saves a new object instance into the db.

20. Given a table named `animals`, What is the SQL query that will return all info from that table?
    `id     name        number_of_legs
    -----   ------      --------------
      1     panda       4
      2     giraffe     4
      3     whale       0
      4     bird        2
      
    
  SELECT * FROM animals;

21. Using the same table, What is the SQL query that will return only the animals that has 4 legs?
  SELECT * FROM animals WHERE number_of_legs=4;


### Review Questions:  
22. Given a CSV file (“films.csv”) with these headers [id, title, description], how would you load these into your database to create new instances of Film?
 

23. Given the following hash:
```
activities = {
  hiking: {cost: $0, supplies: ['hiking shoes', 'water', 'compass']},
  karaoke: {cost: $10, supplies: ['courage', 'microphone']},
  brunch: {cost: $35, supplies: ['mimosa flutes']},
  antiquing: {cost: $200, supplies: ['list of antique stores']}
}
```
How would I add 'granola bar' to things you should have when hiking?

24. What are the 4 Principles of OOP? Give a one sentence explanation of each.
  a. Single Responsibility Principle (SRP): A method should be responsible for no more than completing one single thing.
  b. Abstraction: Elemination of the irrelevant and amplification of the essential.
  c. Don't Repeat Yourself (DRY): Avoiding being redundant and making use of inheritance instead.
  d. Encapsulation: Binding data variables and functions (methods) together in a class.



### Self Assessment:
Choose One: (erase the others)
* I was able to answer most questions independently, but utilized outside resources for a few

Choose One:
* I feel comfortable with the content presented this week
