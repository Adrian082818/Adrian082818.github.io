---
layout: post
title:      "understanding rails routing"
date:       2020-04-04 14:19:23 +0000
permalink:  understanding_rails_routing
---


When an HTTP request is sent from the user’s browser, it needs to know which controller action should be run. Either to display the new user webpage or the display the edit user form, depending on what the HTTP request is the controller action runs the method that is associated with the request. Now those are actions of basic routing such as the controller taking you to /users/sign_in or /users/new, now say I wanted to expand upon my user or for my project I was working with coaches and exercises. I could have generated routes for exercises, or I could nest exercise within the coaches routes such as ```resources :coaches  do 
          resources :exercises [:index, :new]
end ``` 
this would produce new nested routes such as ` /coaches/:coach_id/exercises(.:format)                                                   exercises#index`
which is a get request for exercises of the coaches from the index. If I want my index action to display a collection of exercises that belong to the coach that I am navigating to, I will need to pass ‘params[:coach_id]’ in as an argument so that only the exercises from the coach whose ID matches what I passed in is displayed. Now I need to update my form in my view so that it also displays the coach's names not just the attributes of the exercises. To do this I iterate over the exercises instance variable that I'm getting from the index method I created in the controller and I'm pulling the attributes to display them through my .each block like so `<% @exercises.each do |exercise| %>`. Now to display coach's names I do `<%= exercise.coach.name %>`.  If I wanted to add an edit route for those particular exercises of the coach, I would add that route to my nested resource of exercise thats withing coaches because currently it only has access to :new and :index. Then I would add a coach instance variable to the edit method in my controller where it would find the coach by its id through params then I would have to change the view so that it renders and make sure I'm using the correct path. Now I am working with `edit_coach_exercise_path` and I would pass in what is required from what I set in the controller method edit, so the path would look like `edit_coach_exercise_path(@coach, exercise)`. Testing it out when you click on the link to edit a coach's exercises it takes you to URL of `coaches/2/exercises/43/edit` which is the nested route. 
