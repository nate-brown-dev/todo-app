# To-Do App

## About

Frontend app built in React JS that allows user to create to-do lists.

Incorporates React Context API for state management.

## Version History

0.1.0, 15 May 2023 - Built app from previously developed starter code and obtained proof of life
0.2.0, 16 May 2023 - Implemented React Context to manage settings, added pagination, styled app with Mantine
0.3.0, 17 May 2023 - TBD

## Whiteboard

Whiteboard to follow

## Feature Tasks
------------
Lab 32 requirements below

LAB: Context API - Behaviors
To Do List Manager Phase 2: Incorporate configuration settings to the application.

In this phase, we’ll be adding a settings editor so that users can save their preferences for the application, allowing them to change some of the default behaviors.

Before you begin
Refer to Getting Started in the lab submission instructions for complete setup, configuration, deployment, and submission instructions.

Continue to work in your GitHub Repository named todo-app.
Create and work in a new branch for today called ‘context-methods’.
Business Requirements
Refer to the To Do System Overview for a complete review of the application, including Business and Technical requirements along with the development road map.

Phase 2 Requirements
In Phase 2, we’re going to extend the functionality of our application by allowing the user to make some decisions on how they would like the application to function. Specifically, we’ll let them make changes to 2 settings.

Implement the Context API to make some basic application settings available to components.
How many To Do Items to show at once.
Whether or not to show completed items.
Hint: if reusing the custom useForm() hook, event validation may be necessary if using any Mantine component other than <TextInput />.
Provide the users with a form where they can change the values for those settings.
This should be given in the form of a new component, perhaps linked to from the main navigation.
Hint: Use Browser Router to create the page/route/component for this.
Once settings are updated, render the updated settings to the right of the “form”. Consider using <Grid />, <Card />, and <When /> components.
Save the users choices in Local Storage.
Retrieve their preferences from Local Storage and apply them to the application on startup.
Todo Comp
Todo with Pagination

Settings Comp
Settings Page

Technical Requirements / Notes
Technical requirements for the core application are unchanged from the prior phases, with the addition of context behaviors defined in our global Context Provider.

Extend your context provider to include all of the following features:
Create a context for managing application settings and provide this at the application level.
Display or Hide completed items (boolean).
Number of items to display per screen (number).
Default sort field (string).
Create a function in your context that saves user preferences (for the above) to local storage.
Implement a useEffect() (or componentDidMount()) in your context to read from local storage and set the values for those 2 state properties on application load.
Note: You will need to stringify() your state prior to saving to local storage, and parse it when you retrieve it.

Consume and utilize Context values throughout your components:
Show a maximum of a certain number of items per screen in the <List /> component.
Properly implement the Mantine <Pagination /> component functionality to let the users navigate a long list of items with the correct number of tasks showing per “page”.
Hide or show completed items in the list.
Proposed File Structure
In this proposal:

Utilize Airbnb React/JSX Style Guide conventions.
unit tests are placed in the component directory (testing one file only).
integration tests are placed in the __tests__ directory (testing more than one file).
├── .github
│   ├── workflows
│   │   └── node.yml
├── public
├── src
│   ├── __tests__
│   │   ├── App.test.jsx
│   ├── Components
│   │   ├── Footer
│   │   │   └── index.jsx
│   │   ├── Header
│   │   │   └── index.jsx
│   │   ├── List
│   │   │   └── index.jsx
│   │   ├── SettingsForm
│   │   │   └── index.jsx
│   │   ├── Todo
│   │   │   ├── index.jsx
│   │   │   └── styles.scss  
│   ├── Context
│   │   ├── Settings
│   │   │   ├── index.jsx
│   │   │   └── settings.test.jsx
│   ├── hooks
│   │   └── form.js
│   ├── App.jsx
│   └── index.js
├── .gitignore
├── package-lock.json
├── package.json
└── README.md
Stretch Goal:
Sort the items based on any of the keys (i.e. difficulty).
Update the state handling for todo items to use useReducer() vs separate state management methods.
Testing
Tests should assert all behavioral functionality.
Do a deep mount of the app, and set tests to make assertions on the child components that consume context from the Provider.
Can they see context?
Assignment Submission Instructions
Refer to the the Submitting React Apps Lab Submission Instructions for the complete lab submission process and expectations.

------------
Lab 31 requirements below

LAB - Context API
To Do List Manager Phase 1: Incorporate configuration settings to the application.

Currently, a user can add todo tasks to the proof-of-life starter application. In this phase, we will add hard-wired, default context settings to the application so that the user can view three incomplete todo tasks. In addition, the user will have the option of viewing any additional incomplete tasks by using pagination functionality.

Before you begin
Refer to Getting Started in the lab submission instructions for complete setup, configuration, deployment, and submission instructions.

Use Create React App (CRA) to create a new application named todo-app.
Delete the existing src directory.
Paste in the src directory from the lab/starter-code.
Run npm install uuid sass.
npm start and confirm that the application loads in the browser.
Create an EMPTY GitHub Repository named todo-app.
Follow GitHub instructions labeled “…or push an existing repository from the command line”.
Note: after completeing the above step, CRA starter code will have been pushed to your GitHub Repo.
Immediately ACP after adding your newly created repo to GitHub; this will add the starter-code to your repo and give you the option to rollback changes to the base starter code if necessary.
Create and work in a new branch for today called context-settings.
Business Requirements
Refer to the To Do System Overview for a complete review of the application, including Business and Technical requirements along with the development road map.

Learning Outcomes
Learn React context functionality and gain overall React fluency.
Gain provicency in reading documentation by using a new component library.
Practice JavaScript array manipulation by implementing pagination.
Gain React testing fluency.
Phase 1 Requirements
In Phase 1, we’re going to perform some refactoring of a Todo application built by another team. This application mixes application state and user settings at the top level and passes things around. It was a good proof of concept, but we need to make this production ready.

Create a Detailed UML.
Properly modularize the application into separate components, note the proposed file structure below.
Implement the Context API to make some basic application settings available to components.
Show three items by default.
Hide completed items by default.
Add the sort word ‘difficulty’ by default.
Style the application using the Mantine Component API{target:_blank}.
NOTE: The expectation to style this entire component in one day is likely unrealistic. The recommendation is to implement the required functionality, then systematically begin styling with Mantine. Match the comp image(s) as closely as possible. 80% of the design work will likely take 20% of your time. By the end of the week, being mostly there with style is the goal!
To Do with Pagination

Technical Requirements / Notes
Create a settings Context component that can define how our components should display elements to the User.

Implement the React context API for defining settings across the entire application.
Create React Context for managing application display settings and provide this at the application level.
Add the following defaults to the context provider’s state, they will not be changeable in this lab.
Display three items.
Hide completed items using a boolean.
Define “difficulty” as a default sort word to optionally use in the stretch goal.
Consume and utilize context values throughout your components.
Show a maximum of three items per screen by default in the <List /> component.
Use the Mantine <Pagination /> component to allow users to navigate a list of items.
Hide completed items in the list by default (the ability to show will be added in a later lab).
Pagination Notes:
Only display the first n items in the list, where n is the default number three from your settings context.
If you have more than n items in the list, the <Pagination /> component will add a button that, when clicked, will replace the list with the next n. items in the list.
the <Pagination /> component will manage the “previous” and “next” buttons upon correct implementation.
Proposed File Structure
In this proposal:

Utilize Airbnb React/JSX Style Guide conventions.
unit tests are placed in the component directory (testing one file only).
integration tests are placed in the __tests__ directory (testing more than one file).
├── .github
│   ├── workflows
│   │   └── node.yml
├── public
├── src
│   ├── __tests__
│   │   ├── App.test.jsx (integration test)
│   ├── Components
│   │   ├── Footer
│   │   │   └── index.jsx
│   │   ├── Header
│   │   │   └── index.jsx
│   │   ├── List
│   │   │   └── index.jsx
│   │   ├── Todo
│   │   │   ├── index.jsx
│   │   │   └── styles.scss  
│   ├── Context
│   │   ├── Settings
│   │   │   ├── index.jsx
│   │   │   └── Settings.test.jsx (unit test)
│   ├── hooks
│   │   ├── form.js
│   │   └── styles.js (optional)
│   ├── App.jsx
│   └── index.js
├── .gitignore
├── package-lock.json
├── package.json
└── README.md
Stretch Goals
Sort the items based on any of the keys (i.e. difficulty).
In your Context component, read the settings in from an object in Local Storage and use that as the initial state.
Testing
Tests should assert all behavioral functionality.
Do a deep mount of the app, and set tests to make assertions on the child components that consume context from the Provider.
Can they see context?
Documentation
Describe how global state is consumed by the components.
Describe the operation of the hook: useForm().
Assignment Submission Instructions
Refer to the the Submitting React Apps Lab Submission Instructions for the complete lab submission process and expectations.