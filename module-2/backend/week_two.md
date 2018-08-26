## Week Two - Module 2 Recap

Fork or re-pull this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON - YOU are a web developer!!!). 

Note: When you're done, submit a PR.


### Week 2 Questions

1. At a high level, what is ActiveRecord? What does it do/allow you to do?
  It allows finding database records without to have to use raw SQL for that.
  
2. Assume you have the following model:

```ruby
class Team << ActiveRecord::Base
end
```

What are some methods you can call on `Team`? If these methods aren't defined in the class, how do you have access to them?
 sum
 average
 find
 find_by
 first
 last 
 ...
 
 ActiveRecord methods are accessable through the inheritance from ActiveRecord (< ActiveRecord::Base). I don't think they need   to be defined in class methods in order to be accessable, but not sure.

3. Assume that in your database, a team has the following attributes: "id", "name", owner_id". How would you find the name of a team with an id of 4? Assuming your class only included the code from question 2, how could you find the owner of the same team?
  a. team = Team.find(4)
      team.name
  
  b. team.owner_id
  
  I think I can only retrieve the 'owner_id' of 'team', not the whole information about the owner, because there is no             relationship set between team and owner.  

4. Assume that you added a line to your `Team` class as follows:

```ruby
class Team << ActiveRecord::Base
  belongs_to :owner
end
```

Now how would you find the owner of the team with an id of 4?
  team = Team.find(4)
  Owner.team.name

5. In a database that's holding students and teachers, what will be the relationship between students and teachers? Draw the schema diagram. 

  Relationship: could be  a) one teacher to many students
                                      or
                          b) many teachers to many students 
                        
  if a): In Teachers module: has_many :students
         In Students module: belongs_to :teacher
         
         Teachers_table:
          id: 2 (primary_key)
          name: Mr. Teach
          course: Maths
  
         Students_table
          id: 1 (primary_key)
          name: Heidi 
          teacher_id: 2 (foreign_key)
                             
    if b): In Teachers module: has_many :student_teachers
                               has_many :students through: :student_teachers
           In Students module: has_many :student_teachers
                               has_many :teachers through: :student_teachers
         
         Teachers_table:
          id: 1 (primary_key)
          name: Mr. Teach
          course: Maths
  
         Students_table
          id: 1 (primary_key)
          name: Heidi 
          
         StudentTeachers_join_table 
          id: 1 (primary_key)
          teacher_id: 1 (foreign_key)
          student_id: 1 (foreign_key)
  
6. Define foreign key, primary key, and schema.
  primary key: identifies an object in it's primary table. The table in which the object primary exists.
  foreign key: identifies an object in a related foreign table. Objects exists primary in an other table, but is reference       to through the foreign key in a different table.
  schema: displays the current structure of the database, it shows which tables are in the database and which columns each       table has.
  
7. Describe the relationship between a foreign key on one table and a primary key on another table.
  If the two same tables should be related, then the primary key on the one (primary) table is the same key as the foreign key   on the other (foreign) table representing the same object in the two tables.
  
8. What are the parts of an HTTP response?
  -Response header containing the Status Line
  -Response message body


### Optional Questions

1. Name your five favorite ActiveRecord methods (i.e. methods your models inherit from ActiveRecord) and describe what they do.
  a. .find(:id) -> finds an object by the specified primary key(:id). 
  b. .find_by(name: 'Heidi') -> finds the first record that is matching one or many conditions, here first with name Heidi.
  c. .where(name: 'Heidi') -> finds all records that are matching one or many conditions, here all with name Heidi .
  d. .first(5) -> reuturns the first records of a table, here first 5 records.
  e. .order(:amount) ->  orders a set of recods by the specified field in a table, here order by amount.
  
2. Name your three favorite ActiveRecord rake tasks and describe what they do.
  a. rake db:create -> creates the database.
  b. rake db:migrate -> create, update or delete a table in the database
  c. rake db:seed -> fills a table in the database with content

3. What two columns does `t.timestamps null: false` create in our database?
  It adds the two columns 'created_at' and 'updated_at' to the table.
   
4. In a database that's holding schools and teachers, what will be the relationship between schools and teachers?
    Relationship: one school to many teachers. 
    In Teacher model -> belogns_to :school
    In School model -> has_many :teachers
    
5. In the same database, what will you need to do to create this relationship (draw a schema diagram)?
   run a migration to create the two tables:
         Schools_table:
          id: 2 (primary_key)
          Title: Turing
     
         Teachers_table
          id: 1 (primary_key)
          name: Mr. Teach 
          school_id: 2 (foreign_key)
    

6. Give an example of when you might want to store information besides ids on a join table.
  If e.g. there is table of students that visit many courses and a table of courses that is hosting many students and the       students have a score on each course they visit, then I'll need a join table that's hosting also the score for each student   course combination
      

7. Describe and diagram the relationship between patients and doctors.
    Relationship: could be one doctor to many patiens or many doctors to many patients.
    My diagram would be as the one in question 5 of "week 2 questions".


8. Describe and diagram the relationship between museums and original_paintings.
   Relationship: One museum to many original_paintings
    In OriginalPainting model -> belongs_to :museum
    In Museum model -> has_many :original_paintings
    
    Museums_table:
     id: 2 (primary_key)
     name: Louvre

    original_paintings_table
     id: 1 (primary_key)
     name: Mona Lisa 
     museum_id: 2 (foreign_key)
    
9. What could you see in your code that would make you think you might want to create a partial?
    If see different view template codes that are basically the same.
   
### Self Assessment:
Choose One:
* I was able to answer most questions independently, but utilized outside resources for a few

Choose One:
* I feel comfortable with the content presented this week
