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
  
  **A lightweight Rack-based, Ruby framework that allows to easily interact with the web. It has a Domain Specific Language     that facilitates this interaction.

3. What is MVC?
  a. M = Model and represents the data logic. It interacts with the data base.
  b. V = View and represents the presentation logic. What we display on the browser
  c. C = Controller and represents the business logic. It coordinates the responses to http requests.
         The middleman between what is displayed (views) and gathering the information from the database (models).
  

4. Why do we follow conventions when creating our actions/path names in our Sinatra routes?
  **Because REST is implemented across the web and provides a consistent and easy-to-follow interface for the client.

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
  
  **locals: { name = "Mr. Ed"}
  
8. What's the purpose of ERB?
  ERB = embedded Ruby and it's used to describe how data should be used to create HTML.
  
  **allows us to use ruby and html in the same file.
  

9. Why do I need a development AND test database?
  I would guess the development database is where the valuable data lives. In the testing process experimenting with data       should be possible without to worry about causing damage to the valuable data. I guess that's why testing and a development   are kept seperate from each other, by having a database for each one.
  
  **To keep responsibilities clear. Having a shared database would make brittle code that is harder to test.
  

10. What is CRUD and why is it important?
  a. C = Create
  b. R = Read
  c. U = Update
  d. D = Destroy
  **It is how we interact with a resource such as horses

11. What does HTTP stand for?
  Hypertext Transfer Protocol

12. What are the two ways to interpolate Ruby in an ERB view template? What's the difference between these two ways?
  a. <%= %> prints information within carrots
  b. <% %>  does not print information within carrots.

13. What's an ORM? What does it do?
  OMR = Object Relational Map
  With an ORM framework object classes can be mapped to data tables and object instances can be mapped to rows of those tables   in a relational database allowing to relate different tables to each other.
  
  **a way for us to create objects from rows of a database table for easy interaction.

14. What's the most commonly used ORM in ruby (Sinatra & Rails)?
  ActiveRecord

15. Let's say we have an application with restaurants. There are seven verb + path combinations necessary to provide full CRUD  functionality for our restaurant application. List each of the seven combinations, and explain what each is for.
  1. GET: '/restaurants' -> user can list all restaurants.
                            **See all restaurants
  2. GET: 'restaurants/new' -> user can create a new restaurant and should be able to submit it.
                            **See a form to create new restaurant
  3. POST: 'restaurants' -> user can save the new restaurant and should subsequently be redirected to the show page of the new      restaurant or to the updated index page with all restaurants listed including the new created one.
                            **Create new restaurant
  4. GET: 'restaurants/:id' -> user can call up/view a specific restaurant that is specified through the entered id.
                            **See restaurant with :id
  5. GET: 'restaurants/:id/edit' -> user can edit a specific restaurant that is specified through the entered id and should be      able to submit the changes.
                            **See a form to edit restaurant with :id
  6. PUT: 'restaurants/:id' -> user can update the specific restaurant, that is specified through the entered id and                subsequently be redirected to the show page of the updated restaurant or to the updated index page with all restaurants        listed including the updated one.
                            **Update restaurant with :id
  7. DELETE: 'restaurants/:id' -> user can delete a specific restaurant that is specified through the entered id and should be      redirected to the index page of the remaining restaurants, that don't include the deleted one anymore.
                            **Destroy restaurant with :id
  
  

16. What's a migration?
  Inserting data into the database (feeding the database).
  
  **Instructions for how to modify the database.

17. When you create a migration, does it automatically modify your database?
  Yes. By using ActiveRecord a table gets created with the name and table elements that were entered in the migration file. 
  
  **No, you still have to run rake db:migrate
  
18. How does a model relate to a database?
  The model interacts with the database. Through methods in the model we can organize and crunch the database data in order to   pass that data to the app the way we want it to be.
  
  **The model fetches (gets and returns) information from the database.

19. What is the difference between `#new` and `#create`?
  a. #new: creates a new onject instance, but doesn't save it unless .save is called
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
I would seed them by:
  1. creating a seed file
  2. adding this to the seed file: CSV.foreach('db/csv/film.csv', headers => true, header_converters: :symbol) do |row|
                                   film = Film.create(title: row[:title],
                                               description: row[:description])
  3. run 'rake db:seed'
                                          
 

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
 activities[:hiking][:supplies] << 'granola bar'

24. What are the 4 Principles of OOP? Give a one sentence explanation of each.
  a. Single Responsibility Principle (SRP): A method should be responsible for no more than completing one single thing.
  b. Abstraction: Elemination of the irrelevant and amplification of the essential.
  c. Don't Repeat Yourself (DRY): Avoiding being redundant and making use of inheritance instead.
  d. Encapsulation: Binding data variables and functions (methods) together in a class.
  
  **Encapsulation -- Only expose information and behavior that must be exposed to get your functionality
    Abstraction -- Creating objects with simple logical interfaces that represent your item
    Inheritance -- The ability to bring in methods from a single parent class
    Polymorphism -- Methods of the same name on different objects, creating the ability to build dynamically



### Self Assessment:
Choose One: (erase the others)
* I was able to answer most questions independently, but utilized outside resources for a few

Choose One:
* I feel comfortable with the content presented this week
