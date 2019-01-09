# Package with two docker images to provide easy way to management AWS resources over AWS CLI and Terraform 

Write AWS authentication infos on variables.env and ./terraform/data/deploy.tf files.
```
access_key = ""
secret_key = ""
region = ""
```

## To run:
docker-compose --verbose up -d

## Interaction examples:

To describe EC2 Instances on AWS:
docker run --rm -it aws_cli ec2 describe-instances

## To init a new deploy by Terraform:
PWD='./terraform/data'
docker run -it -v $(pwd):/data -w /data terraform init

## To make a new EC2 deploy on AWS
docker run -it -v $(pwd):/data -w /data terraform apply

## EC2 resource example:
```
resource "aws_instance" "example" {
    ami = "ami-2757f631"
    instance_type = "t2.micro"
}
```
