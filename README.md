# 🚀 Terraform VPC Project

This project creates a **custom VPC with public and private subnets** in AWS using **Terraform**.  
It is designed for setting up networking resources (VPC, subnets, route tables, internet gateway, NAT gateway, security groups, etc.) as the base layer for your infrastructure.

---

## 📂 Project Structure

terraform-vpc/

│── instance.tf # EC2 instance configuration

│── loadbalancer.tf # Load balancer configuration

│── out.tf # Output values (VPC ID, Subnet IDs, etc.)

│── providers.tf # Provider and AWS region setup

│── vars.tf # Variable definitions

│── vpc.tf # VPC, Subnets, Gateways, Route Tables

│── README.md # Documentation




---
```
## 🛠️ Prerequisites

Before using this project, make sure you have:

- ✅ An **AWS Account**
- ✅ **Terraform** installed ([Download](https://developer.hashicorp.com/terraform/downloads))
- ✅ **AWS CLI** installed and configured with your credentials:
  ```bash
  aws configure
```
---

✅ SSH key pair (public/private key) created for EC2 instances.

---
⚙️ Configuration

All configurable variables are stored in vars.tf.

You can update them as per your requirements.

---

```
Example important variables:


variable "AWS_REGION" {
  default = "ap-south-1"
}

variable "VPC_NAME" {
  default = "vprofile-VPC"
}

variable "VpcCIDR" {
  default = "172.21.0.0/16"
}

variable "PubSub1CIDR" {
  default = "172.21.1.0/24"
}
```
👉 Update MYIP variable with your system’s public IP for SSH access:

```
h
variable "MYIP" {
  default = "YOUR_PUBLIC_IP/32"
}
```
---
🚀 How to Run

1️⃣ Initialize Terraform
```
terraform init
```
2️⃣ Validate Configuration
```
terraform validate
```
3️⃣ See Execution Plan
```
terraform plan
```
4️⃣ Apply Configuration (Create VPC & Resources)
bash
Copy
Edit
terraform apply -auto-approve
5️⃣ Destroy Infrastructure (Clean Up)
```
terraform destroy -auto-approve
```
---
📤 Outputs
After applying, Terraform will output useful information such as:

- VPC ID

- Public & Private Subnet IDs

- Security Group IDs

- Load Balancer DNS

---

📝 Notes

- Make sure you don’t exceed AWS limits (max 5 VPCs per region by default).

- You can request a VPC quota increase in AWS if needed.

- Always destroy resources after testing to avoid charges.

  ---

📌 Example Use Case
This VPC setup can be used for:

- Deploying an EKS cluster

- Hosting multi-tier applications

- Running EC2 instances with secure networking
---
