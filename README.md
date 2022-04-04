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

- React w/ Material UI 
- Node.js
- Airtable (database)
- Auth0 (authentication) 
- Firebase (to host the app)

## 3. To Do

The task is split into 3 feature sets which will make up the MVP for this application.

### 3.1. Feature Set 1. Authentication 
This focuses on the basic user interface to register and log in to the site. I'll use Auth0 for authentication and get everyone to register and login via Google. Guests can view all lists but they can't upload their own lists.

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

### 3.2. Feature Set 2. Viewing & Editing & Creating Joke Ratings
This feature set will focus on viewing, editing and the creation of the jokes. 
A unique screen should exist for all of these functions. For these features, there will be more focus on functionality over aesthetic. 

### 3.2.1 Creating Ratings
- [ ] For a user who is logged in / authorised:
  - [ ] A "create rating" button should exist on the main screen
  - [ ] Upon clicking the "reate button, this takes the user to a unique screen
  - [ ] Allow the user to input the following
      - [ ]  Name of user being rated*
      - [ ]  The joke itself*
      - [ ]  Rating* (1 to 10 stars)
      - [ ]  Review (optional)
      - [ ]  Anonymous button (optional)
  - [ ] There should be a submit button that saves the joke


 ### 3.2.2 Viewing and Searching Jokes
 - [ ] For all users:
    - [ ] A unique screen should exist to view all ratings
    - [ ] A search function by person who made joke should be available

### 3.2.3 Editing Ratings
- [ ] For a user who is logged in / authorised:
  - [ ] A button exists somewhere to allow users to edit their own ratings
  - [ ] Upon clicking the edit button, this takes the user to a unique screen
  - [ ] The user should be able to edit all of the inputs
  - [ ] The user should also be able to delete the rating entirely
  - [ ] A button exists on the unique screen to save their changes
