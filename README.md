# Rate a Joke

1. Background & Motivation
2. The Stack
3. To Do


## 0. Change Log


- None

## 1. Background & Motivation

So my brother is notorious for making terrible jokes at all times of the day. Granted, some of these jokes will land and they can be quite funny, but most of them tend to fall flat.
So I thought it would be fun to track all of his terrible jokes for all the world to see!
But as a computer science student, it's my duty to makes things more MoDuLaR I guess, so instead of a an application solely for the
purpose of rating my brother's jokes, this app will allow you to rate any person's jokes!

## 2. The Stack

I'll be building this application with the following

### LANGUAGE
- Typescript
Decided that it's probably time I probably learn TS and what better way to do it then through this project.

### FRONTEND
- Next.js 
- React
- Material UI

### BACKEND
- Airtable (database)
- Express
- Netlify (severless functions)
- Firebase (to host and authenticate the app)


## 3. To Do (Frontend)

The frontend is split into  feature sets which will make up the MVP for this application.

### 3.1. Feature Set 1. Authentication 
This focuses on the basic user interface to register and log in to the site. I'll use Firebase for authentication and get everyone to register and login via Google. Guests can view all jokes but they can't upload their own.

#### 3.1.1. Login Screen
 - [ ] A unique route must exist for this screen
 - [ ] User must be able to select Google for their login
 - [ ] If the form submission fails, a reasonable error message is shown
 - [ ] A button must exist to allow submission of form  

#### 3.1.2. Register Screen
 - [ ] A unique route must exist for this screen
 - [ ] User must be able to select Google for their registration
 - [ ] If the form submission fails, a reasonable error message is shown
 - [ ] A button must exist to allow submission of form  

 #### 3.1.3. Items on all screens
 - [ ] On all screens, for a user who is logged in / authorised:
   - [ ] The logout button exists somewhere
   - [ ] A button exists that will take the user to the screen to view joke ratings.
   - [ ] A button exists that will allow users to edit their own jokes ratings.
   - [ ] A button exists that will take the user to the screen to view all joke ratings.
- [ ] On all screens, for a user who is not logged in / authorised:
   - [ ] The login button exists somewhere
   - [ ] A button exists that will take the user to the screen to view joke ratings.

### 3.2. Feature Set 2. Viewing & Editing & Creating Jokes
This feature set will focus on viewing, editing and the creation of the jokes. 
A unique screen should exist for all of these functions. For these features, there will be more focus on functionality over aesthetic. 

### 3.2.1 Creating Jokes
- [ ] For a user who is logged in / authorised:
  - [ ] A "create joke" button should exist on the main screen
  - [ ] Upon clicking the create button, this takes the user to a unique screen
  - [ ] Allow the user to input the following
      - [ ]  Name of user who made the joke
      - [ ]  The joke itself
  - [ ] There should be a submit button that publishes the joke


 ### 3.2.2 Viewing and Searching Jokes
 - [ ] For all users:
    - [ ] A unique screen should exist to view all jokes
    - [ ] A search function by person who made a joke should be available
    - [ ] The jokes should be swipable on mobile, swiping left and right to view jokes
    - [ ] Each joke should have the following:
      - [ ]  Name of user who made the joke
      - [ ]  The joke itself
      - [ ]  Rating (the average)
      - [ ]  Reviews section

### 3.2.3 Editing and Deleting Jokes
- [ ] For a user who is logged in / authorised:
  - [ ] A button exists somewhere to allow users to edit jokes
  - [ ] Upon clicking the edit button, this takes the user to a unique screen
  - [ ] The user should be able to edit all of the inputs
  - [ ] The user should also be able to delete the joke entirely
  - [ ] A button exists on the unique screen to save their changes

### 3.3. Feature Set 3. Viewing & Editing & Creating Reviews
This feature set will focus on viewing, editing and the creation of reviews. 

### 3.3.1 Reviewing Jokes
- [ ] Upon viewing a joke, a user who is logged in / authorised should be able to:
  - [ ] A "rating" with starts button should exist for each joke
  - [ ] The user should be able to select a rating 1 - 10
  - [ ] The user should have an option to leave a review through a textbox
  - [ ] The user should have the option to remain anonymous
  - [ ] A submit button should exist to submit the review

 ### 3.3.2 Viewing Reviews
 - [ ] For all users:
    - [ ] Jokes should have a section for all reviews
    
### 3.3.3 Editing and Deleting Reviews
- [ ] For a user who is logged in / authorised:
  - [ ] A button exists somewhere to allow users to edit their own reviews
  - [ ] Upon clicking the edit button, this takes the user to a unique screen
  - [ ] The user should be able to edit all of the inputs
  - [ ] The user should also be able to delete the review entirely
  - [ ] A button exists on the unique screen to save their changes
 
      
## 4. To Do (Backend)
The backend is split into the main API endpoints.

### 4.1 /jokes
This is the route for retrieving, posting, updating and deleting jokes. 

#### 4.1.1. GET /jokes/{id}
- [ ] Return 404 if joke doesn't exist 
- [ ] Return 500 for server related errors
- [ ] Return 200 if success 

Example Response returns: 200 OK
```
{
 "id": 123, 
 "last_update": "2022-03-08-12:34:40",
 "joker_id": 456,
 "author_id": 678, 
 "joke": "Why did the chicken cross the road? To get to the other side!",
 "reviews": [9876, 2312, 4998],
 "rating": 4.2
}
```

#### 4.1.2. GET /jokes/order=+id&page=1&size=10&filter=id,joke,rating,joker_id
All four parameters are optional with default values being "order=+id", "page=1", and "size=10", "id,joke,rating,joker_name"
- [ ] Return 500 for server related errors
- [ ] Return 400 if there is an error in the request (ordering by something not within the filter, size is not an int, filter doesn't exist, etc.)
- [ ] Return 200 if success 

Example Response returns: 200 OK
```
{
  "page": 1,
  "page-size": 10,
  "jokes": [ 
           { 
            "id": 1,
            "joker_name": "Brad Pitt", 
            "joke": "Gorlami.", 
            "rating": 5.0
            },
           { 
            "id": 2,
            "joker_name": "Fake Namington",
            "joke": "I'm not real. I don't exist.",
            "rating": 1.3
           },
           ...
        ],
}
```

#### 4.1.3. POST /jokes/
- [ ] Return 500 for server related errors
- [ ] Return 400 if POST body is malformed
- [ ] Return 201 if joke is created 

Example Response returns: 200 OK
```
{
 "id": 123, 
 "last_update": "2022-03-08-12:34:40",
 "joker_id": 456,
 "author_id": 678, 
 "joke": "Why did the chicken cross the road? To get to the other side!",
 "reviews": [9876, 2312, 4998],
 "rating": 4.2
}
```


