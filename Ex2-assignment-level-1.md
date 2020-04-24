## BLOCK-readText

#### Timeline for the entire topic - 3 hours.

In this topic, you have to build a small web API from scratch for the following user stories.

*Note - This is not fullstack application, you only have to build the API using Node.js, Express.js and MongoDB. Please follow standard web practices.*

```
1. There are two kinds of users in our system 
  - students
  - mentors
2. A student should be able to signup using following information.
  - Name, Email Id, Password, Batch Number.
3. A student should be able to login using his/her email id and password.
4. Atleast 3 mentors should be automatically seeded into the database and so they don't have to signup. Mentor data should be seeded with the following information.
  - Name, Email Id, Password.
5. A mentor should be able to login using email and password.
6. The identification route for both the types of users has to be the same.
7. A mentor should be able to add a task in a resource called `Todo` with following info.
  - Name of todo, Whether its completed or not.
8. A mentor should be able to see all the tasks.
9. A student should be able to see all the tasks but should not be able to add a new task.
```

## BLOCK-writeTextAnswer

Here write the psuedo code you would follow to build the above API.

-   create a new folder and call it API or as required.
    $ mkdir API
$ cd API
-   creating a package.json file using command "npm init" so that we can add package name, author name, License....
    \$ npm init
-   now we will add express or setup express to it using following command
    $ express -help
or
$ express --no-view
-   now we need to install all dependencies by using "npm i"
    \$ npm i
-   now we can check using it's is working or not using "npm start"
    \$ npm start
-   now we need to connect it to Mongo DB so we will install mongoose
    \$ npm install mongoose --save
-   now we can import mongoose into app.js
    // Import Mongoose
    let mongoose = require('mongoose');
-   now we will connect it to mongo db
    // mongodb connection
    mongoose.connect('mongodb://localhost/resthub', { useNewUrlParser: true,useUnifiedTopology:true},
    err =>{
    console.log(err ? err : "Database connected")
    });
-   now we will create all api endpoint hall be defined in this folder
    $ cd routes
$ mkdir api
    $ touch mentors.js studemts.js
$ cd ..

-   now we will require routes in app.js
    // Require Routes file
    var mentorsRouter = require('./routes/api/mentors');
    var studentsRouter = require('./routes/api/students');

// Use All Routes
app.use('/api/v1/mentors', mentorsRouter);
app.use('/api/v1/students', studentsRouter);

-   now we will write code for endpoints
-   then we will create model as per data required
    $ mkdir models
$ touch mentors.js students.js tasks.js
-   for securing the password we can install bcrypt
    \$ npm i bcryptjs
-   now we can create Schema as per required in models
-   now we can add authentication as per required
