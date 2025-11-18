Absolutely! Here is your **final README.md** — based on the YAML but structured beautifully for GitHub, portfolio, or recruiter review.
It includes logos, emojis, sections, and clear formatting. **You can directly copy-paste it into your Terraform folder.**

---

# 🌍 Terraform AWS Projects – Infrastructure as Code (IaC)

This folder contains **six real-world AWS infrastructure projects** built using **Terraform**.
Each project demonstrates a specific use case — from web hosting and VPC creation to load balancing, S3 integration, event notifications, and secure two-tier architecture.

> 🚀 *Built with Terraform and AWS – Fully automated using Infrastructure as Code (IaC)*

---

## 🧾 Tech Stack & Skills Demonstrated

| Skill / Service                   | Purpose                    |
| --------------------------------- | -------------------------- |
| **Terraform (HCL)**               | IaC automation             |
| **AWS EC2**                       | Compute provisioning       |
| **AWS VPC, NAT, Subnets**         | Networking & Routing       |
| **Security Groups, IAM Policies** | Access & Security          |
| **Application Load Balancer**     | Traffic distribution       |
| **S3, SNS, IAM Roles**            | Event-driven workflow      |
| **Provider + Modules Structure**  | Clean & reusable Terraform |

---

## 📁 Folder Structure

```
terraform/
│── 01-ec2-webserver/        # EC2 + Apache Web Server
│── 02-vpc-create-destroy/   # Custom VPC creation & teardown
│── 03-s3-access-from-ec2/   # IAM Role: EC2 reading from S3
│── 04-alb-with-ec2/         # ALB distributing traffic to EC2s
│── 05-s3-sns-notification/  # Event: S3 upload → SNS email alert
│── 06-vpc-nat-two-tier/     # Two-tier VPC with NAT Gateway
│── README.md                # (This file)
```

Each project folder includes:
✔ `main.tf`
✔ `variables.tf`
✔ `terraform.tfvars (example)`
✔ `outputs.tf` (where needed)
✔ `README.md` with explanation & screenshots

---

# 📦 Projects Breakdown

## 1️⃣ 🚀 EC2 Apache Web Server using Terraform

**Folder:** `01-ec2-webserver/`
Deploys an **EC2 instance** with **Apache web server** using `user_data`.
Security Group allows **HTTP traffic on port 80**, making the webpage publicly accessible.

**Key Concepts**

* Terraform provider + resource basics
* Security Groups for HTTP access
* user_data to install/configure Apache

**AWS Services Used**

> EC2 • Security Groups

---

## 2️⃣ 🏗️ Create & Destroy VPC using Terraform

**Folder:** `02-vpc-create-destroy/`
Builds a **custom VPC** with subnets, route table and Internet Gateway.
Created using `terraform apply` — removed cleanly using `terraform destroy`.

**Key Concepts**

* IaC workflow: init / plan / apply / destroy
* Routing & basic networking
* CIDR planning and subnetting

**AWS Services Used**

> VPC • Subnets • Route Tables • Internet Gateway

---

## 3️⃣ 🪣 EC2 Accessing S3 Bucket Securely

**Folder:** `03-s3-access-from-ec2/`
EC2 fetches **HTML content from S3** and serves it through Apache.
Uses **IAM Role + Instance Profile** instead of hardcoding credentials.

**Key Concepts**

* IAM Role ➝ EC2 access to S3
* Apache web server automation
* Secure EC2 ↔ S3 integration

**AWS Services Used**

> EC2 • S3 • IAM Roles • Security Groups

---

## 4️⃣ ⚖️ Application Load Balancer with EC2 Instances

**Folder:** `04-alb-with-ec2/`
Scalable architecture: **ALB → two EC2 instances**.
Traffic is distributed using **Target Group + Health Checks**.

**Key Concepts**

* High availability architecture
* Target groups & listener rules
* ALB DNS instead of direct IPs

**AWS Services Used**

> ALB • EC2 • Target Groups • Security Groups

---

## 5️⃣ 🔔 S3 Event Notifications with SNS (Email Alerts)

**Folder:** `05-s3-sns-notification/`
When a file is uploaded to S3 ➝ AWS SNS sends an **email notification**.
Demonstrates event-driven architecture using Terraform.

**Key Concepts**

* S3 → SNS trigger
* Email subscription + confirmation flow
* Event-based IaC deployment

**AWS Services Used**

> S3 • SNS Topic • SNS Subscription (Email)

---

## 6️⃣ 🌐 Two-Tier VPC with NAT Gateway

**Folder:** `06-vpc-nat-two-tier/`
A **production-style network setup** with:
✔ Public subnet (exposed)
✔ Private subnet (hidden)
✔ NAT Gateway for secure outbound traffic
✔ EC2 instance in each subnet

**Key Concepts**

* Secure private subnet design
* Route tables & EIP for NAT
* Public–private communication model

**AWS Services Used**

> VPC • Internet Gateway • NAT Gateway • Subnets • EC2 • Elastic IP

---

# 🧪 How to Run Any Project

```bash
terraform init
terraform plan
terraform apply -auto-approve
```

To remove everything later ⛔:

```bash
terraform destroy -auto-approve
```

> 💡 Tip: Always destroy resources after testing to avoid AWS charges!

---

# 📦 Prerequisites

| Required            | Details                            |
| ------------------- | ---------------------------------- |
| AWS Account         | Needed for credentials & API calls |
| Terraform Installed | `terraform -version` to check      |
| IAM User            | With programmatic access           |
| AWS Region          | Must match Terraform config        |
| terraform.tfvars    | Should contain AWS keys            |

---

# 👤 Author

**Balwant Singh**
*Learning Cloud & DevOps by building real projects* ☁️

🔗 LinkedIn – [https://www.linkedin.com/in/balwant-singh-aa024b37b/](https://www.linkedin.com/in/balwant-singh-aa024b37b/)
💻 GitHub – [https://github.com/balwant2711](https://github.com/balwant2711)

---

Let me know if you want:
✔ Terraform Project Diagram (draw.io / PNG)
✔ CI/CD Pipeline with GitHub Actions
✔ Resume Section for Terraform Skills

I'll help you build it next! 🚀
