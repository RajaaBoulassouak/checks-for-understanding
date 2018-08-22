## Week Two - Module 2 Recap

Fork or re-pull this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON - YOU are a web developer!!!). 

Note: When you're done, submit a PR.


### Week 2 Questions

1. At a high level, what is ActiveRecord? What does it do/allow you to do?
  It allows finding database records without to need to use raw SQL for that.
  
2. Assume you have the following model:

```ruby
class Team << ActiveRecord::Base
end
```

What are some methods you can call on `Team`? If these methods aren't defined in the class, how do you have access to them?

3. Assume that in your database, a team has the following attributes: "id", "name", owner_id". How would you find the name of a team with an id of 4? Assuming your class only included the code from question 2, how could you find the owner of the same team?
  Team.find(4)

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

  Relationship: could be many teachers to many students or one teacher to many students.
  In Teachers module: has_many :students
  In Students module: has_many :teachers or belongs_to :teacher
  
  Students_table
  id: 1 (primary_key)
  name: Heidi
  course: Maths 
  teacher_id: 2 (foreign_key)
  ...
  
  Teachers_table:
  id: 2 (primary_key)
  name: Mr. Teach
  course: Maths
  student_id: 1 (foreign_key)
  ...
  
  
6. Define foreign key, primary key, and schema.
  

7. Describe the relationship between a foreign key on one table and a primary key on another table.
  If the two same tables are related and only to each other, then the primary key on the one table is the same key as the       foreign key on the other table, which allows that way for the tables relationship.
  
8. What are the parts of an HTTP response?


### Optional Questions

1. Name your five favorite ActiveRecord methods (i.e. methods your models inherit from ActiveRecord) and describe what they do.
  a. .find(:id) -> finds an object by the specified primary key(:id). 
  b. .find_by(name: 'Heidi') -> finds the first record that is matching one or many conditions, here first with name Heidi.
  c. .where(name: 'Heidi') -> finds all records that are matching one or many conditions, here all with name Heidi .
  d. .first(5) -> reuturns the first records of a table, here first 5 records.
  e. .order(:amount) ->  orders a set of recods by the specified field in a table, here order by amount.
  
2. Name your three favorite ActiveRecord rake tasks and describe what they do.

3. What two columns does `t.timestamps null: false` create in our database?
  It adds the two columns 'created_at' and 'updated_at' to the table.
   
4. In a database that's holding schools and teachers, what will be the relationship between schools and teachers?
    Relationship: one school to many teachers. 
    In Teacher model -> belogns_to :school
    In School model -> has_many :teachers
    
5. In the same database, what will you need to do to create this relationship (draw a schema diagram)?
    

6. Give an example of when you might want to store information besides ids on a join table.

7. Describe and diagram the relationship between patients and doctors.
    Relationship: could be one doctor to many patiens or many doctors to many patients.
    In Patient model -> belongs_to :doctor or has_many :doctors
    In Doctor model -> has_many :patients 


8. Describe and diagram the relationship between museums and original_paintings.
   Relationship: One museum to many original_paintings
    In OriginalPainting model -> belongs_to :museum
    In Museum model -> has_many :original_paintings
    
9. What could you see in your code that would make you think you might want to create a partial?

### Self Assessment:
Choose One:
* I was able to answer most questions independently, but utilized outside resources for a few

Choose One:
* I feel comfortable with the content presented this week
