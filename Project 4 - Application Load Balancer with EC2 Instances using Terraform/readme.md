Perfect — you want me to create a **GitHub-style `README.md`** for your **Application Load Balancer with EC2 Instances using Terraform** project, in the same detailed and professional format as your S3 + SNS one.

Here’s the complete draft:

---

# 🚀 Application Load Balancer with EC2 Instances using Terraform

![Terraform](https://img.shields.io/badge/Terraform-623CE4?style=flat\&logo=terraform\&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-FF9900?style=flat\&logo=amazon-aws\&logoColor=white)
![Amazon-EC2](https://img.shields.io/badge/Amazon-EC2-FF9900?style=flat\&logo=amazonec2\&logoColor=white)
![Amazon-ALB](https://img.shields.io/badge/Amazon-ALB-527FFF?style=flat\&logo=amazonaws\&logoColor=white)

Automate AWS infrastructure using **Terraform** to deploy an **Application Load Balancer (ALB)** that distributes incoming traffic between **two EC2 instances**.

---

## 📌 Project Overview

This project demonstrates:

* ⚙️ Provisioning **2 EC2 instances** with Apache web servers
* 🔐 Creating a **Security Group** to allow HTTP traffic
* 🌐 Setting up an **Application Load Balancer (ALB)**
* 🎯 Defining **Target Groups** with health checks
* 🔗 Attaching EC2 instances to the Target Group
* ⚡ Automating the full architecture with Terraform

---

## 🗂️ Folder Structure

```
terraform-alb-ec2/
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
cd terraform-alb-ec2
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

6. **Access the ALB DNS name**

   * Terraform will output the **`elb-dns-name`**.
   * Paste it in your browser and verify traffic is routed to your EC2 instances.

7. **Clean up resources**

```bash
terraform destroy -auto-approve
```

</details>  

---

## 🛠️ Terraform Resources Used

| Resource                                  | Purpose                                      |
| ----------------------------------------- | -------------------------------------------- |
| 🔐 **aws\_security\_group**               | Allow inbound HTTP traffic for EC2 + ALB     |
| 💻 **aws\_instance**                      | Launch 2 EC2 instances with Apache webserver |
| 🌐 **aws\_lb**                            | Create the Application Load Balancer         |
| 🎯 **aws\_lb\_target\_group**             | Define target group with health checks       |
| 🔗 **aws\_lb\_target\_group\_attachment** | Attach EC2s to the target group              |
| 🎧 **aws\_lb\_listener**                  | Forward requests from ALB to target group    |
| 🗂️ **aws\_vpc & aws\_subnet (data)**     | Use default VPC and subnets for deployment   |

---

## 💡 Key Learnings

* ✅ Automated **EC2 + ALB setup** with Terraform
* ✅ Understood **Target Groups & health checks**
* ✅ Implemented **high availability** using multiple subnets (AZs)
* ✅ Gained hands-on experience with **scalable AWS architecture**

---

## 📈 Future Enhancements

<details>
<summary>Click to Expand 🔽</summary>

* ⚡ Integrate **Auto Scaling Groups (ASG)** for elasticity
* 🔒 Enable **HTTPS (TLS/SSL)** on the ALB
* 📊 Add **CloudWatch monitoring & alarms**
* 🚀 Deploy via CI/CD pipeline for automation

</details>  

---

## 📸 Screenshots

1. **Terraform Apply Output (with ALB DNS)**
   <img width="1371" height="783" alt="Screenshot 2025-09-06 153259" src="https://github.com/user-attachments/assets/35a93cb7-4d27-405c-8447-95edadcad1d7" />


2. **AWS Console – Load Balancer Dashboard**
 
<img width="1916" height="485" alt="Screenshot 2025-09-06 153408" src="https://github.com/user-attachments/assets/052fa247-18e7-4b33-9f2b-0fe26e2e47ce" />

3. **AWS Console – Target Group Health Check**
   *(EC2 instances registered as healthy)*

4. **Browser Test**
  <img width="1665" height="342" alt="Screenshot 2025-09-06 153459" src="https://github.com/user-attachments/assets/ab2c69ca-cff1-42ba-b898-b87eb1ea62cf" />


---

## 👤 Author

**Balwant Singh**
Learning by doing projects with Terraform & AWS.

* LinkedIn: [Balwant Singh](https://www.linkedin.com/in/balwant-singh-aa024b37b/)

---
