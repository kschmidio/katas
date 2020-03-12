# Hello World node

## Prerequisites
* Have node installed

## Steps

1. create node app
   ```
   npm init -y
   npm i -s express
   touch server.js
   ```
   create simple express server by adding the following lines to `server.js`
   ```
   const express = require("express");
   const app = express();
   app.get("/", function(req,res){
     res.send("Hi There. Your id is " + req.query.id);
   });
   const port = 8080;
   app.listen(port, function () {
     console.log("Listening on port 8080!")
   })
   ```
2. start node app `node server.js`
3. open local browser `localhost:8080`