# Cloudformation-task

## _Prerequisite_

Aws Cli 
Docker install
node 
npm

### Run Project using Docker

Build docker image: docker build -t nodeApp .
Run docker image:  docker run -it -p 3000:3000 --rm   //you can also use -d if you want to run detached mode
Stop docker image running : docker stop <container-id>

## AWS ECR 

Create ECR Repo using AWS cli 

```sh
aws ecr create-repository --repository-name <Repo Name>
```

Docker Login command

```sh
aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin 1234567890.dkr.ecr.us-east-1.amazonaws.com
```

Tag Docker Image and Push Docker Image

```sh
docker tag nodeapp:latest 1234567890.dkr.ecr.us-east-1.amazonaws.com/nodeapp:latest

docker push 1234567890.dkr.ecr.us-east-1.amazonaws.com/nodeapp:latest
```

## AWS ECS

Creating VPC for ECS using cloudformation

```sh
aws cloudformation create-stack --stack-name vpc-ecs --template-body file://infra/vpc.yml --region us-east-2
```
Creating IAM for ECS using Cloudformation

```sh
aws cloudformation create-stack --stack-name iam-ecs --template-body file://infra/iam.yml --capabilities CAPABILITY_NAMED_IAM
```