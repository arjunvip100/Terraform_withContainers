Create a repo in aws ECR name - > django-app

IMPORTANT - Once the repo is create change the 600735812827.dkr.ecr.us-west-1.amazonaws.com BELOW VALUES IN COMMANDS TO THE REPO OF YOURS


aws ecr get-login-password --region us-west-1 | docker login --username AWS --password-stdin 600735812827.dkr.ecr.us-west-1.amazonaws.com


cd app/


docker build -t 600735812827.dkr.ecr.us-west-1.amazonaws.com/django-app:latest . 


docker push 600735812827.dkr.ecr.us-west-1.amazonaws.com/django-app:latest

Change the docker_image_url_django in VARIABLES.TF file with your current repo name 


Change the file paths in iam.tf and variables.tf file

Go to terraform folder and hit this below command 

ssh-keygen -f california-region-key-pair


terraform init 


terraform plan -out terraform.out


terraform apply "terraform.out"






pip install boto3 click


export AWS_ACCESS_KEY_ID="" 


export AWS_SECRET_ACCESS_KEY="" 


export AWS_DEFAULT_REGION="us-west-1" 


python update-ecs.py --cluster=production-cluster --service=production-service


terraform destroy

Result vy ALB :
![The install worked successfully! Congratulations! - Brave 1_8_2023 5_20_24 PM](https://user-images.githubusercontent.com/106534507/211194626-fbe790fe-f4de-4f27-9357-1adf51cb80db.png)

