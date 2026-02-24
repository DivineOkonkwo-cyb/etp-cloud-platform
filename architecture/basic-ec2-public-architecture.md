# Week 2 – Public EC2 Deployment Architecture

## Overview
This conceptual architecture illustrates a **public EC2 deployment** with minimal attack surface, security boundaries, and Zero-Trust principles. It is designed for **Free Tier testing** while following best practices.

---

## Components

### 1. VPC
- Isolated network boundary for all resources  
- CIDR: `10.0.0.0/16`  

### 2. Public Subnet
- Hosts EC2 instances accessible via the Internet  
- CIDR: `10.0.1.0/24`  
- Associated with a **public route table**  

### 3. Internet Gateway (IGW)
- Enables inbound/outbound internet connectivity for the public subnet  

### 4. Route Table
- Public route table points `0.0.0.0/0` to the Internet Gateway  
- Ensures internet reachability only for public resources  

### 5. Security Group
- Acts as a virtual firewall attached to EC2 instance  
- Example rules:
  - SSH (22) → Source: **My IP only**  
  - HTTP (80) → Source: **My IP only**  
- Restricts access to reduce exposure  

### 6. EC2 Instance
- Type: `t2.micro` (Free Tier)  
- AMI: Amazon Linux 2  
- Public IP assigned via subnet auto-assignment  
- Deployed inside public subnet  
- Protected by security group

---

## ASCII Diagram
