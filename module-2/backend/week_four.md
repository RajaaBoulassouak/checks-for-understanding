## Week Four Recap

### Instructions
Fork or re-pull this repository. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Week 4 Questions

1. What is a cookie?
   A cookie is used to store small amounts of data during a session, e.g. a unique session ID
 
2. What’s the difference between a session and a cookie?
   A session stores data on the server, a cookie stores data in the visitor's browser
 
3. What’s a flash and when do you want to use flashes?
   A flash is a part of a session. Values stored in a flah will be available only in the next request. A flash can e.g. be        used for passing a notice/message after a user logs in or logs out.
 
4. Why do people say “HTTP is stateless”?
   Because every request and response is independent. The connection between the browser and the server is lost once the          transaction ends
 
5. What’s authentication? Explain.
   Authentication is the process of verification that an individual, entity or website is who it claims to be.
 
6. What’s the difference between authentication and authorization?
   Authentication confirms the identity in order to access to the system. Authorization determines if a user is authorized to    access a specific resource.

7. What’s a before filter?
   It's a rails class method to use in controllers to execute a piece of code before executing any action in the controller.

8. How do we keep track of a user once they’ve logged in?
   Each session has a session id. With logging in the session id is set equal to the user id of the user that logged in. As      long as the user is staying logged in the session id is used to keep track of that user.

9. When do you want to namespace a resource? When do you want to nest a resource? What's the differences between those two approaches?
   I can organize controllers for different user groups in corresponding controller groups under a namespace. A namespace        allows me to change the prefix that's used as a path helper as well as the routes according to the different user groups. 
   I can use a nested resource when I have a resource that only matters with/within an other resource. Nested resources are      all resources. Namspace itself is not a resource.
   

10. At a high level, what tools can you use to implement authorization? How would you use them?
    I would determine the different levels of authorization users can have through different user roles. Through assigning a       specific user role to a user I can specify the level of authorization that user can have. With namespace I can also           differntiate the different views and controllers for the differnt authorization levels.

11. What's an enum, and what advantages does it offer? What data type needs to be in your database to use an enum? Where do       you declare an enum?
    It's a data type that enables for a variable to be a set of predefined values. The variable must be equal to one of the       values that have been predefined for it. The data type needs to an integer in the database. The enum is set on the model       level.

12. What are some strategies you can use to keep your views DRY?
    Put code that's rendered in all pages in the file application_html.erb.
    Use partials for repetitive code.


### Reviews Questions 
13. Given the following array of hashes, how would I print an alphabetical list of holidays?
```ruby
[
 {holiday: {name: "St Patrick's Day", supplies: ["Corned Beef and Cabbage"]}},
 {holiday: {name: "Halloween", supplies: ["Candy", "Costume"]}},
 {holiday: {name: "Hanukkah", supplies: ["Menorah"]}}
]
```  
  order('holidays.name')

14. How would you clean incoming data to ensure "$300" or "300.00" is stored as 300? 

set: price.to_i


### Self Assessment:
Choose One:
* I was able to answer most questions independently, but utilized outside resources for a few

Choose One:
* I feel comfortable with the content presented this week

