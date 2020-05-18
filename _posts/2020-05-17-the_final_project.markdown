---
layout: post
title:      "The Final Project"
date:       2020-05-17 23:27:32 -0400
permalink:  the_final_project
---


The final project for Flatiron School was to create an app using React-Redux frontend and Rails-API backend. It took me some time to figure out what to do for my final project. I figured the best place to look was at my previous projects the ideas I used for those. At first, I was thinking about doing something workout-related but I couldn't work out the structure of how I wanted it to look. Then I started thinking of something relating to games, that is one of the main reasons I got an interest in coding, to begin with. To start I set up the Rails backend API, this will be handling data persistence. I used rails new  --api to generate the API and then I used rails g scaffold to create the controllers and models.  I used the create-react-app generator to start my project. This will set up everything I would need to build a single-page React application. Set-up files, containers, components, and reducers. Then it was onto adding react-redux to the project, I used some components and functions to bring React and Redux together such as Provider, Store, and Connect.
```
import React from 'react';
import ReactDOM from 'react-dom';
import './index.css';
import App from './App';
import { BrowserRouter as Router } from 'react-router-dom';
import { createStore, applyMiddleware, compose } from 'redux';
import { Provider } from 'react-redux';
import thunk from 'redux-thunk';
import rootReducer from './reducers/rootReducer.js';
import * as serviceWorker from './serviceWorker';

const composeEnhancers = window.__REDUX_DEVTOOLS_EXTENSION_COMPOSE__ || compose;

const store = createStore(rootReducer, composeEnhancers(
applyMiddleware(thunk)
));

ReactDOM.render(
<React.StrictMode>
<Provider store={store}>
<Router>
<App />
</Router>
</Provider>
</React.StrictMode>,
document.getElementById('root')
);
```.  I moved unto setting up Redux-Thunk Middleware, I tried using fetch requests without it but I was running into errors dealing with the execution of code. When fetching my data from the API the problem I ran into was the action creator returned an action before the data was retrieved. So to resolve this issue I implemented the middleware Thunk. One of the requirements for the project was to use React Router, this allows us to build a single-page application with navigation without page refresh. React Router uses a component structure to call components that display the appropriate information. Another requirement for the project was to have at least 5 components. I used 2 container components that would be connected to the 9 presentational components. These components are stateless and accept props from the container component and do not interact with the Redux store. 
I used functional components on components that I didn't need a state which is available to the class components. A big thank you to Flatiron School for taking me on this coding journey that's only now beginning and thank you for reading this blog post. 
