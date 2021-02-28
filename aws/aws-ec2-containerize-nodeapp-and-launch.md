# Containerize nodeapp

## Prerequisites
* Have access to an AWS account
* Completed Kata [Access website hosted on ec2 instance through ssh tunnel](access-ec2-website-through-ssh-tunnel.md)
* Completed Kata [Create AMI with docker and node](create-ami-with-docker-node.md)
* Completed Kata [Hello World node](../languages/hello-world-node.mdhello-world-node.md)
## Steps
1. launch ami with docker and node installed
2. create [Hello World node](../languages/hello-world-node.md)
3. create [dockerfile](https://nodejs.org/de/docs/guides/nodejs-docker-webapp/)
4. build docker image `docker build -t <your username>/node-web-app .`
5. run `docker images`, you should know see your image
6. start and test the containerized node app 
   ```
   docker run -p 3000:8080 -d <your username>/node-web-app
   docker ps
   docker logs <container id>
   docker exec -it <container id> /bin/bash
   curl -i localhost:3000
   ```