# Create a serverless app

## Prerequisites
* Have access to an AWS account
* Have the framework [serverless](https://serverless.com/) installed

## Steps
1. run `sls` and create an aws nodejs app
2. change `serverless.yml` and add an event to the functions section
   ```
   events:
     - http:
         path: hello
         method: get
  ```
3. `sls deploy`
4. check if the app has been deployed successfully
5. open local browser and call the endpoint 