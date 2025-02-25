# Re-architecting Web App on AWS Cloud

## Overview
This project demonstrates how to re-architect a multi-tier application (VProfile) on AWS using Elastic Beanstalk, RDS, ElastiCache, Amazon MQ, and CloudFront.

## Architecture
![AWS Architecture](screenshots/aws-architecture.png)

## Steps to Set Up
1. **Provision AWS Resources**:
   - Use Terraform to provision Elastic Beanstalk, RDS, ElastiCache, and Amazon MQ.
2. **Initialize RDS Database**:
   - Run the `initialize-rds.sh` script to set up the database.
3. **Deploy Application Artifact**:
   - Use the `deploy-artifact.sh` script to deploy the application to Elastic Beanstalk.
4. **Configure CloudFront**:
   - Set up a CloudFront distribution for content delivery.

## Project Structure
aws-rearchitect-webapp/
├── scripts/
├── screenshots/
├── README.md
