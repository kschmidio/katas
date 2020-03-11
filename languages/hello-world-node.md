# Prerequisites
* Have node installed

# Steps

1. create node app
   ```
   npm init -y
   npm i -s express
   touch app.js
   ```
   create simple express server by adding the following lines to app.js
   ```
   const express = require("express");
   const app = express();
   app.get("/", function(req,res){
     res.send("Hi There");
   });
   const port = 8080;
   app.listen(port, function () {
     console.log("Listening on port 8080!")
   })
   ```
2. start node app `node app.js`
3. open local browser `localhost:8080`