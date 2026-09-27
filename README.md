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

---

## 🖼️ Architecture Diagram

![AWS 3-Tier Architecture](aws-3-tier-architecture.png)

The architecture demonstrates a segmented AWS environment consisting of
public Web, private Application, and private Database tiers across
two Availability Zones.
---

## ☁️ AWS Services

The project uses the following AWS services and components:

| AWS Service / Component | Purpose |
|---|---|
| **Amazon VPC** | Provides an isolated virtual network for the application |
| **Amazon EC2** | Hosts the Windows Web and Application servers |
| **Internet Gateway** | Provides Internet connectivity to the public Web Tier |
| **Route Tables** | Controls traffic between the VPC, Internet Gateway, and subnets |
| **Security Groups** | Controls inbound and outbound traffic to EC2 instances |
| **Availability Zones** | Provides network separation across two Availability Zones |
| **Amazon RDS** | Planned database layer for the future implementation |

### EC2 Configuration

The Web Tier was deployed using:

- Windows Server 2025
- `t3.micro` instance
- IIS Web Server
- Public subnet
- Public IPv4 address

The Application Tier was deployed using:

- Windows Server 2025
- `t3.micro` instance
- Private subnet
- No public IPv4 address

### AWS Region

```text
Region: us-east-1
Region Name: US East (N. Virginia)
