# Steps

1. Create EC2 Instance. Choose Amazon Linux 2 AMI.
2. When up and running ssh into the instance
3. install and start docker
   ```
   sudo yum update -y
   sudo amazon-linux-extras install docker
   sudo service docker start
   sudo docker info
   optional sudo usermod -a -G docker ec2-user
   ```
4. install nvm and node on instance
   ```
   curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.34.0/install.sh | bash
   . ~/.nvm/nvm.sh
   nvm install node
   node -e "console.log('Running Node.js ' + process.version)"
   ```
5. create image from running instance