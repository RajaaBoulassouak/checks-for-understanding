### Week 5 Questions

Re-pull from this repository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON!).

Note: When you're done, submit a PR.

### Week 5 Questions
1. How do we make flash messages display on a page?
   Setting up a method for flash messages in the html controller and adding the specific messages in the corresponding controller method

2. Where is cart information/temporary information usually stored?
   In a session.

3. What might be some reasons not to store a cart in our database? Are there any reasons why we would want to persist that information?
   Adding everything a visitor has in their cart, would overflow the db. When a customer ends up ordering something from the cart, the order could be added to the db.

4. What is the purpose of the asset pipeline?
   To concatenate assets.

5. Why do we precompile our assets?
   To reduces the number of requests a browser makes to render a web page, which can speed up loading the application.

6. What do each of the following tags do?

```ruby 
<%= stylesheet_link_tag "application" %>
<%= javascript_include_tag "application" %>
<%= image_tag "rails.png" %>
```
   They allow the asset pipeline to access the content that is passed in the tag.

7. What are some of the elements of a great read me? What are some of the benefits of taking the time to update a readme for our project?
    Elements:
    What the project is about (can be a summary with snippets or scrrenshots).
    Description of the work process of the project (from idea till completition).
    Link to the project.
    How to implement and use the project.
    Benefits:
    To inform people that will look at the project, which can help increasing their interest for the project, which can beneficial, e.g. a during job search process.
    To help driving a project, by using the readme as a guide through the project.
    To help managing the project expectations and having orientation when working in a team.
    

8. What are the top four accessibility issues that we as developers should be aware of?
    1. Navigation & Hyperlinks issues
    2. Site Structure issues
    3. Text issues
    4. Image/Multimedia issues
    5. Forms issues
    
9. `before_save` is an example of a what? Where in our Rails application would we find a `before_save`?
    It's an example of a Callback, it would be used in a specific controller for local use or in the application controller for global use through out all of the apps's controllers.

10. Given the following object, how would we create a scope for all users who are active?

```ruby 
User.create(name: "Happy", active: true)
```
class User < ActiveRecord::Base
  scope :active, -> { where(active: true) }
 end

11. What is the difference between a scope and a class method?
  I think there is no difference, it's just a matter of preference, but not sure.

### Review Questions:  
12. Given the following hash:  

```ruby
hash = {cart: {"17" => 4, "204" => 52, "29" => 22}}
```

  12a. How would you add item with id of 48 with a quantity of 4?  
       [:hash][:cart] << ["48"] = 4
       
  12b. How would you increase the quantity of item 29?  
       [:hash][:cart]["48"] = 29
       
  12c. How would you find out how many items your user is thinking about purchasing?
       By looking up the cart (cookie) that was stroed in from the session of that current_user.
  
13. What is polymorphism? How does it relate to duck-typing? What are two ways you use this in everyday Rails applications? 
      I'm not sure
      
14. How would you clean the string "(630) 854-5483" to "630.854.5483"?  
      I'm not sure


### Self Assessment:
Choose One:
* I was able to answer most questions independently, but utilized outside resources for a few

Choose One:
* I feel comfortable with the content presented this week
