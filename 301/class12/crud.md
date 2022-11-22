# CRUD

## Reading

* [Status Codes Based on REST Methods](https://www.moesif.com/blog/technical/api-design/Which-HTTP-Status-Code-To-Use-For-Every-CRUD-App/)
* [VIDEO: Build A REST API With Node.js, Express, & MongoDB - Quick](https://www.youtube.com/channel/UCFbNIlppjAuEX4znoulh0Cw)

## Questions

## Reading

* **In your own words, describe what each group of status code represents:**
  * **100’s =** Informational codes that tell the client that the request has been received
  * **200’s =** Successful request by the client
  * **300’s =** Request redirected to current location
  * **400’s =** Request not found
  * **500’s =** Server is having an issue
* **What is a status code 202?**
  * All validation requirements were met for an asynchronous request
* **What is a status code 308?**
  * Permanent Redirect: the URL has moved and the client should stop using the current URL
* **What code would you use if an update didn’t return data to a client?**
  * 204 No Content
* **What code would you use if a resource used to exist but no longer does?**
  * 410 Gone
* **What is the ‘Forbidden’ status code?**
  * 403 Forbidden: client does not have permission to access the resource

## Video

* **Why do we need to pull our MongoDB database string out of our server and put it into our .env?**
  * So that we can secure the location of our database from potential threats
* **What is middleware?**
  * Software that provides services to software applications beyond those available to the operating system
* **What does `app.use(express.json())` do?**
  * Allows our server to accept JSON data
* **What does the `/:id` mean in a route?**
  * That it is a parameter and can be accessed with `request.params.id`
* **What is the difference between `PUT` and `PATCH`?**
  * `PATCH` updates only the information that is passed
  * `PUT` updates all the information at once
* **How do you make a default value in a schema?**
  * Add `default: <defaultValue>` to the schema
* **What does a `500` error status code mean?**
  * There was a server error
* **What is the difference between a status `200` and a status `201`?**
  * 200 = "OK", request was good
  * 200 = "OK", request was successful and a resource was created as a result

## Notes

### Building an API Quick

* Steps
  1. `npm i`
  2. `npm i express mongoose`
      * Installs `express`
        * Makes interacting with Node.js easier
      * Installs `mongoose`
        * Allows us to interact with MongoDB
  3. `npm i --save-dev dotenv nodemon`
      * `dotenv` allows us to pull environmental variables from a `.env` file
      * `nodemon` allows us to update our server without needing to restart each time
  4. In `package.json`, change `devStart` to `"devStart": "nodemon server.js"`
  5. Create `server.js` file
  6. Create `.env` file
  7. Create `.gitignore`
     * Add `.env`
     * Add `node_modules`
  8. In `server.js`:
     * Import `express`
       * `const express = require('express');`
     * Declare `app` variable to configure the server
       * `const app = express();`
     * Add `listen` method to `app` to tell it what port to listen to
       * `app.listen(3000, () => console.log('Server Started'))`
     * Import `mongoose`
       * `const mongoose = require('mongoose');`
     * Connect `mongoose` to database
       * `mongoose.connect('mongodb://<dbURL>, { useNewUrlParser: true })`
     * Create `db` variable to handle events with the database
       * `const db = mongoose.connection`
     * Create error handler for database
       * `db.on('error', (error) => console.error(error))`
     * Create a proof of life that the database is connected
       * `db.once('open', () => console.log('Connected to database'))`
     * Set `DATABASE_URL` in `.env` file equal to your database URL in `mongoose.connect`
       * `DATABASE_URL=://mongodb://<dbURL>`
     * Inside `server.js` change `dbURL` to `process.env.DATABASE_URL`
     * Import `.env` variables
       * `require('dotenv').config()`
     * Setup server to accept JSON
       * `app.use(express.json())`
     * Setup routes
       * Create a `routes` folder
       * Define your routes: `const <routeName> = require('./routes/<endpointName>')`
     * You can now begin configuring routes in their own components
