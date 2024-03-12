# github-3.5-angkokbeng

## step-by-step how to create an image until it will be deployed to AWS ECR

1. Retrieve an authentication token and authenticate your Docker client to your registry.

Use the AWS CLI: aws ecr get-login-password --region ap-southeast-1 | docker login --username AWS --password-stdin 255945442255.dkr.ecr.ap-southeast-1.amazonaws.com


2. Build your Docker image using the following command

docker build -t akb-private-ecr .


3. After the build completes, tag your image so you can push the image to this repository:

docker tag akb-private-ecr:latest 255945442255.dkr.ecr.ap-southeast-1.amazonaws.com/akb-private-ecr:latest

4. Run the following command to push this image to your newly created AWS repository:

docker push 255945442255.dkr.ecr.ap-southeast-1.amazonaws.com/akb-private-ecr:latest
