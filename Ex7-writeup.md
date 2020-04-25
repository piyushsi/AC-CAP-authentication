## BLOCK-writeTextAnswer

Write a detailed article here about authentication and authorization. It should include all these at minimum -

- The flow of authentication along with code samples.
- The best practices to be kept in mind while doing authentication.
- Difference between authorization and authentication.
- Difference between cookies/sessions and JWT. Write about their pros and cons as well.

Flow of Authentication 

Create a new folder and call it API or as required. 
$ mkdir API $ cd API

Creating a package.json file using command "npm init" so that we can add package name, author name, License....
 $ npm init

Now we will add express or setup express to it using the following command.
$ express -help
 Or
 $ express --no-view

Now we need to install all dependencies by using "npm i".
$ npm i

Now we can check using it's is working or not using "npm start" .
$ npm start

Now we need to connect it to Mongo DB so we will install mongoose.
 $ npm install mongoose --save

Now we can import mongoose into app.js
 // Import Mongoose let mongoose = require('mongoose');

Now we will connect it to mongo db.
 // mongodb connection mongoose.connect('mongodb://localhost/resthub', { useNewUrlParser: true,useUnifiedTopology:true}, err =>{ console.log(err ? err : "Database connected") });

Now we will create all api endpoint shall be defined in this folder.
 $ cd routes
 $ mkdir api 
$ touch mentors.js studemts.js 
$ cd ..

Now we will require routes in app.js
 // Require Routes file
 var mentorsRouter = require('./routes/api/mentors'); 
var studentsRouter = require('./routes/api/students');

// Use All Routes 
app.use('/api/v1/mentors', mentorsRouter); 
app.use('/api/v1/students', studentsRouter);

Now we will write code for endpoints
Then we will create model as per data required 
$ mkdir models 
$ touch mentors.js students.js tasks.js
For securing the password we can install bcrypt 
$ npm i bcryptjs
Now we can create Schema as per required in models.
Now we can add authentication as per required.


Authentication 
- Validating your credentials.
- Methods
  -Login Form
  -HTTP Authentication
  -HTTP DIgest
  -X.509 Certificates

Authorization
- It occurs after your identity is successfully authenticated by the system.
- Methods
  -Access controls for URLs
  -Secure Object and Methods
  -ACL i.e. Access Control Lists

JSON Web Token (JWT) is an open standard (RFC 7519) that defines a compact and self-contained way to securely transmit information between parties as a JSON Object.

In Sessions, If the credentials are valid, the server responds with a cookie, which is set on the user’s browser and includes a SESSION ID to identify the user. The user sessions are stored in memory either via files or in the database on the server. 
