# Terraform AWS VPC with Public/Private Subnets and EC2 Instances

## 📦 Project Overview

This project provisions a custom **AWS Virtual Private Cloud (VPC)** with two EC2 instances: one for a WordPress web server (public subnet) and one for a MySQL database server (private subnet). The architecture reflects best practices for separating frontend and backend resources in a secure and scalable manner.

---

## 🧰 Tech Stack

- **Terraform** for Infrastructure as Code
- **AWS VPC** with custom subnets
- **EC2** for application and database servers
- **Security Groups** to manage access

---

## 🗂️ Architecture Summary

- **VPC CIDR**: `192.168.0.0/16`
- **Public Subnet**: `192.168.0.0/24` (Zone: `ap-south-1a`)
- **Private Subnet**: `192.168.1.0/24` (Zone: `ap-south-1b`)
- **Internet Gateway**: Attached to the VPC
- **Route Table**: Associated to public subnet with default internet route
- **WordPress EC2 Instance**: Launched in public subnet, with SSH and HTTP access enabled
- **MySQL EC2 Instance**: Launched in private subnet, access restricted to WordPress instance via SG reference

---

## ✅ Prerequisites

- Terraform installed locally
- AWS CLI with configured profile `jayanth`
- A valid key pair named `saikey` in the `ap-south-1` region

---

## 🚀 Getting Started

1. Clone the repository
2. Run:
```bash
terraform init
terraform plan
terraform apply
```

---

## 🔐 Security Considerations

- SSH and HTTP ports are open to the internet (`0.0.0.0/0`) for demo purposes. Restrict access in production.
- The MySQL security group restricts DB access to only the web server (using SG reference).
- The private subnet does not have outbound internet access as NAT Gateway is not included.

---

## 🧠 Recruiter-Focused Highlights

- Demonstrates full **VPC architecture understanding**
- Uses **Terraform modules and resource blocks** correctly
- Implements **segregation of services** (frontend/backend)
- Security Groups use **reference-based restrictions** (WordPress SG → DB SG)
- Can easily evolve into production-grade design with NAT, ELB, and Auto Scaling

---
## 👤 Author

**Sai Jayanth Rajamahendram**  
Cloud | DevOps | Infrastructure as Code  
[LinkedIn](https://www.linkedin.com/in/saijayanthraj/) | [GitHub](https://github.com/saijayanth41)
