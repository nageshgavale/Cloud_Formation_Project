# Cloud_Formation_Project
This project uses AWS CloudFormation to automatically deploy a scalable cloud infrastructure including VPC, public and private subnets, NAT Gateway, Auto Scaling EC2 instances, Application Load Balancer, RDS MySQL database, S3 storage, and SNS alerts.

# AWS CloudFormation Infrastructure Project

This project demonstrates Infrastructure as Code using AWS CloudFormation.

The template automatically deploys a scalable cloud infrastructure including VPC, subnets, load balancer, EC2 Auto Scaling, RDS database, S3 storage, and monitoring alerts.

## Architecture

- VPC with public and private subnets
- Internet Gateway and NAT Gateway
- Application Load Balancer
- EC2 Auto Scaling Group
- Docker container deployment
- RDS MySQL database
- S3 bucket for storage
- CloudWatch and SNS alerts

## AWS Services Used

- Amazon VPC
- EC2
- Auto Scaling
- Application Load Balancer
- Amazon RDS
- Amazon S3
- CloudWatch
- SNS

## Deployment

Upload the YAML template to AWS CloudFormation and create a stack.

## Architecture of This Project
                Internet
                    |
            Internet Gateway
                    |
           Application Load Balancer
             /                \
        EC2 Instance       EC2 Instance
       (Auto Scaling)     (Auto Scaling)
             |                |
        Docker Container  Docker Container
             |
         Private Subnets
             |
           RDS MySQL
             |
           NAT Gateway
             |
           Internet
             
Other Services:
S3 Bucket (storage)
SNS (email alerts)
CloudWatch (monitoring)
