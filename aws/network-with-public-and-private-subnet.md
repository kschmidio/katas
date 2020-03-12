# Create VPC with public and private subnet

## Prerequisites
* Have access to an AWS account
* Have an understanding of VPC sizing. A refresher can be found [here](https://aws.amazon.com/answers/networking/aws-single-vpc-design/).
* In case you want to refresh how to set private and public subnets read [this](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Scenario2.html#VPC_Scenario2_Implementation).
* [ssh agent forwarding](https://aws.amazon.com/blogs/security/securely-connect-to-linux-instances-running-in-a-private-amazon-vpc/)
## Steps
1. create a new VPC
2. create 2 subnets in this VPC
3. create Internet Gateway
4. create NAT Gateway
5. create and adjust the route tables
6. launch ec2 instance in the public subnet
7. launch ec2 instance in the private subnet
8. ssh into the public instance
9. ssh into the private instance from the public instance and test if you can reach the internet
10. make sure that you have 2 subnet, the public one is reachable from the internet and the private one only has access to the internet, but cannot be reached from the internet