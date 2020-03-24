# Setup cognito with loadbalancer

## Prerequisites
* Have access to an AWS account
* Here is a [video](https://www.youtube.com/watch?v=cAEtjMI1KcQ) that explains the whole setup
* [Cognito Endpoints](https://docs.aws.amazon.com/cognito/latest/developerguide/token-endpoint.html)

## Steps
1. launch ami with docker and node installed
2. create [node application](../languages/hello-world-node.md)
3. create a application loadbalancer that routes traffic to the node app
4. check security groups and limit access as far as possible
5. check if you can reach the app via your local browser
6. create a user pool with cognito
7. wire the loadbalander with cognito
8. check if you can know see the sign up / sign up page from cognito when calling your app
9. try to get a valid token with curl
   ```
   call with browser
   https://<DOMAIN>.auth.<REGION>.amazoncognito.com/oauth2/authorize?response_type=code&client_id=<CLIENT_ID>&redirect_uri=<REDIRECT_URL>&state=STATE&scope=openid+profile+aws.cognito.signin.user.admin
   
   use the code token to recieve valid tokens
   curl -d "grant_type=authorization_code&redirect_uri=<REDIRECT_URL>&code=<CODE>" -H "Authorization: Basic <ENCODED_CLIENTID_CLIENTSECRET" -H "Content-Type: application/x-www-form-urlencoded" -X POST https://<DOMAIN>.auth.<REGION>.amazoncognito.com/oauth2/token
   ```