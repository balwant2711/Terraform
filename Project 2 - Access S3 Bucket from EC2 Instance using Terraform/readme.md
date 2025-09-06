
# 🚀 Access S3 Bucket from EC2 Instance using Terraform

![Terraform](https://img.shields.io/badge/Terraform-623CE4?style=flat&logo=terraform&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-FF9900?style=flat&logo=amazon-aws&logoColor=white)
![Apache](https://img.shields.io/badge/Apache-Server-D22128?style=flat&logo=apache&logoColor=white)

Automate AWS infrastructure using **Terraform** to allow an **EC2 instance** to access **S3 bucket objects** and serve them via a web server.  

---

## 📌 Project Overview

This project demonstrates:

- 🪣 Create an S3 bucket and upload HTML files  
- 💻 Launch an EC2 instance with Apache installed  
- 🔐 Configure IAM Role & Instance Profile for EC2 access to S3  
- 🌐 Serve HTML pages stored in S3 via EC2  
- ⚡ Automate deployment using Terraform

---

## 🗂️ Folder Structure

```

terraform-s3-ec2/
├── main.tf
├── variables.tf
├── terraform.tfvars
├── outputs.tf
└── html/
└── index.html

````

---

## ⚡ Prerequisites

- ✅ AWS Account  
- ✅ Terraform installed  
- ✅ Basic knowledge of AWS EC2, S3, IAM, Security Groups

---

## 🚀 Steps to Run

<details>
<summary>Click to Expand 🔽</summary>

1. **Clone the repository**

```bash
git clone <your-repo-url>
cd terraform-s3-ec2
````

2. **Add AWS credentials** in `terraform.tfvars`:

```hcl
region      = "us-east-1"
access_key  = "<your-aws-access-key>"
secret_key  = "<your-aws-secret-key>"
bucket_name = "balwant-s3-demo-bucket-2025"
```

> ⚠️ Bucket name must be **globally unique** and lowercase.

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

6. **Access the website**

Copy the EC2 public IP from Terraform outputs:

```
http://<EC2-public-ip>
```

7. **Clean up resources**

```bash
terraform destroy -auto-approve
```

</details>

---

## 🛠️ Terraform Resources Used

| Resource                                            | Purpose                         |
| --------------------------------------------------- | ------------------------------- |
| 🪣 **aws\_s3\_bucket**                              | Stores HTML files               |
| 📄 **aws\_s3\_bucket\_object**                      | Upload HTML files to S3         |
| 🔐 **aws\_iam\_role & aws\_iam\_instance\_profile** | Allow EC2 to access S3          |
| 🛡️ **aws\_security\_group**                        | Allows HTTP traffic (port 80)   |
| 💻 **aws\_instance**                                | Launch EC2 instance with Apache |

---

## 💡 Key Learnings

* ✅ Implemented **Infrastructure as Code (IaC)** with Terraform
* ✅ Created secure **EC2 ↔ S3 integration** using IAM roles
* ✅ Automated Apache server configuration via **user\_data**
* ✅ Hands-on experience with AWS service deployment & automation

---

## 📈 Future Enhancements

<details>
<summary>Click to Expand 🔽</summary>

* 🌐 Host a **full static website** on S3
* 🔒 Enable **CloudFront + HTTPS** for performance & security
* ⚡ Extend setup to **Auto Scaling EC2 instances**
* 🔄 Integrate with **CI/CD pipeline** for automated deployments

</details>

---

## 📸 Screenshots

1. **Terraform Plan & Apply Output**
 <img width="1891" height="937" alt="Screenshot 2025-09-06 104727" src="https://github.com/user-attachments/assets/7869e16a-084f-4bec-99ba-09145a043b84" />


2. **AWS Console View (EC2 + S3)**
<img width="1919" height="837" alt="Screenshot 2025-09-06 110437" src="https://github.com/user-attachments/assets/e9f06ae8-4cd5-4935-b80e-5f6a28eaf094" />
<img width="1919" height="593" alt="Screenshot 2025-09-06 110558" src="https://github.com/user-attachments/assets/fb80f1a8-0302-4339-b9ee-94027bbaf588" />



3. **Website served via EC2**
<img width="1907" height="721" alt="Screenshot 2025-09-06 110749" src="https://github.com/user-attachments/assets/270c710e-b9d7-4317-a475-4f8fe82f682d" />

---

## 👤 Author

**Balwant Singh**
Learning by doing projects with Terraform & AWS.

* LinkedIn: https://www.linkedin.com/in/balwant-singh-aa024b37b/

