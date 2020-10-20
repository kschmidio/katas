# Create a kubernetes cluster on AWS

## Prerequisites
* Have access to an AWS account
* Have `eksctl`, `kubectl` installed. If not walk through the steps [here](https://docs.aws.amazon.com/eks/latest/userguide/getting-started-eksctl.html)
* create eks cluster 
  ```
  eksctl create cluster --name dev --region eu-west-1 --fargate
  or
  eksctl create cluster --name test --region eu-west-1 --nodegroup-name linux-nodes --node-type t3.medium --nodes 3 --nodes-min 1 --nodes-max 4 --managed
  ```
* Watch out only specific regions are [supported](https://stackoverflow.com/questions/59673755/failed-to-create-fargate-profile)

## Steps
1. TODO
2. Destroy https://docs.aws.amazon.com/eks/latest/userguide/delete-cluster.html

