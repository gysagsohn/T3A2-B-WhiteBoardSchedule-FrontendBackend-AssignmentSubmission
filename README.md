
# T3A2-B-WhiteBoardSchedule-FrontendBackend-AssignmentSubmission

This project is the culmination of my final assignment for Corder Academy. It is a MERN (MongoDB, Express, React, Node.js) full-stack web application designed to manage scheduling information for operators, assets, clients, and allocations within a company. The application includes a frontend interface built with React and a backend built with Node.js, Express, and MongoDB.

## Table of Contents

- [Repository Links](#repository-links)
- [Website Links](#website-links)
- [Deployment](#deployment)
- [Project Overview](#project-overview)
- [Planning](#planning)
- [Packages/Libraries](#packageslibraries)
- [Routes/Pages](#routespages)
- [Contexts](#contexts)
- [Data Management](#data-management)
- [Components](#components)
- [Styling (CSS)](#styling-css)
- [Functional Overview](#functional-overview)
- [Future Enhancements](#future-enhancements)
- [Project Management](#project-management)
- [Development Testing](#development-testing)
  - [Frontend Testing](#frontend-testing)
    - [Dashboard Page](#dashboard-page)
    - [Allocation Page](#allocation-page)
    - [Asset Page](#asset-page)
    - [Client Page](#client-page)
    - [Operator Page](#operator-page)
    - [User Page](#user-page)
    - [Login/Signup Page](#loginsignup-page)
    - [Hosting](#hosting)
    - [UI/UX Testing](#uiux-testing)
    - [Mobile Responsiveness](#mobile-responsiveness)
  - [Backend Testing](#backend-testing)
    - [Basic Backend Files](#basic-backend-files)
    - [Seeding Data](#seeding-data)
    - [Hashing Passwords](#hashing-passwords)
    - [Route Testing](#route-testing)
      - [Asset Router](#asset-router)
      - [Client Router](#client-router)
      - [Operator Router](#operator-router)
      - [User Router](#user-router)
      - [Allocation Router](#allocation-router)
    - [Error Handling Routes](#error-handling-routes)
    - [Backend Server Testing](#backend-server-testing)
-[Product Testing](#production-testing)

## Repository Links

- **Frontend Repository**: [GitHub - Frontend](https://github.com/gysagsohn/t3a2_whiteboard_frontend)
- **Backend Repository**: [GitHub - Backend](https://github.com/gysagsohn/T3A2B_whiteboardscheduler_backend)
- **Combined Repository**: [GitHub - Frontend & Backend Combined](https://github.com/gysagsohn/T3A2-B-WhiteBoardSchedule-FrontendBackend-AssignmentSubmission)

## Website Links

- **Live Website**: [Whiteboard Scheduler](https://whiteboardschedulercom.netlify.app/)
- **Custom Domain**: [whiteboardscheduler.com](https://whiteboardscheduler.com/)

## Deployment

- **Frontend Deployment**: The frontend has been deployed using **Netlify**.
- **Backend Deployment**: The backend is deployed using **Render**.

## Project Overview

This application allows users to manage scheduling information for operators, assets, clients, and allocations through a user-friendly interface. The frontend communicates with the backend via RESTful APIs to perform CRUD operations. The backend handles data storage and processing, while the frontend provides a responsive interface for user interaction.

## Planning

Extensive planning was completed for this project. The planning files can be found here:
[Part A assignment](resources/PartA)

### Changes from the Original Plan

- **Admin Function**: This feature was abandoned due to time constraints and difficulties in implementation. As a result, the user function on the frontend differs slightly from the backend.
- **Color Scheme**: The same color scheme outlined in the plan was used, but in different proportions after realizing the original distribution did not meet design expectations.
- **User Route on Frontend**: The original plan was to have the user route on the top right-hand corner of the page, but due to time constraints, this feature was not implemented. The user route is now included in the navbar and functions correctly.
- **Layout for Create and Edit**: The original plan was to navigate to a new page when creating or editing in Asset, Client, Operator, and Allocation. However, it was found that these actions could be done more efficiently on a single page, so the layout was adjusted accordingly.
- **Login and Signup Layout**: Instead of redirecting to a new page, a modal package was used for a more elegant solution.

### Changes from the Original Plan

- **Admin Function**: This feature was abandoned due to time constraints and difficulties in implementation. As a result, the user function on the frontend differs slightly from the backend.
- **Color Scheme**: The same color scheme outlined in the plan was used, but in different proportions after realizing the original distribution did not meet design expectations.
- **User Route on Frontend**: The original plan was to have the user route on the top right-hand corner of the page, but due to time constraints, this feature was not implemented. The user route is now included in the navbar and functions correctly.
- **Layout for Create and Edit**: The original plan was to navigate to a new page when creating or editing in Asset, Client, Operator, and Allocation. However, it was found that these actions could be done more efficiently on a single page, so the layout was adjusted accordingly.
- **Login and Signup Layout**: Instead of redirecting to a new page, a modal package was used for a more elegant solution.

## Packages/Libraries

### Frontend

- **React**: Core framework for building the user interface.
- **React Router DOM**: For handling routing and navigation between pages.
- **React Modal**: For implementing modals on the login and signup pages.
- **Axios**: For making HTTP requests to the backend API.
- **CORS**: To enable cross-origin resource sharing between the frontend and backend.
- **React Icons**: For adding icons (GitHub, LinkedIn) to the contact page.

### Backend

- **Express**: Web framework for building the backend API.
- **Mongoose**: For MongoDB data modeling.
- **bcryptjs**: For password hashing.
- **jsonwebtoken**: For handling JWT authentication.
- **dotenv**: For managing environment variables.
- **cors**: For enabling cross-origin resource sharing.
- **nodemon** (Dev Dependency): For automatically restarting the server during development.

## Routes/Pages

### Frontend

The application is divided into several pages, each accessible through specific routes:

- **Dashboard Page** (`/`): Home page displaying a summary of allocations, assets, clients, and operators.
- **Login Page** (`/login`): Allows users to log in; redirects to the dashboard upon successful login.
- **Operator Page** (`/operator`): Manage operators, including creating, updating, and deleting operator records.
- **Asset Page** (`/asset`): Manage assets with options to create, update, and delete asset records.
- **Client Page** (`/client`): Manage client information with full CRUD functionality.
- **Allocation Page** (`/allocation`): Manage allocations, including assigning assets and operators to clients.
- **User Page** (`/user`): Manage user details; currently allows editing and deleting user profiles.
- **Contact Page** (`/contact`): Displays contact information with links to GitHub and LinkedIn profiles.

### Backend

Each data model in the backend has its own route:

- **User**: `/users`
- **Asset**: `/assets`
- **Operator**: `/operators`
- **Client**: `/clients`
- **Allocation**: `/allocations`

These routes handle all CRUD operations and include authentication checks using JWT tokens.

## Contexts

### Frontend

- **Authentication Context**: Used to manage user authentication state across the application, ensuring only authenticated users can access certain pages.

## Data Management

### Frontend

The application handles the following data entities, each corresponding to specific pages:

- **Login**: Authenticates users and manages session tokens.
- **Operator**: Handles data related to operators, including license classes and available days.
- **Asset**: Manages assets, including asset types and registration information.
- **Client**: Manages client information and associated projects.
- **Allocation**: Manages the allocation of assets and operators to clients.
- **User**: Handles user profiles, allowing updates to user details.

### Backend

The backend manages the following models:

- **User**: Handles user authentication and authorization.
- **Asset**: Manages details about assets, such as asset number, type, and registration information.
- **Operator**: Manages operators, including their license classes and availability.
- **Client**: Manages client information, including associated projects.
- **Allocation**: Manages the assignment of assets and operators to clients.

## Components

### Frontend

The application is built with reusable components to enhance maintainability and scalability:

- **NavBar**: A responsive navigation bar that includes links to different pages and a logout button. It dynamically changes color based on the current active page.
- **Header**: Contains the application’s logo and a link back to the dashboard.
- **Button**: Customizable buttons used throughout the application, with styles that change on hover and active states.

## Styling (CSS)

### Frontend

The application uses a modular CSS approach, with separate files for each component and page:

- **Global Styles** (`global.css`): Contains the base styles for the entire application, including typography and colors.
- **Button Styles** (`buttons.css`): Defines the styles for primary, secondary, and disabled buttons.
- **Page-Specific Styles**: Each page has its own CSS file to handle unique styling needs:
  - `dashboardPage.css`
  - `operatorPage.css`
  - `assetPage.css`
  - `clientPage.css`
  - `allocationPage.css`
  - `userPage.css`
  - `contactPage.css`
- **Responsive Design**: CSS media queries are used to ensure the application is fully responsive and usable on different screen sizes.

## Functional Overview

### Frontend

The application is designed with the following functionalities:

- **Authentication**: Users must log in to access most of the pages. JWT tokens are stored in local storage to maintain sessions.
- **CRUD Operations**: Each data entity (operator, asset, client, allocation, user) can be created, read, updated, and deleted through the respective pages.
- **Responsive Design**: The application is fully responsive, with layouts adjusting for mobile, tablet, and desktop screens.
- **Modals**: The login and signup forms are displayed in modals, providing a smooth user experience without navigating away from the current page.

## Future Enhancements

### Frontend

- **Dark/Light Mode**: Implement a theme toggle that allows users to switch between dark and light modes.
- **User Profile Page**: Add a dedicated page for users to view and edit their profiles.
- **Enhanced Error Handling**: Improve error messages and feedback to users during operations like login and data submission.
- **Improved Accessibility**: Ensure all components and pages are fully accessible to users with disabilities, following WCAG guidelines.

### Backend

- **Admin Function**: Potentially adding an admin feature to manage users and data.
- **Data Access Control**: Implementing middleware for data authorization based on user roles and the company they belong to.

## Project Management

To ensure the development process was organized and efficient, I used **Trello** for task management and assigned **story points** to estimate the effort required for each task. I also followed the **Conventional Commits** standard for commit messages.

### Trello Kanban Board

- **Trello**: resources/trello baord

### Story Points

- **Story Points**: Each task on the Trello board was assigned story points, which represented the estimated difficulty and time required to complete the task. This helped prioritize tasks and allocate time more effectively throughout the project.

### Conventional Commits

- **Conventional Commits 1.0.0**: I adhered to the Conventional Commits standard for my Git commit messages, making it easier to understand the changes made in each commit. This practice improved the clarity and organization of the commit history.

## Development Testing

### Frontend Testing

The application was manually tested during development to ensure all functionalities worked as intended. Below is an overview of the testing methods and results for each page.

#### Dashboard Page

- **Basic Route**: Passed  
  *Method*: Start the app and go to the local host to verify if the message is displayed correctly.
  ![Dashboard Testing](<resources/Development Testing/frontend/route testing/Dashboard testing.png>)
  
- **API Route**: Passed  
  *Method*: Start the app and go to the local host to check if data is being fetched and displayed correctly.
  ![Dashboard API Testing](<resources/Development Testing/frontend/route testing/Dashboard API.png>)

#### Allocation Page

- **Basic Route**: Passed  
  *Method*: Go to the route (localhost:3000/allocation) and verify if the page loads correctly.
  ![Allocation Page Testing](<resources/Development Testing/frontend/route testing/Allocation Page Testing.png>)
  
- **Create Data**: Passed  
  *Method*: Use Bruno to create data in the backend and verify if it appears on the front end.
  ![Creating Data](<resources/Development Testing/frontend/route testing/Allocation Page/creating some data.png>)

- **Edit Data**: Passed  
  *Method*: Edit existing data and check if the changes are reflected.
  ![Edit Data](<resources/Development Testing/frontend/route testing/Allocation Page/edit.png>)
  
- **Delete Data**: Passed  
  *Method*: Delete data and verify if it is removed from the list.
  ![Delete Data](<resources/Development Testing/frontend/route testing/Allocation Page/delete.png>)

#### Asset Page

- **Basic Route**: Passed  
  *Method*: Go to the route (localhost:3000/asset) and verify if the page loads correctly.
  ![Asset Page Testing](<resources/Development Testing/frontend/route testing/AssetPage/Asset Page testing.png>)
  
- **API Route**: Passed  
  *Method*: Use Bruno to create data in the backend and verify if it appears on the front end.
  ![Asset API Testing](<resources/Development Testing/frontend/route testing/AssetPage/Asset API tested.png>)
  ![Asset Route with API data](<resources/Development Testing/frontend/route testing/AssetPage/asset page with an asset created.png>)

- **Create Asset**: Failed  
*Method*: Use route to create new asset
![Asset Route](<resources/Development Testing/frontend/route testing/AssetPage/asset page with create function.png>)
![Failed Method](<resources/Development Testing/frontend/route testing/AssetPage/issues with creating asset.png>)

**Round 2**

- **API Route**: Passed  
  *Method*: go to route to see API data is coming and button is present
  ![new Asset route](<resources/Development Testing/frontend/route testing/AssetPage/round2/AssetAPI.png>)

- **Create Asset**: PAssed - but when typing the info isn't coming up  
  *Method*: Use route to create new asset
  ![Creating Asset but can't see typing](<resources/Development Testing/frontend/route testing/AssetPage/round2/it does update but I can't see what I am typing.png>)

**Round 3**
- **Create/edit Asset with preview**: Passed 
  *Method*: Use route to create new asset
  ![Edit Asset and preview working]!(<resources/Development Testing/frontend/route testing/AssetPage/round2/new asset.png>)

- **Button and Data Preview**: Passed  
  *Method*: Verify that buttons and data preview correctly.
  ![Preview Testing](<resources/Development Testing/frontend/route testing/AssetPage/round2/test to show it shows preview.png>)

#### Client Page

- **Basic Route**: Passed  
  *Method*: Go to the route and verify if the page loads correctly.
  ![Client Page Testing](<resources/Development Testing/frontend/route testing/client page/client page testing.png>)
  
- **Backend info showing**: Passed  
  *Method*: Go to route and see backend info is showing
  ![Back end info showing](<resources/Development Testing/frontend/route testing/client page/client page.png>)
  
- **Add Client**: Passed  
  *Method*: Add a new client and verify if it is added to the list.
  ![Add Client](<resources/Development Testing/frontend/route testing/client page/adding new client.png>)
  
- **Edit Client**: Passed  
  *Method*: Edit a client and verify if the changes are reflected.
  ![Edit Client](<resources/Development Testing/frontend/route testing/client page/editing client.png>)
  
- **Delete Client**: Passed  
  *Method*: Delete a client and verify if it is removed from the list.
  ![Delete Client](<resources/Development Testing/frontend/route testing/client page/deleting client.png>)

#### Operator Page

- **Basic Route**: Passed  
  *Method*: Go to the route and verify if the page loads correctly.
  ![Operator Page Testing](<resources/Development Testing/frontend/route testing/OperatorPage/Opeartor page testing.png>)
  
- **API for backend working**: Passed  
  *Method*: go to route to see if backend data is showing up
  ![Operator CRUD Testing](<resources/Development Testing/frontend/route testing/OperatorPage/Operator Page.png>)
  
- **Add Operator**: Passed  
  *Method*: Add a new operator and verify if it is added to the list.
  ![Add Operator](<resources/Development Testing/frontend/route testing/OperatorPage/New operator.png>)

- **Edit Operator**: Passed  
  *Method*: Edit an operator and verify if the changes are reflected.
  ![Edit Operator](<resources/Development Testing/frontend/route testing/OperatorPage/edit operator.png>)
  
- **Delete Operator**: Passed  
  *Method*: Delete an operator and verify if it is removed from the list.
  ![Delete Operator](<resources/Development Testing/frontend/route testing/OperatorPage/delete operator.png>)

#### User Page

- **Basic Route**: Passed  
  *Method*: Go to the route and verify if the page loads correctly.
  ![User Page Testing](<resources/Development Testing/frontend/route testing/userPage/User Page Testing.png>)
  
- **API route**: Passed  
  *Method*: go to route to see if backend data is showing up
  ![User CRUD Testing](<resources/Development Testing/frontend/route testing/userPage/User API.png>)
  
- **Edit User**: Passed  
  *Method*: Edit a user and verify if the changes are reflected.
  ![Edit User](<resources/Development Testing/frontend/route testing/userPage/edit user API.png>)
  
- **Delete User**: Passed  
  *Method*: Delete a user and verify if it is removed from the list.
  ![Delete User](<resources/Development Testing/frontend/route testing/userPage/Screenshot 2024-08-09 at 9.31.14 AM.png>)

#### Login/Signup Page

- **Basic Route**: Passed  
  *Method*: Go to the route and verify if the page loads correctly.
  ![Login Page Testing](<resources/Development Testing/frontend/route testing/Login Page testing.png>)
  
- **Protected Route**: Passed  
  *Method*: Attempt to access a protected route without logging in and verify if it redirects to the login/signup page.
  ![Protected Route Testing](<resources/Development Testing/frontend/route testing/Login Page/Login:singup page with options for both.png>)
  
- **JWT Handling Issue**: Failed initially due to missing CORS implementation, resolved after adding CORS.
  *Method*: Attempt to login
  ![JWT Handling Issue loggin in](<resources/Development Testing/frontend/route testing/Login Page/failed login.png>)
  ![JWT Handling Fixed](<resources/Development Testing/frontend/route testing/Dashboard API.png>)

  - **Modal and button**: Passed
  *Method*: See if modal works and buttons (note it worked but other issues as above)
  ![JWT Handling Issue loggin in](<resources/Development Testing/frontend/route testing/Login Page/failed signup.png>)
  ![JWT Handling Fixed](<resources/Development Testing/frontend/route testing/Dashboard API.png>)

#### Hosting

- **URL Working**: Initially failed but resolved after waiting for DNS propagation.
  *Method*: visit url
  ![URL Working](<resources/Development Testing/frontend/route testing/Hosting working.png>)

- **DNS Redirection**: Initially failed but resolved after waiting for DNS propagation.
  *Method*: visit url
  ![URL Working Final](<resources/Development Testing/frontend/route testing/Hosting working.png>)

#### UI/UX Testing

- **Color Consistency**: Passed  
  *Method*: Verify that the selected colors are applied consistently across the site.
  ![Color Testing](<resources/Development Testing/frontend/route testing/UI testubg/Colour.png>)
  
- **Navbar Color Change**: Passed  
  *Method*: Navigate through different pages and verify that the navbar color changes according to the active route.
  ![Navbar Color Change](<resources/Development Testing/frontend/route testing/UI testubg/mobile user/Asset Page.png>)

- **Logo Link**: Passed  
  *Method*: Click on the logo and verify if it navigates back to the dashboard.
  ![Navbar Color Change](<resources/Development Testing/frontend/route testing/UI testubg/mobile user/Asset Page.png>)

- **Icon Visibility**: Passed  
  *Method*: Verify that the GitHub and LinkedIn icons are visible and functional.
  ![GitHub and LinkedIn Icons](<resources/Development Testing/frontend/route testing/UI testubg/Git hub and Linkedin ICON.png>)

- **Link Functionality**: Passed  
  *Method*: Click on the icons and verify if they redirect to the correct profiles.
  ![GitHub Link](<resources/Development Testing/frontend/route testing/UI testubg/Git HUB.png>)
  ![LinkedIn Link](<resources/Development Testing/frontend/route testing/UI testubg/Linkedin.png>)

#### Mobile Responsiveness

- **Login/Signup Page**: Passed  
  *Method*: Use inspect mode to simulate a smaller screen and verify that the layout adjusts correctly.
  ![Login/Signup Mobile](<resources/Development Testing/frontend/route testing/UI testubg/mobile user/Client Page.png>)
  
- **Dashboard Page**: Passed  
  *Method*: Use inspect mode to simulate a smaller screen and verify that the layout adjusts correctly.
  ![Dashboard Mobile](<resources/Development Testing/frontend/route testing/UI testubg/mobile user/dashboard page.png>)
  
- **Scrolling within the Box**: Passed  
  *Method*: Verify that scrolling works correctly within content boxes.
  ![Scrolling Box](<resources/Development Testing/frontend/route testing/UI testubg/mobile user/scrolling within the box.png>)

### Backend Testing

#### Basic Backend Files

**Server Testing**

The server was tested to ensure it was working properly:

![Basic Testing](<resources/Development Testing/backend/Basic Backend file set up/basic testing.png>)
![Terminal console log](<resources/Development Testing/backend/Basic Backend file set up/Screenshot 2024-07-31 at 11.28.10 AM.png>)

- Method: Start the app and go to the local link to see if the message is up.
- Passed: Server is working as expected.

#### Seeding Data

After creating some models, data was seeded to the database:

![Seeding Data](<resources/Development Testing/backend/seeddata/Screenshot 2024-08-02 at 2.10.26 PM.png>)
![Seeding Data](<resources/Development Testing/backend/seeddata/Screenshot 2024-08-02 at 2.10.33 PM.png>)

- Method: Check the terminal line to ensure the seeded data is coming up.
- Passed: Data is successfully seeded into the database.

#### Hashing Passwords

Testing the hashing of passwords:

![Hashed Data](<resources/Development Testing/backend/hashing password/frist test after code to check hasing is working.png>)

- Method: Go to the terminal to see logged data of hashed passwords.
- Passed: Passwords are hashed.

Validated hashed passwords using JWT:

![JWT Validation First Attempt](<resources/Development Testing/backend/hashing password/testing of hasing on seed data failure.png>)

- Method: Use [JWT.io](https://jwt.io) and the key to decode the data.
- Failed: JWT validation did not work.

Second Attempt:

![Hashed Data](<resources/Development Testing/backend/hashing password/terminal line code.png>)
![JWT Validation](<resources/Development Testing/backend/hashing password/jwt.to for seeddata.png>)

- Method: Check the terminal line for hashed data, and use JWT.io to validate.
- Passed: JWT validation worked.

#### Route Testing

Each route was tested locally using the Bruno API testing tool:

##### Asset Router

- **GET all assets**: Passed
  - Method: Use Bruno to test the route and verify that information comes up.
  ![Get All Assets](<resources/Development Testing/backend/route/assetrouter/asset get all.png>)
  
- **POST new asset**: Passed
  - Method: Use Bruno to test the route and create a new asset.
  ![Post New Asset](<resources/Development Testing/backend/route/assetrouter/create new asset.png>)
  
- **DELETE asset**: Passed
  - Method: Use Bruno to test the route and delete an asset.
  ![Delete Asset](<resources/Development Testing/backend/route/assetrouter/delete asset.png>)
  
- **GET asset by ID**: Passed
  - Method: Use Bruno to test the route and get one asset by ID.
  ![Get Asset By ID](<resources/Development Testing/backend/route/assetrouter/asset get all.png>)
  
- **PUT update asset**: Passed
  - Method: Use Bruno to test the route and update one asset's information.
  ![Update Asset](<resources/Development Testing/backend/route/assetrouter/update asset details by id.png>)

##### Client Router

- **POST new client**: Passed
  - Method: Use Bruno to test the route and create a new client.
  ![Post New Client](<resources/Development Testing/backend/route/client/create new client.png>)
  
- **DELETE client**: Passed
  - Method: Use Bruno to test the route and delete one client.
  ![Delete Client](<resources/Development Testing/backend/route/client/delete client.png>)
  
- **PUT update client**: Passed
  - Method: Use Bruno to test the route and update one client's information.
  ![Update Client](<resources/Development Testing/backend/route/client/edit client .png>)
  
- **GET all clients**: Passed
  - Method: Use Bruno to test the route and retrieve all clients' information.
  ![Get All Clients](<resources/Development Testing/backend/route/client/get all client.png>)
  
- **GET client by ID**: Passed
  - Method: Use Bruno to test the route and retrieve one client's information by ID.
  ![Get Client By ID](<resources/Development Testing/backend/route/client/Get client by ID.png>)

##### Operator Router

- **DELETE operator**: Passed
  - Method: Use Bruno to test the route and delete one operator's information.
  ![Delete Operator](<resources/Development Testing/backend/route/operators/Delete Operator.png>)
  
- **GET all operators**: Passed
  - Method: Use Bruno to test the route and retrieve all operators' information.
  ![Get All Operators](<resources/Development Testing/backend/route/operators/Get all operators.png>)
  
- **GET operator by ID**: Passed
  - Method: Use Bruno to test the route and retrieve one operator's information by ID.
  ![Get Operator By ID](<resources/Development Testing/backend/route/operators/get operator by id.png>)
  
- **PUT new operator**: Passed
  - Method: Use Bruno to test the route and create a new operator.
  ![Post New Operator](<resources/Development Testing/backend/route/operators/new operator.png>)
  
- **POST edit operator**: Passed
  - Method: Use Bruno to test the route and edit one operator's information.
  ![Update Operator](<resources/Development Testing/backend/route/operators/update operator details.png>)

##### User Router

- **GET user by ID**: Passed
  - Method: Use Bruno to test the route and retrieve one user's information by ID.
  ![Get User By ID]![alt text](<resources/Development Testing/backend/route/user route/local testing/userroute/Get all useres.png>)
  
- **DELETE user**: Passed
  - Method: Use Bruno to test the route and delete one user's information.
  ![Delete User](<resources/Development Testing/backend/route/user route/local testing/userroute/delete 1 user.png>)
  
- **GET all users**: Passed
  - Method: Use Bruno or go to local link to test the route and retrieve all users' information.
  ![Get All Users](<resources/Development Testing/backend/route/user route/local testing/userroute/Get all useres.png>)
  
- **PUT edit user**: Passed
  - Method: Use Bruno to test the route and update one user's information.
  ![Update User](<resources/Development Testing/backend/route/user route/local testing/userroute/update user details.png>)
  
- **POST new user**: Passed
  - Method: Use Bruno to test the route and create a new user.
  ![Post New User](<resources/Development Testing/backend/route/user route/local testing/userroute/Post new used.png>)
  
- **Login and Authentication**: Passed
  - Method: Use Bruno to test the login route and verify JWT token is provided.
  ![Login and Auth](<resources/Development Testing/backend/route/user route/loginig in.png>)

##### Allocation Router

- **POST new allocation**: Passed
  - Method: Use Bruno to test the route and create a new allocation.
  ![Post New Allocation](<resources/Development Testing/backend/route/allocations/create new allocation.png>)
  
- **DELETE allocation**: Passed
  - Method: Use Bruno to test the route and delete one allocation's information.
  ![Delete Allocation](<resources/Development Testing/backend/route/allocations/delet Allocation.png>)
  
- **PUT update allocation**: Passed
  - Method: Use Bruno to test the route and update one allocation's information.
  ![Update Allocation](<resources/Development Testing/backend/route/allocations/create new allocation.png>)
  
- **GET all allocations**: Passed
  - Method: Use Bruno to test the route and retrieve all allocations' information.
  ![Get All Allocations](<resources/Development Testing/backend/route/allocations/get all allocations.png>)
  
- **GET allocation by ID**: Passed
  - Method: Use Bruno to test the route and retrieve one allocation's information by ID.
  ![Get Allocation By ID](<resources/Development Testing/backend/route/allocations/get allocations by id.png>)

#### Error Handling Routes

Error handling was tested to ensure correct behavior:

- **Wrong client ID**: Passed
  - Method: Use Bruno to test the route with an incorrect ID and verify the correct error message is delivered.
  ![Wrong Client ID](<resources/Development Testing/backend/route/erro handling/errohandling wrong client details.png>)
  
- **Missing login details**: Passed
  - Method: Use Bruno to test the route with missing login information and verify the correct error message is delivered.
  ![Missing Login Details](<resources/Development Testing/backend/route/erro handling/error handling login.png>)
  
- **Wrong route**: Passed
  - Method: Use Bruno and local url to test a non-existent route and verify the correct error message is delivered.
  ![Wrong Route](<resources/Development Testing/backend/route/erro handling/error handling wrong route.png>)
  ![General Error Handling](<resources/Development Testing/backend/route/erro handling/general error handling.png>)

#### Backend Server Testing

Backend routes were tested after deployment to Render:

- **Backend deployed on Render**: Passed
  - Method: Deploy the backend and check the terminal log on Render to see the server message.
  ![Backend Render](<resources/Development Testing/backend/backend server testing/backend serverlive.png>)
  - Method: Go to the Render site and verify the server message is displayed.
  ![Backend Live](<resources/Development Testing/backend/backend server testing/backend server live render.png>)
  
- **Route to allocations**: Passed
  - Method: Test the deployed route by going to the allocations route.
  ![Route to Allocations](<resources/Development Testing/backend/backend server testing/backend allocations.png>)
  
- **Route to assets**: Passed
  - Method: Test the deployed route by going to the assets route.
  ![Route to Assets](<resources/Development Testing/backend/backend server testing/backend assets.png>)
  
- **Route to operators**: Passed
  - Method: Test the deployed route by going to the operators route.
  ![Route to Operators](<resources/Development Testing/backend/backend server testing/backend operators.png>)
  
- **Route to users**: Passed
  - Method: Test the deployed route by going to the users route.
  ![Route to Users](<resources/Development Testing/backend/backend server testing/backend users.png>)
  
- **Route to clients**: Passed
  - Method: Test the deployed route by going to the clients route.
  ![Route to Clients](<resources/Development Testing/backend/backend server testing/backend route to clients.png>)
  
- **Error route**: Passed
  - Method: Test the deployed route by going to a non-existent route and verify the correct error message is delivered.
  ![Error Route](<resources/Development Testing/backend/backend server testing/backend error test wrong route.png>)

## Production Testing

Product testing was conducted manually due to time constraints. Unlike the development testing phase, no screenshots were taken, and results were documented in an Excel file. Some key findings from the product testing include:

1. **Login and Authentication:**
   - **Positive Scenario:** Users were able to log in and navigate to the dashboard successfully.
   - **Negative Scenario:** When incorrect login details were entered, no error message was displayed, and the page did not change, which was identified as a fail.

2. **Sign-Up Process:**
   - **Positive Scenario:** New users could sign up and were redirected to the dashboard upon successful registration.
   - **Negative Scenario:** If a user tried to sign up with an existing email or left mandatory fields empty (e.g., company info), the form did not show an error message, and no action was taken, resulting in a fail.

3. **Navigation and UI:**
   - **Navigation:** All links in the navigation bar functioned correctly, redirecting users to the appropriate pages, and the active page was highlighted.
   - **Logo:** The logo correctly linked back to the dashboard from any page.
   - **Mobile View:** The application was tested on various screen sizes, ensuring that the UI was responsive and elements were visible and usable in mobile view.

4. **CRUD Operations:**
   - **Asset, Operator, Client, and Allocation Pages:**
     - Users were able to create, update, and delete records successfully.
     - However, creating new records with invalid data (e.g., entering text in a numeric field) did not prompt an error message, which was flagged as a fail.

5. **Error Handling:**
   - **Insufficient Error Messages:** A common issue identified was the lack of user-facing error messages when operations failed due to invalid input or missing information.

6. **User Interface (UI):**
   - **Responsiveness:** The UI was thoroughly tested on different screen sizes, and all elements adjusted well to various resolutions, particularly in mobile view.

For a detailed report on the testing, please refer to the [Product Testing Excel File](<resources/Product Testing/Product testing manual result.xlsx>).
