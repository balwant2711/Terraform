# 🚀 S3 Bucket Event Notifications with SNS using Terraform

![Terraform](https://img.shields.io/badge/Terraform-623CE4?style=flat\&logo=terraform\&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-FF9900?style=flat\&logo=amazon-aws\&logoColor=white)
![Amazon-SNS](https://img.shields.io/badge/Amazon-SNS-FF4F00?style=flat\&logo=amazon-aws\&logoColor=white)

Automate AWS infrastructure using **Terraform** to trigger **SNS Email Notifications** when an **object is uploaded to an S3 bucket**.

---

## 📌 Project Overview

This project demonstrates:

* 🪣 Create an **S3 bucket** with Terraform
* 🔔 Configure an **SNS topic** for notifications
* 📧 Subscribe an **email endpoint** to SNS
* 🔗 Link **S3 bucket events → SNS topic**
* ⚡ Automate the entire flow using Terraform

---

## 🗂️ Folder Structure

```
terraform-s3-sns/
├── main.tf
├── variables.tf
├── terraform.tfvars
├── outputs.tf
```

---

## ⚡ Prerequisites

* ✅ AWS Account
* ✅ Terraform installed
* ✅ Valid email address for SNS subscription (must be confirmed)

---

## 🚀 Steps to Run

<details>
<summary>Click to Expand 🔽</summary>

1. **Clone the repository**

```bash
git clone <your-repo-url>
cd terraform-s3-sns
```

2. **Add AWS credentials** in `terraform.tfvars`:

```hcl
region     = "us-east-1"
access_key = "<your-aws-access-key>"
secret_key = "<your-aws-secret-key>"
endpoint   = "your-email@example.com"
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

6. **Confirm SNS subscription**

   * Check your email inbox for an AWS SNS confirmation email.
   * Click **Confirm subscription** to activate.

7. **Upload a test object to S3**

   * After confirmation, upload a file to your bucket.
   * You’ll instantly receive an email notification.

8. **Clean up resources**

```bash
terraform destroy -auto-approve
```

</details>

---

## 🛠️ Terraform Resources Used

| Resource                             | Purpose                             |
| ------------------------------------ | ----------------------------------- |
| 🪣 **aws\_s3\_bucket**               | Create S3 bucket for file uploads   |
| 🔔 **aws\_sns\_topic**               | Create SNS topic for notifications  |
| 📧 **aws\_sns\_topic\_subscription** | Subscribe email to SNS topic        |
| 🔗 **aws\_s3\_bucket\_notification** | Link S3 events to SNS topic         |
| 🔐 **random\_string**                | Ensure globally unique bucket names |

---

## 💡 Key Learnings

* ✅ Implemented **Infrastructure as Code (IaC)** with Terraform
* ✅ Automated **S3 → SNS email notification flow**
* ✅ Understood **SNS topic policies & S3 integration**
* ✅ Hands-on experience in event-driven AWS architecture

---

## 📈 Future Enhancements

<details>
<summary>Click to Expand 🔽</summary>

* 🌐 Add multiple email subscribers to SNS
* 🔒 Secure notifications with **encrypted SNS topics**
* ⚡ Trigger **Lambda functions** on S3 uploads
* 📊 Push notifications into monitoring tools like CloudWatch

</details>

---

## 📸 Screenshots

1. **Terraform Apply Output**
  <img width="1906" height="986" alt="Screenshot 2025-09-06 145030" src="https://github.com/user-attachments/assets/19308fe4-67f1-489d-930c-f2bc81aaa3c3" />


2. **AWS Console (S3 + SNS topic)**
   <img width="1439" height="527" alt="Screenshot 2025-09-06 144608" src="https://github.com/user-attachments/assets/b57afe9c-7f2c-4ba7-92c6-3d573a31d292" />
   <img width="1140" height="583" alt="Screenshot 2025-09-06 145138" src="https://github.com/user-attachments/assets/dbe7dbf9-2750-4258-b4b5-35296502eb01" />


3. **SNS Email Notification**
   <img width="948" height="275" alt="Screenshot 2025-09-06 150258" src="https://github.com/user-attachments/assets/5eeb449f-05de-4566-a550-0f67be0eb684" />
   <img width="556" height="208" alt="Screenshot 2025-09-06 145503" src="https://github.com/user-attachments/assets/5795bdc3-dd96-4955-bd2c-33eae5c13d3d" />


---

## 👤 Author

**Balwant Singh**
Learning by doing projects with Terraform & AWS.

* LinkedIn: [Balwant Singh](https://www.linkedin.com/in/balwant-singh-aa024b37b/)

---
