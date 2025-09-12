# 🌐 Two-Tier AWS VPC Infrastructure with NAT Gateway using Terraform

![Terraform](https://img.shields.io/badge/Terraform-623CE4?style=flat\&logo=terraform\&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-FF9900?style=flat\&logo=amazon-aws\&logoColor=white)
![Amazon-VPC](https://img.shields.io/badge/Amazon-VPC-232F3E?style=flat\&logo=amazonaws\&logoColor=white)
![Amazon-EC2](https://img.shields.io/badge/Amazon-EC2-FF9900?style=flat\&logo=amazonec2\&logoColor=white)

Automate AWS networking with **Terraform** to build a **Two-Tier VPC Infrastructure** that securely connects private and public subnets using an **Internet Gateway (IGW)** and a **NAT Gateway**.

---

## 📌 Project Overview

This project provisions:

* 🏗️ A **custom VPC** with CIDR block
* 🌐 **Public Subnet** with Internet Gateway access
* 🔒 **Private Subnet** with NAT Gateway for outbound internet access
* 💻 **EC2 instance in Public Subnet** (with public + private IP)
* 💻 **EC2 instance in Private Subnet** (only private IP)
* 📑 **Route Tables** for public and private traffic routing

---

## 🗂️ Folder Structure

```
terraform-vpc-nat/
├── main.tf
├── variables.tf
├── terraform.tfvars
├── outputs.tf
```

---

## ⚡ Prerequisites

* ✅ AWS Account
* ✅ Terraform installed
* ✅ Existing AWS key pair (for EC2 access)

---

## 🚀 Steps to Run

<details>
<summary>Click to Expand 🔽</summary>  

1. **Clone the repository**

```bash
git clone <your-repo-url>
cd terraform-vpc-nat
```

2. **Add AWS credentials** in `terraform.tfvars`:

```hcl
region     = "us-east-1"
access_key = "<your-aws-access-key>"
secret_key = "<your-aws-secret-key>"
```

3. **Initialize Terraform**

```bash
terraform init
```

4. **Preview the infrastructure**

```bash
terraform plan
```

5. **Apply Terraform**

```bash
terraform apply -auto-approve
```

6. **Verify resources in AWS Console**

   * Check VPC, Subnets, and Route Tables
   * Ensure **NAT Gateway** is created
   * Confirm EC2 connectivity (Public → Internet, Private → via NAT)

7. **Clean up resources**

```bash
terraform destroy -auto-approve
```

</details>  

---

## 🛠️ Terraform Resources Used

| Resource                              | Purpose                                   |
| ------------------------------------- | ----------------------------------------- |
| 🏗️ **aws\_vpc**                      | Create the custom VPC                     |
| 🌐 **aws\_internet\_gateway**         | Allow internet access for public subnet   |
| 🗂️ **aws\_route\_table**             | Define routing for subnets                |
| 🔗 **aws\_route\_table\_association** | Link route tables to subnets              |
| 📦 **aws\_subnet**                    | Create public & private subnets           |
| ⚡ **aws\_nat\_gateway**               | Provide outbound internet for private EC2 |
| 💻 **aws\_instance**                  | Launch EC2 instances in subnets           |
| 🔐 **aws\_security\_group**           | Allow SSH/HTTP access as needed           |
| 🌍 **aws\_eip**                       | Elastic IP for NAT Gateway                |

---

## 💡 Key Learnings

* ✅ Built a **two-tier VPC network** with Terraform
* ✅ Configured **public & private subnets** for secure workloads
* ✅ Understood **NAT Gateway vs Internet Gateway**
* ✅ Practiced routing, security groups, and subnet isolation

---

## 📈 Future Enhancements

<details>
<summary>Click to Expand 🔽</summary>  

* 🚀 Add **Application Load Balancer (ALB)** in public subnet
* ⚡ Integrate **Auto Scaling Groups** for private EC2s
* 🔒 Enable **VPN or Direct Connect** for hybrid networks
* 📊 Add **CloudWatch monitoring & VPC Flow Logs**

</details>  

---


## 📸 Screenshots
    
  <img width="1024" height="1024" alt="image" src="https://github.com/user-attachments/assets/d352dc82-df3a-44c1-9896-0d5f49b8e5a1" />

1. **Terraform Apply Output** – <img width="1899" height="970" alt="Screenshot 2025-09-12 170711" src="https://github.com/user-attachments/assets/5820e152-3494-41f5-8e0e-59a8bce72690" />

2. **AWS Console – VPC Dashboard** – <img width="1432" height="516" alt="image" src="https://github.com/user-attachments/assets/26111d25-383b-44cc-be06-bd5a1177c00d" />

3. **AWS Console – Subnets** – <img width="1439" height="464" alt="Screenshot 2025-09-12 171654" src="https://github.com/user-attachments/assets/6c1af944-053e-4d55-b80e-94b5568bce84" />

4. **AWS Console – Route Tables** –<img width="1438" height="579" alt="Screenshot 2025-09-12 171220" src="https://github.com/user-attachments/assets/d27cfb48-5d45-41f9-91b3-3c1a3f387483" />

5. **AWS Console – NAT Gateway** – <img width="1439" height="545" alt="image" src="https://github.com/user-attachments/assets/01bb697e-7083-41e6-8c0c-2b300c40a3a2" />

6. **EC2 Instances** – <img width="1438" height="579" alt="Screenshot 2025-09-12 171220" src="https://github.com/user-attachments/assets/7b3175e5-d775-47e0-8e5f-c115eac65343" />


---

## 👤 Author

**Balwant Singh**
Learning by doing projects with Terraform & AWS.

* LinkedIn: [Balwant Singh](https://www.linkedin.com/in/balwant-singh-aa024b37b/)

---

