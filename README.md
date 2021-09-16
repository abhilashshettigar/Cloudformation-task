## Cloudformation-task

# _Prerequisite_

Aws Cli 
Docker install
node 
npm

# Run Project using Docker

Build docker image: docker build -t nodeApp .
Run docker image:  docker run -it -p 3000:3000 --rm   //you can also use -d if you want to run detached mode
Stop docker image running : docker stop <container-id>


Create ECR Repo using AWS cli 

aws ecr create-repository --repository-name <Repo Name>

Docker Login command

aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin 1234567890.dkr.ecr.us-east-1.amazonaws.com

Tag Docker Image and Push Docker Image

docker tag nodeapp:latest 1234567890.dkr.ecr.us-east-1.amazonaws.com/nodeapp:latest

docker push 1234567890.dkr.ecr.us-east-1.amazonaws.com/nodeapp:latest