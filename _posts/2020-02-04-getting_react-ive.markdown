---
layout: post
title:      "Getting React-ive"
date:       2020-02-04 05:05:46 +0000
permalink:  getting_react-ive
---


For my final project, I developed a React/Redux application named ECHO. The idea was to design an easy-to-use digital flight logbook for pilots. It’s important to maintain a backup flight log in order to calculate hours and confirm endorsements if a physical logbook is ever lost or destroyed. The benefit of a digital logbook is the ability to store years of flight information in one, centralized location, rather than combing through dozens of material logbooks.

The basic user experience entails securely signing up and logging in, browsing an index of existing flights with general information, selecting a specific flight to view detailed information, and adding new flights to the logbook. 

### Step 1: rails new --api
A Rails API backend handles data persistence within the app. I utilized the following workflow to get the backend up and running. 

First, I activated CORS and updated the API port to 3001, leaving port 3000 available for NPM. Next, I created the fundamental user and flight resources, implementing api/v1 namespacing in case of future updates. I defined the model relationships in addition to adding validations. I incorporated the `fast_jsonapi gem` to build serializers for both resources. Finally, I added basic index, show, and create actions to the users controller, and all CRUD actions to the flights controller. I then created some simple seed data, migrated the database, and tested that the API was working as expected.

### Step 2: create-react-app
Per the requirements, I used `create-react-app` to generate the client side of my project. This allowed me to quickly start building out the frontend of my single-page application. This generator provides the essential structure and tools needed to jump right in to designing a React application. 

### Step 3: react-redux & redux (redux-thunk, too!)
React and Redux work together to render and store data on the frontend of the app. I followed these next steps to build out the client side.

I started by configuring the Redux store and wrapping the base App component with the store Provider as well as react-router-dom’s BrowserRouter, which allows for declarative RESTful routing without page refresh. With these in place, I was able to begin developing the Redux store. Utilizing `redux-thunk` action creators, I built user actions in addition to a reducer. I implemented a root reducer to manage the combined reducers, and added the user reducer to this store. 

After testing that users were now in my store by checking with DevTools, I built a basic home page component to be rendered from App. Next, I dove into developing login functionality. I incorporated the `bcrypt gem` along with sessions in the backend to securely manage user passwords. On the frontend, I built a login component and made the decision to manage the form’s state through the Redux store, rather than in local state. The final piece of the puzzle was creating the actions and the reducers to handle creating and setting the user properly, along with updating and resetting the login form’s state. Next, I added in a comparatively simple logout component with the associated actions and reducer to clear the user’s session. With everything in place for login, I was able to reuse a good deal of this functionality to devise a sign up component.

With user login, logout, and signup in order, I then moved on to implementing the flight form and log. I began by developing a flight log container that would render flight index cards on the user’s main account page. I built a flight card component to render basic flight details and then got to work on the flight form component. I incorporated two containers for the form, one for new flights and the other to edit an existing flight. For flight actions, I first built out the form’s more simple actions and reducer to update, reset, and set the edit values for the form. As with login, flight form data would be managed in the Redux store rather than locally. Then it was time to tackle adding all CRUD actions for flights, including setting the current user’s flights.

As expected, the vast majority of time and troubleshooting for this project was spent on step 3. I found the biggest challenge to be deciding to go with a specific design pattern, only to realize I should redesign in a more efficient manner. This was the source of the biggest headaches as well as the most rewarding “aha!” moments on this project. 

### Step 4: react-router
Time to circle back to `react-router-dom`’s BrowserRouter. This functionality was actually integrated in tandem with each piece of step 3, but deserves a quick, special aside. In order to use RESTful navigation on a single-page app without refresh, the main App component must use BrowserRouter. This enables us to declare custom routes which render an associated component, allowing for useful, descriptive URLs based on the current content. For example, visiting “/login” renders the login component, or typing in “/flights/:id/edit” shows a specific flight’s edit page. This makes traversing the application more user-friendly and predictable.

### Final Thoughts
Developing ECHO was a wonderful learning experience and truly helped me to gain a deeper understanding of React and Redux. If anything, my biggest takeaway is that there are a thousand different ways to accomplish something, especially in programming. However with each new problem, some of those approaches will whittle away and the opportunity to learn better processes and patterns will emerge - the goal is to stay receptive and react-ive to those opportunities.

