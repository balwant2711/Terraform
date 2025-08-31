# 🚀 Launch an EC2 Instance as a Web Server using Terraform  

This project demonstrates how to use **Terraform** to provision an **EC2 instance on AWS** and configure it as a simple **Apache web server**. The web server hosts a basic HTML page served through HTTP.  

---

## 📌 Project Overview  

- **Provider:** AWS  
- **Service Used:** EC2, Security Groups  
- **Automation Tool:** Terraform  
- **Goal:** Deploy an Apache Web Server on EC2 and expose it via port **80 (HTTP)**  

---

## ⚙️ Features  

- Infrastructure defined as code using **Terraform**  
- Creates an **EC2 instance (t2.micro)** with a pre-defined AMI  
- Configures **Security Group** to allow inbound HTTP traffic  
- Uses **user_data script** to install and start Apache (`httpd`) automatically  
- Deploys a simple **HTML welcome page**  

---

## 📂 Project Structure  

```

├── main.tf          # Contains AWS provider, security group, and EC2 instance config
├── variables.tf     # Stores region, access\_key, secret\_key, and other variables
├── terraform.tfvars # Actual values for variables (ignored in git for security)

````

---

## 🛠️ main.tf Code  

```
provider "aws" {
  region     = "${var.region}"
  access_key = "${var.access_key}"
  secret_key = "${var.secret_key}"
}

resource "aws_security_group" "web-server" {
  name        = "web-server"
  description = "Allow incoming HTTP Connections"

  ingress {
    from_port   = 80
    to_port     = 80
    protocol    = "tcp"
    cidr_blocks = ["0.0.0.0/0"]
  }

  egress {
    from_port   = 0
    to_port     = 0
    protocol    = "-1"
    cidr_blocks = ["0.0.0.0/0"]
  }
}

resource "aws_instance" "web-server" {
  ami             = "ami-0150ccaf51ab55a51"
  instance_type   = "t2.micro"
  key_name        = "portfolio"
  security_groups = ["${aws_security_group.web-server.name}"]

  user_data = <<-EOF
    #!/bin/bash
    sudo su
    yum update -y
    yum install httpd -y
    systemctl start httpd
    systemctl enable httpd
    echo "<html><h1> Welcome to Cetpa Infotech. Happy Learning... </h1></html>" >> /var/www/html/index.html
  EOF

  tags = {
    Name = "web_instance"
  }
}
````

---

## 📋 variables.tf

```
variable "region" {}
variable "access_key" {}
variable "secret_key" {}
```

---

## 🔑 terraform.tfvars (example values)

```
region     = "ap-south-1"
access_key = "your-access-key"
secret_key = "your-secret-key"
```

⚠️ **Do not push real credentials to GitHub.** Add `terraform.tfvars` to `.gitignore`.

---

## 🚀 Deployment Steps

1. **Initialize Terraform**

   ```bash
   terraform init
   ```

2. **Validate the configuration**

   ```bash
   terraform validate
   ```

3. **Preview changes**

   ```bash
   terraform plan
   ```

4. **Apply configuration**

   ```bash
   terraform apply -auto-approve
   ```

5. **Access Web Server**

   * Copy the **Public IP** of the EC2 instance
   * Paste it in your browser:

     ```
     http://<EC2-Public-IP>
     ```

   You should see:

   > **Welcome to Cetpa Infotech. Happy Learning...**

---

## 🧹 Cleanup

To avoid charges, destroy resources:

```bash
terraform destroy -auto-approve
```

---

## 📷 Screenshots



---

## 📌 Skills & Tools Used

* **Terraform** (IaC)
* **AWS EC2**
* **AWS Security Groups**
* **Linux (Amazon Linux 2)**
* **Apache HTTPD Web Server**

---

## 🤝 Contributing

Feel free to fork this repo and enhance the project (e.g., host multi-page websites, use modules, or enable HTTPS).

---

## 📜 License

This project is licensed under the MIT License.

---


