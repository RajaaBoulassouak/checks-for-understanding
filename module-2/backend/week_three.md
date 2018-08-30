## Week Three Recap

### Instructions
Fork this repository. Be sure to pull the latest changes to your local repo. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Week 3 Questions

1. What is the entry at the command line to create a new rails app?
   rails new new_project -T -d="postgresql" --skip-spring --skip-turbolinks
  
2. What do Models generally inherit from in rails?
   Models inherit from ApplicationRecord which inherits from ActiveRecord::Base
  
3. What do Controllers generally inherit from in a rails project?
   Controllers inherit from ApplicationController which inherits from ActionController::Base
  
4. How would I create a route if I wanted to see a specific horse in my routes file assuming I'm sticking to standard            conventions and that I didn't want other CRUD functionality?
   In the routes.rb file of the config folder I need to enter: resources :hourses, only: [:show]

5. What rake task is useful when looking at routes, and what information does it give you?
  "rails routes". It shows the prefix path, the http verb, the URI pattern and the controller action that's executed for a        route.

6. What is an example of a route helper? When would you use them?
  "visitors_path" for '/visitors/'. 
   I would use them anywhere where I need to specify a path in my code. They are easier to remember and easier to write and in    case the uri syntax get's changed, the paths will be updated automatically so that I don't have to change every single path    individually

7. What's the difference between what `_url` and `_path` return when combined with a routes prefix?
 
  
8. What are strong params and why are they necessary?
   Strong parameters are used to verify that the parameters (form data) coming in is permitted before it's sent to the data      base. It's is a security practice to help prevent accidentally allowing users to update sensitive model attributes and also    makes sure required attributes are present before creating a new object.

9. What role does `form_for` play in helping us create our forms?
   It's a method, which is a form helper that provides a set of methods for creating forms based on the present models. it's      designed to make working with models easier compared to using standard HTML elements.
   

10. How does `form_for` know where to submit the user's input?
   It uses the instance variable to determine if it is a form for creating new object or editing an exixting object.
   If the object has a value i.e. (params[:id]) in the controller method, then Rails knows that a resource needs to be            edited. If the instance variable holds no value, Rails knows that it needs to create a new resource.
 
11. Create a form using a `form_for` helper to create a new `Horse`.
    <%= form_for(@horse) do |f| %>
      <%= f.label :name %><br />
      <%= f.text_field :name %>
      <%= f.submit %>
    <% end %>
    

12. Why do we want to validate our models?

13. What are the steps of the DNS lookup?

### Review Questions
14. Within a feature test and given the following HTML, write the code necessary to target the following section and check the person's name?

  `<section id="personal-info">
    <h3><%= @person.name%></h3>
   </section>
  
  person = Person.create!(name: "Lisa")
  
  within "personal-info" do
    expect(page).to have_content(person.name)
  end
  
15. How would you call the method `prance` from within the method `move` on a `Horse` instance?

16. Given the following hash:

    ```ruby
    furniture = {table: {height: 3, color: "red"}, purchased: true}
    ```
    What is the difference between how you would return true vs returning 3? 
    Checking for if a condition is met or not will return eather true or false, e.g. does the hash 'include?(3)' => true.
    Quering the number 3 will return the record itself. the value must be true at first place in order to be returned.


17. What is inheritance?
    It's when a class (sub-class) inherits behavior from an other class(super-class).
    


### Self Assessment:
Choose One:
* I was able to answer most questions independently, but utilized outside resources for a few


Choose One:
* I feel comfortable with the content presented this week
