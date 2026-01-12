

---

# 🌐 Scalable Web Application on AWS with ALB & Auto Scaling
---
## 📑 Table of Contents

* [📌 Project Overview](#-project-overview)
* [🏗️ Architecture Overview](#️-architecture-overview)

   * [📐 Architecture Diagram](#-architecture-diagram)
   * [🏛️ AWS Well Architected Pillars](#-aws-well-architected-pillars)

* [☁️ AWS Services Used](#️-aws-services-used)

  * [🖥️ Amazon EC2]
  * [⚖️ Application Load Balancer (ALB)]
  * [📈 Auto Scaling Group (ASG)]
  * [🗄️ Amazon RDS )]
  * [🔐 AWS IAM]
  * [📊 Amazon CloudWatch & SNS]
* [🚀 Deployment Steps](#-deployment-steps)
* [🎯 Key Features](#-key-features)
* [📎 Notes](#-notes)
* [✅ Conclusion](#-conclusion)

---


## 📌 Project Overview

This project demonstrates how to deploy a **highly available, scalable web application** on **AWS** using an **EC2-based architecture**. It leverages **Application Load Balancer (ALB)** and **Auto Scaling Groups (ASG)** to automatically distribute traffic and scale compute resources based on demand.

The architecture follows AWS best practices for **availability, scalability, security, and cost efficiency**, making it suitable for learning, experimentation, and professional portfolios.

---

## 🏗️ Architecture Overview

The system is designed to ensure **fault tolerance and elasticity** by distributing resources across multiple Availability Zones and using managed AWS services.

**High-Level Flow:**

1. Users send requests to the **Application Load Balancer (ALB)**
2. ALB routes traffic to healthy **EC2 instances** in the Auto Scaling Group
3. Auto Scaling dynamically adjusts capacity based on demand
4. (Optional) EC2 instances communicate with **Amazon RDS**
5. **CloudWatch** monitors performance and triggers alerts via **SNS**

```
Users → ALB → EC2 (ASG) → (Optional) RDS
```

---

### 📐 Architecture Diagram

Below is a visual representation of the system architecture:

![Architecture Diagram](./architecture-diagram.png)


---


### 🏛️ AWS Well Architected Pillars

This project follows the core principles of the AWS Well-Architected Framework:

- **Operational Excellence**: CloudWatch monitoring and alarms are used to observe system health and automate responses.
- **Security**: IAM roles with least-privilege access and security groups protect infrastructure components.
- **Reliability**: Multi-AZ deployment with Auto Scaling ensures high availability and fault tolerance.
- **Performance Efficiency**: Application Load Balancer and Auto Scaling dynamically handle traffic fluctuations.
- **Cost Optimization**: Auto Scaling and right-sized EC2 instances help minimize unnecessary costs.


---

## ☁️ AWS Services Used

### 🖥️ Amazon EC2

* Hosts the web application
* Launched using a Launch Template
* Deployed across multiple Availability Zones

### ⚖️ Application Load Balancer (ALB)

* Distributes incoming HTTP/HTTPS traffic
* Performs health checks on EC2 instances
* Improves availability and fault tolerance

### 📈 Auto Scaling Group (ASG)

* Automatically scales EC2 instances based on demand
* Maintains desired capacity for performance and reliability
* Helps optimize infrastructure costs

### 🗄️ Amazon RDS (Optional)

* Managed MySQL or PostgreSQL database
* Multi-AZ deployment for high availability
* Automated backups and maintenance

### 🔐 AWS IAM

* Role-based access control for EC2 instances
* Implements least-privilege permissions

### 📊 Amazon CloudWatch & SNS

* Collects metrics and logs
* Creates alarms for resource thresholds
* Sends notifications via SNS

---

## 🚀 Deployment Steps
    This section outlines the steps required to deploy the application and provision the necessary AWS resources.


1️⃣ **Create IAM Roles**

* Create an IAM role for EC2
* Attach required policies (SSM, CloudWatch)
* Apply least-privilege principles

2️⃣ **Prepare the Web Application**

* Build a simple web app (HTML, Flask, or Node.js)
* Configure it to listen on port **80** or **8080**

3️⃣ **Create a Launch Template**

* Choose Amazon Linux 2 AMI
* Select instance type (e.g., `t2.micro`)
* Attach IAM role and security groups
* Add User Data to install and start the app

4️⃣ **Configure Auto Scaling Group**

* Deploy across multiple Availability Zones
* Set minimum, desired, and maximum capacity
* Configure scaling policies based on CPU utilization

5️⃣ **Set Up Application Load Balancer**

* Create an ALB in public subnets
* Configure a target group
* Register the ASG with the target group
* Enable health checks

6️⃣ **(Optional) Configure Amazon RDS**

* Create a MySQL or PostgreSQL database
* Enable Multi-AZ
* Update security groups for database access

7️⃣ **Enable Monitoring and Alerts**

* Enable CloudWatch metrics and logs
* Create alarms for CPU usage and instance health
* Configure SNS notifications

8️⃣ **Test the Deployment**

* Access the application using the ALB DNS name
* Simulate traffic to verify Auto Scaling behavior
* Confirm health checks and alarms

---

## 🎯 Key Features

* ✅ High availability across multiple Availability Zones
* ✅ Automatic scaling based on traffic demand
* ✅ Load-balanced web traffic
* ✅ Secure IAM role-based access
* ✅ Centralized monitoring and alerting

---

## 📎 Notes

This project is designed to be **cost-conscious** and suitable for learning or portfolio purposes. Optional components such as Amazon RDS can be omitted to minimize AWS costs.

---

## ✅ Conclusion

This project demonstrates a **production-ready, scalable AWS web architecture** using EC2, Application Load Balancer, and Auto Scaling Groups. It highlights how to design, deploy, and monitor a highly available system while adhering to AWS best practices for reliability, security, and cost optimization.

It serves as a strong foundation for more advanced cloud architectures and is well-suited for **hands-on learning and professional portfolios** 🚀

---






---


---



