# AWS 3-Tier VPC Architecture

## 📌 Project Overview

This project demonstrates the design and implementation of a secure
3-tier application architecture on Amazon Web Services (AWS).

The architecture separates the application into three logical tiers:

- **Web Tier** – Public-facing web server
- **Application Tier** – Private application server
- **Database Tier** – Private database layer

The infrastructure was designed using Amazon VPC, subnets,
Internet Gateway, route tables, security groups, and Amazon EC2.

---

## 🎯 Project Objective

The objective of this project is to demonstrate how a real-world
application can be deployed on AWS using:

- Network segmentation
- Public and private subnets
- Controlled communication between application tiers
- Security-group based access control
- Availability Zone separation
- Internet Gateway connectivity

---

## 🏗️ Architecture

The high-level architecture follows this traffic flow:

```text
Internet
   │
   ▼
Internet Gateway
   │
   ▼
Public Web Tier
Windows EC2 + IIS
   │
   │ TCP 8080
   ▼
Private Application Tier
Windows EC2
   │
   │ TCP 3306
   ▼
Private Database Tier
Amazon RDS MySQL
