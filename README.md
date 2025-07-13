# Solution-Architect-Project
  

## 📚 Table of Contents

- [Project Overview](#project-overview)

- [AWS Environment Structure](#aws-environment-structure)

- [Architecture Diagram](#architecture-diagram)

- [Used Services](#used-services)

  - [1. EC2 Instances](#1-ec2-instances)

  - [2. Application Load Balancer (ALB)](#2-application-load-balancer-alb)

  - [3. Auto Scaling Group (ASG)](#3-auto-scaling-group-asg)

  - [4. Amazon RDS (Optional)](#4-amazon-rds-optional)

  - [5. IAM Roles](#5-iam-roles)

  - [6. CloudWatch](#6-cloudwatch)

  - [7. Simple Notification Service (SNS)](#7-simple-notification-service-sns)

- [Suggested Services](#suggested-services)

  

---

  

## 📖 Project Overview

  

This web application is hosted on **Amazon EC2 instances** behind an **Application Load Balancer**, managed by an **Auto Scaling Group**. It optionally connects to a **MySQL/PostgreSQL database on Amazon RDS**, and uses **IAM roles** for secure permissions. The infrastructure is monitored using **CloudWatch**, and critical alerts are sent via **SNS**.

  

---

  

## ☁️ AWS Environment Structure

### 1. ☁️ AWS Cloud

	Outermost where every thing is grouped under it.

### 2. 🙋🏻‍♂️ AWS Account

	Where we can access and manage our AWS resources.

### 3. 🏳️ AWS Region

	Geographical location where EC2, ALB and RDS are deployed.

---

  

## 🗺️ Architecture Diagram

  

![Architecture Diagram](./Blank%20diagram%20(7).png)

  

---

  

## 🧩 Used Services

  

### 1. 🖥️ EC2 Instances

  

- **Functionality**: Hosts the actual web application code.

- **Scalability**: Managed within an Auto Scaling Group.

  

---

  

### 2. 🌐 Application Load Balancer (ALB)

  

- **Functionality**: Distributes HTTP/HTTPS traffic across EC2 instances.

  

---

  

### 3. 📈 Auto Scaling Group (ASG)

  

- **Functionality**: Automatically adjusts the number of EC2 instances based on traffic.

- **Fault Tolerance**: Ensures application availability by replacing failed instances to stay fullfilling the demand.

  

---

  

### 4. 🗄️ Amazon RDS (Optional)

  

- **Functionality**: Provides a relational database for needed data storage.


  

---

  

### 5. 🔐 IAM Roles

  

- **Functionality**: Provide secure access to AWS services.

  

---

  

### 6. 📊 CloudWatch

  

- **Functionality**: Collects and visualizes  metrics (CPU, memory, requests).

- **Integration**: Tied to EC2, ALB, and Auto Scaling.

- **Alarms**: Used to trigger SNS notifications or scaling actions.

  

---

  

### 7. 📬 Simple Notification Service (SNS)

  

- **Functionality**: Sends alerts to email/SMS when CloudWatch alarms fire.

- **Use Case**: Alert when instances fail.

  


## 🧐 Suggested Services

### 1. Amazon VPC (Virtual Private Cloud)

**Functionality**: Make non-public resources unaccessible directly from internet 
(Private subnet & Nat Gateway for RDS).

### 2. Amazon Route 53

**Functionality**: Scalable DNS service for custom domain names & we can link it with ALB.
(Access the web app with a "www.______.com")
