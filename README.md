# TronSpace-NW
#### Video Demo:  < https://youtu.be/2ltchg-6oVo>
#### Description:

 Hello! This is Madhu Shantan majoring in Computer Science from SRM University, currently in my pre-final year. This Final Project for the CS50 Course that I took back in the first quarter of 2023 is TronSpace! TronSpace is a Web Application which is an authentic space to talk about the places we have experienced and visited all over the world. Let that be a restaurant, a paddock or a small shawl business in the Himalayas! When I say Tronspace or a Campground, I refer to any physical place, let that be a cafe, bar, restaurant, gaming zone or even a book store.

 A User has to first register so as to be logged inside TronSpace. You could add the tronspaces that you have visited in your life and give a review to them! This helps other people to consider going to that particular tronspace/campground. Each Tronspace has a map giving its location, helping people to navigate the campground easily right in the website! Quite cool isnt it?

 You could add multiple images into a certain campground of your own to cherish your favourite memories of that place. People could view all information of the campground you've added, that includes its location, description, the price of its experience (average price of the food/access to a place) and the images. They could also consider looking at the reviews of that particular campground. One could edit his/her own campground information after creating one, they cannot edit other campgrounds!

 I've created Tronspace in hope of making it easier for the people in my friend group and family, so as they could look at the recommendations of various places among the friends and keep a look at where they have visited! This could create a fun interactive engagement between each other and let everyone keep updated about others as most of my friends live in different cities for their Undergrad. Everyone could keep a tab on all the reviews of Tronspaces of their friends and visit that particular campground if they had to visit that particular city later.

### Technologies/Softwares Used:
 The FrontEnd Technologies i've used to make this project include Node.js, EJS Template Engine, JavaScript, HTML & CSS.
 The BackEnd Technologies include Nodejs, Express.js and MongoDB Database. I've used [Cloudinary](https://cloudinary.com/developers) for storing and uploading the images and videos uploaded by various people. I have also used [Unsplash](https://unsplash.com/) to use images for my website. For example, if anyone submitted a campground without any images included, a default images gets added. That image in Tronspace is [Default Image](https://images.unsplash.com/photo-1512594282804-b5f400408c9d?q=80&w=2940&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D).
 The Location Technology used to display the geo-map marking all the tronspaces is [MapBox](https://www.mapbox.com/) and [MapBox GL JS](https://docs.mapbox.com/mapbox-gl-js/guides/). Mapbox GL JS is a client-side JavaScript library for building web maps and web applications with Mapbox's modern mapping technology. I've used the default Access Token which is given after logging into mapbox.

 The Website has a Home Page, A Page containing all the TronSpaces, A Page to add a new TronSpace, a login, register and Edit Tronspace Page.
 The CodeBase includes 10 folders, several files inside them and 7 other files apart from the first ten folders mentioned above. They are:

 * __.vscode__: This directory is used to store configuration settings for Visual Studio Code. It contains a settings.json file which allows you to customize the behavior of VSCode for a particular workspace or project.

 * **cloudinary**/index.js: The code sets up Cloudinary, a cloud-based media management service, for my Node.js application. It configures Cloudinary with authentication credentials, establishes storage settings for file uploads (defining a target folder and allowed formats), and exports the configured Cloudinary instance and storage parameters for use in handling media uploads within TronSpace.

 * **Controllers**: Includes three files, they are
     - __campgrounds.js__ - The Node.js and Express.js code defines controller functions for managing campgrounds in a web application. It includes functionality for rendering a list of campgrounds, displaying details of a single campground, creating new campgrounds with location data, editing campground information, updating images, and deleting campgrounds. The code integrates with Mapbox for geocoding location data and Cloudinary for managing images associated with campgrounds. Additionally, it handles rendering views for creating, editing, and displaying campground information, and it uses flash messages to provide user feedback.

     - __reviews.js__- The createReview function adds a new review to a specific campground, associating it with the logged-in user. The deleteReview function removes a review from a campground, updating both the campground's reviews array and deleting the review itself.

     -  __users.js__ - The renderRegister and renderLogin functions render registration and login forms, respectively. The register function handles user registration, creating a new user with provided credentials, and logging them in. The login function handles user login, flashing a welcome message and redirecting to the previous page. The logout function logs the user out, displaying a goodbye message and redirecting to the campgrounds page.

 * **models**: This does include three files too,
     - __campground.js__ - This defines a MongoDB schema for campgrounds in TronSpace using Mongoose. The schema includes fields for title, images, geographical coordinates, price, description, location, author, and associated reviews. It also incorporates a virtual property for generating a thumbnail image URL, a virtual property for creating pop-up markup for map markers, and a post-hook to delete associated reviews when a campground is deleted. The schema is exported as the 'Campground' model.

     -  __review.js__- The schema includes fields for the review body, rating, popup text, and a reference to the author, who is associated with the 'User' model. The schema is exported as the 'Review' model for use in the application's data structure, allowing reviews to be stored and retrieved in the MongoDB database.

     -  __user.js__ -The schema includes an email field with constraints for uniqueness and requirement. The schema is enhanced with the passportLocalMongoose plugin, which simplifies the integration of local authentication strategies (username and password) with Passport.js. The resulting 'User' model is exported for use in handling user authentication within the application.

- __node_modules__: This folder stores the actual code of the installed packages, as well as any nested dependencies they may have.

- __public__:

     - *javascripts*:

        - clusterMap.js: This JavaScript code uses the Mapbox GL JS library to create an interactive map for displaying campgrounds. It clusters map markers to improve performance at lower zoom levels. The clusters represent groups of campgrounds, and the code defines the visual appearance of these clusters based on the number of campgrounds within each cluster. Additionally, it handles pop-up interactions for both clusters and individual campgrounds when clicked, providing an engaging user experience.

        - showPageMap.js: adds a navigation control, and places a marker on the map with a popup displaying the campground's title and location.

        - validateForms.js: This applies custom validation styles to forms with the class 'validated-form', and prevents form submission if the form is not valid.

     - *stylesheets*:

        - app.css: css code for app.
        - home.css: css code for home page.
        - stars.css: css code for star ratings!

- __routes__: This folder consists of three files, they are
     - __campgrounds.js__ - This file defines routes for campgrounds using the Express.js framework. It includes routes for displaying a list of campgrounds, creating a new campground, viewing a specific campground, updating and deleting campgrounds. The code utilizes middleware for user authentication, authorization, form validation, and image uploads. Additionally, it integrates Cloudinary for image storage.

     - __reviews.js__- It includes a route to create a new review associated with a campground and another route to delete a specific review. The code incorporates middleware for user authentication, review validation, and authorization checks.

     -  __users.js__ - It includes routes for user registration, login, and logout. The registration route renders a form for user registration and handles the registration process. The login route renders a login form and authenticates users using Passport.js. The logout route logs out the authenticated user.

* **seeds**:
     - __cities.js__: Contains a few cities with their information

     - __index.js__: This connects to a MongoDB database using Mongoose and seeds it with 300 campground entries. Each entry is generated with random data, including location, title, description, price, and images. The seed data is used for testing a YelpCamp web application. The code also includes cloudinary URLs for images and closes the database connection after the seeding process.

     - __seedHelpers__: contains adjectives and nouns for tronspaces.

* **utils**: Contains various utility modules or functions that provide common and reusable functionalities used across different parts of Tronspace.

      - __catchAsync.js__: This module exports a higher-order function that wraps an asynchronous function to handle promise rejections and pass errors to Express's next middleware.

      - __Expresserror.js__: This module defines an ExpressError class, extending the native Error class, to handle custom error messages and HTTP status codes in Express applications.

* **views**: This contains 4 folders (with files inside them) and 2 ejs files:

  - **campgrounds**:

     - *edit.ejs*: This is an HTML template for editing a particular campground . It uses embedded JavaScript (EJS) to dynamically render the form with existing campground data and provides the ability to update details such as Campground price, description, price , including uploading images and deleting existing ones.

     - *index.ejs*: It generates cards for each campground, including details such as title, description, and location. The template also includes a script to initialize a map with the campgrounds' locations using Mapbox, and it passes the campground data to a JavaScript file for clustering and mapping functionality.

     - *new.ejs*: It includes a form with fields for entering a new campground's title, location, price, description, and images. The form uses Bootstrap styles for a clean and responsive layout. Users can submit the form to add a new campground, and a link is provided to navigate back to the page displaying all campgrounds.

     - *show.ejs*: It includes a Bootstrap carousel to showcase images of the campground, a card section providing details such as title, description, location, author, and price. Users, if authenticated, can leave reviews, including a star rating. Additionally, a map is displayed, and campground reviews are listed, with the option for the author to edit or delete their own reviews.

  - **layouts**:

     - *boilerplate.ejs*: This file serves as a template for the overall structure and layout of web pages in an EJS (Embedded JavaScript) application. It contains the common HTML structure, including the head section with meta tags, stylesheets, and scripts, as well as the body section where the dynamic content is injected using EJS syntax.

  - **partials**:

     - *flash.ejs*: This file is a template for displaying flash messages. It includes conditional blocks to show success and error messages in styled alert boxes. If there is a success message, it generates a green alert; if there is an error message, it generates a red alert. The alerts are dismissible and feature a close button for a user-friendly experience. The messages are dynamically inserted using EJS syntax.

     - *footer.ejs*: HTML template that uses EJS for the footer of the website.

     - *navbar.ejs*: HTML template that uses EJS for the navbar of the website.

  - **users**:

    - *login.ejs*: HTML template that uses EJS for login page.
    - *register.ejs*: HTML template that uses EJS for register page.

  - **error.ejs**:  HTML template that uses EJS for an error form/page.

  - **home.ejs**: HTML template that uses EJS for the Home Page of TronSpace.

* **.env**: It stores environment variables, it stores the MAPBOX_TOKEN here. I inserted my default mapbpx token here.

* **.gitignore**: contains node_modules and .env files.

* **app.js**: This file is the main entry point for our Tronspace web application built using Express.js, MongoDB, and other related technologies. It begins by checking if the environment is not set to "production" and, if true, loads environment variables from a .env file using the dotenv module. The file sets up an Express application, establishes a connection to a MongoDB database, and configures various middleware such as session management, security headers using Helmet, and sanitization to prevent MongoDB injection attacks. It also configures authentication using Passport.js with a local strategy, sets up routes for users, campgrounds, and reviews, and handles errors. The content security policy is implemented for enhanced security. The application serves views using the EJS templating engine and starts the server on a specified port, either from the environment or a default of 3000.

* **middleware.js**: This code exports a set of middleware functions used in our web application. The functions handle user authentication, campground and review data validation, authorization checks for campground and review ownership, and storing the user's return path after authentication. They are employed as middleware in route handlers to ensure users are logged in, validate input data, check ownership, and manage the return path for a smoother user experience.

* **schemas.js**: This code defines Joi validation schemas for the campground and review data. It uses the Joi library to create structured validation rules, ensuring that the input data adheres to specific criteria. Additionally, it extends Joi's functionality by adding a custom rule, 'escapeHTML', which sanitizes input strings to prevent HTML injection, enhancing security by disallowing HTML content in user input for titles, prices, locations, descriptions, ratings, and review bodies.

I've wanted to use React for the frontend as I have heard it is pretty easy but since my brother recommended me ejs for this project, i've learned and used ejs for this project. Glad I did use this technology.

***This is the End of describing all the files from the Code base***

> I've put around 4-5 months in completing this project, learning to use various technologies and frameworks subsequently. I'm proud for this to be my first Project of my Software Tech journey. Glad I started with Full Stack Development! I've enjoyed the whole CS50 course and yes, there were days i wanted to quit but glad I completed it finally before the due date. Moving on with a lot of knowledge and hands on experience, I thank everyone from CS50 for letting me a part of this wonderful opportunity! I'll miss this Codespace.
