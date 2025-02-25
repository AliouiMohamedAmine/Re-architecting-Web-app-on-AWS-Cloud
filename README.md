# Re-architecting Web App on AWS Cloud

## Overview
This project focuses on rearchitecting or refactoring application services using **AWS-managed services**. The goal is to replace traditional infrastructure or EC2-based deployments with **Platform as a Service (PaaS)** and **Software as a Service (SaaS)** offerings provided by AWS. By adopting this approach, we aim to improve business agility, scalability, and operational efficiency while reducing costs and management overhead.

The project transitions from a "lift and shift" strategy to leveraging AWS-managed services like **Elastic Beanstalk**, **Amazon RDS**, **Elastic Cache**, **Amazon MQ**, **Route 53**, and **CloudFront**. The architecture enables seamless scaling, better performance, and a pay-as-you-go model while minimizing administrative tasks.

---

## Key Objectives
- **Flexible Infrastructure**: Use AWS-managed services for scalability and ease of management.
- **Pay-as-You-Go Model**: Optimize costs by leveraging AWS's pricing model.
- **Automation**: Implement infrastructure as code and automate scaling and monitoring.
- **Global Reach**: Use **CloudFront** for content delivery to a global audience.

---

## Architecture Overview
The architecture for this project involves the following components:

### Frontend
- **CloudFront**: For global caching and content delivery.
- **Route 53**: For DNS resolution.
- **Elastic Load Balancer**: Managed by Elastic Beanstalk.
- **S3 Bucket**: For storing application artifacts.

### Backend
- **Amazon RDS**: Relational database service.
- **Elastic Cache**: Redis for caching.
- **Amazon MQ**: For message queuing.

### Monitoring and Automation
- **Auto-scaling**: Managed by Elastic Beanstalk.



## Execution Flow
1. The user accesses the application URL via **Route 53**, resolving to the **CloudFront** endpoint.
2. **CloudFront** forwards the request to an **Elastic Load Balancer** in the Beanstalk environment.
3. The load balancer forwards requests to **EC2 instances** managed by **Elastic Beanstalk**.
4. Backend services like **RDS**, **Elastic Cache**, and **Amazon MQ** process application data.

---

## AWS Services Used
- **Elastic Beanstalk**: For managing web servers and auto-scaling.
- **Amazon RDS**: For database services.
- **Elastic Cache**: For caching services.
- **Amazon MQ**: For message queuing.
- **Route 53**: For DNS management.
- **CloudFront**: For Content Delivery Network (CDN).
- **S3**: For storing artifacts.
- **IAM**: For identity and access management.
- **ACM**: For SSL certificates.

---

## Tools and Environments Used
- **Development and Build Tools**:
  - Maven or Gradle: For building the application artifacts.
- **Domain Management**:
  - GoDaddy: For domain setup and DNS entries.

---

## Project Walkthrough

### 1. Setting Up the Environment
- Log in to the AWS Console and create a **key pair** for secure access.
- Set up a **security group** for backend services like **Elastic Cache**, **RDS**, and **Amazon MQ**.
- Create individual backend services (**RDS**, **Elastic Cache**, **Amazon MQ**).

### 2. Setting Up Elastic Beanstalk
- Launch an **Elastic Beanstalk** environment to host the application.
- Allow traffic between Beanstalk's security group and backend services.

### 3. Backend Initialization
- Use an **EC2 instance** to initialize the **RDS database** by logging in via MySQL.

### 4. Deploying the Application
- Configure application properties with the endpoints for **RDS**, **Amazon MQ**, and **Elastic Cache**.
- Build and deploy the application artifact to the **Elastic Beanstalk** environment.
- Configure health checks and HTTPS listeners for the **Elastic Load Balancer**.

### 5. Content Delivery Network
- Set up **CloudFront** with an SSL certificate for secure connections.
- Integrate the application with **Route 53** or **GoDaddy** for domain name resolution.

### 6. Testing the Application
- Access the application via a browser and inspect the connection to verify **CloudFront** integration.
- Test application performance, scaling, and operational efficiency.

### 7. Cleanup
- Delete all unused AWS resources (**CloudFront**, **RDS**, **Elastic Cache**, **Amazon MQ**, **Elastic Beanstalk**) to prevent unnecessary charges.

---

## Project Structure
aws-rearchitect-webapp/
├── scripts/ # Scripts for initializing RDS and deploying artifacts
├── screenshots/ # Screenshots of AWS architecture and setup
├── README.md # Project documentation
