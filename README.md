terraform_portfolio:
  meta:
    title: "🌍 Terraform AWS Projects – Infrastructure as Code (IaC)"
    tagline: "Automating real-world AWS infrastructures using Terraform 🚀"
    description: >
      This collection contains six hands-on Terraform projects built on AWS.
      Each project focuses on a real-world use case such as web hosting,
      VPC networking, load balancing, S3 integration, event notifications,
      and secure two-tier architectures.

  branding:
    primary_tech: "Terraform"
    primary_cloud: "AWS"
    badges:
      - label: "Terraform"
        image: "https://img.shields.io/badge/Terraform-623CE4?style=flat&logo=terraform&logoColor=white"
      - label: "AWS"
        image: "https://img.shields.io/badge/AWS-FF9900?style=flat&logo=amazon-aws&logoColor=white"
    theme:
      emoji_accent: "✨"
      color_style: "purple-cloud"
      vibe: "clean, modern, cloud-native"

  structure:
    root_folder: "terraform/"
    description: "All Terraform-based AWS projects are grouped inside this folder."
    tree:
      - "01-ec2-webserver/        # EC2 + Apache web server (HTTP)"
      - "02-vpc-create-destroy/   # Basic custom VPC creation & teardown"
      - "03-s3-access-from-ec2/   # EC2 serving content from S3 using IAM Role"
      - "04-alb-with-ec2/         # Application Load Balancer + 2 EC2 instances"
      - "05-s3-sns-notification/  # S3 object upload → SNS email notification"
      - "06-vpc-nat-two-tier/     # Two-tier VPC with NAT Gateway"
      - "README.md                # Terraform portfolio overview (this file)"

  skills:
    high_level:
      - "Infrastructure as Code (IaC) with Terraform 🧱"
      - "AWS Networking – VPC, Subnets, Route Tables, NAT, IGW 🌐"
      - "Compute – EC2 provisioning & automation 💻"
      - "Storage & Integration – S3, IAM Roles, Instance Profiles 🪣"
      - "Traffic Management – Application Load Balancer (ALB) ⚖️"
      - "Event-Driven Design – S3 Events with SNS Notifications 🔔"
      - "Security – Security Groups, least-privilege IAM policies 🔐"
    tools:
      - "Terraform (HCL)"
      - "AWS Management Console"
      - "AWS CLI (optional)"
      - "Git & GitHub"

  projects:
    - id: 1
      code: "01-ec2-webserver"
      name: "🚀 EC2 Apache Web Server using Terraform"
      short_tagline: "From zero to running web server with a single terraform apply."
      overview: >
        This project provisions a single EC2 instance and automatically configures
        it as an Apache HTTP web server using user_data. It demonstrates how to
        go from no infrastructure to a live, publicly accessible web page in one
        Terraform workflow.
      aws_services:
        - "EC2"
        - "Security Groups"
      highlights:
        - "Creates an EC2 instance (t2.micro) in a chosen AWS region."
        - "Uses user_data to install and start Apache (httpd) automatically."
        - "Deploys a simple HTML welcome page on /var/www/html/index.html."
        - "Configures a Security Group to allow inbound HTTP (port 80) from the internet."
      learning_focus:
        - "Basic Terraform provider and resource definition."
        - "Using user_data for server bootstrapping."
        - "Ingress/egress rules with Security Groups."
      difficulty: "Beginner-friendly 🌱"

    - id: 2
      code: "02-vpc-create-destroy"
      name: "🏗️ Create & Destroy VPC using Terraform"
      short_tagline: "Foundational networking stack as code."
      overview: >
        This project automates the creation of a custom AWS VPC and its core
        components like subnets, internet gateway, and route tables. It is ideal
        for understanding how Terraform manages network-level infrastructure and
        how easy it is to create and tear down environments.
      aws_services:
        - "VPC"
        - "Subnets"
        - "Internet Gateway"
        - "Route Tables"
      highlights:
        - "Defines a custom CIDR block for the VPC."
        - "Creates subnets mapped to the VPC."
        - "Attaches an Internet Gateway for outbound internet access."
        - "Sets up route tables and associations for proper routing."
      learning_focus:
        - "Complete Terraform lifecycle – init, plan, apply, destroy."
        - "Using variables.tf and terraform.tfvars for reusability."
        - "Exposing important IDs via outputs.tf."
      difficulty: "Beginner to Intermediate 📘"

    - id: 3
      code: "03-s3-access-from-ec2"
      name: "🪣 EC2 Accessing S3 Bucket using IAM Role"
      short_tagline: "Serve S3-hosted content through an EC2 web server securely."
      overview: >
        This project shows how to securely connect an EC2 instance to an S3 bucket
        using an IAM Role and Instance Profile. The EC2 instance runs Apache and
        serves HTML files that are stored in the S3 bucket, demonstrating a clean
        separation of compute and storage.
      aws_services:
        - "EC2"
        - "S3"
        - "IAM Role"
        - "IAM Instance Profile"
        - "Security Groups"
      highlights:
        - "Creates an S3 bucket to store static HTML files."
        - "Launches an EC2 instance with Apache installed via user_data."
        - "Attaches an IAM Role that grants read access to the S3 bucket."
        - "Serves web content from S3 without hardcoding credentials."
      learning_focus:
        - "Best practices with IAM: no credentials on the server."
        - "Practical EC2 ↔ S3 integration patterns."
        - "Combining multiple AWS services through Terraform."
      difficulty: "Intermediate ⚙️"

    - id: 4
      code: "04-alb-with-ec2"
      name: "⚖️ Application Load Balancer with EC2 Instances"
      short_tagline: "High-availability web architecture with ALB + 2 EC2 instances."
      overview: >
        This project builds a classic scalable web architecture where an
        Application Load Balancer distributes traffic to two EC2 instances running
        Apache. It demonstrates core concepts of load balancing, target groups,
        and health checks in AWS, all managed via Terraform.
      aws_services:
        - "Application Load Balancer (ALB)"
        - "Target Group"
        - "ALB Listener"
        - "EC2"
        - "Security Groups"
      highlights:
        - "Launches two EC2 instances in different subnets (where applicable)."
        - "Creates an ALB and configures listeners on HTTP (port 80)."
        - "Defines a target group with health checks for backend instances."
        - "Registers EC2 instances into the target group for traffic distribution."
      learning_focus:
        - "Designing for high availability and scalability."
        - "Understanding target groups, health checks, and ALB behavior."
        - "Routing traffic using ALB DNS instead of direct EC2 IPs."
      difficulty: "Intermediate to Advanced 📗"

    - id: 5
      code: "05-s3-sns-notification"
      name: "🔔 S3 Event Notifications with SNS (Email Alerts)"
      short_tagline: "Event-driven architecture: S3 uploads → SNS email notifications."
      overview: >
        This project wires up S3 and SNS to send email notifications whenever a new
        object is uploaded to the S3 bucket. It showcases how Terraform can be used
        to build event-driven workflows in AWS, from bucket creation to topic setup
        and subscription management.
      aws_services:
        - "S3"
        - "SNS Topic"
        - "SNS Subscription (Email)"
      highlights:
        - "Creates an S3 bucket for file uploads."
        - "Creates an SNS topic and email subscription endpoint."
        - "Configures S3 bucket notifications to trigger SNS on object creation."
        - "Sends an email each time a new file is uploaded (after confirmation)."
      learning_focus:
        - "Event-driven design principles on AWS."
        - "Integrating S3 event notifications with SNS."
        - "Understanding subscription confirmation flow."
      difficulty: "Intermediate 📡"

    - id: 6
      code: "06-vpc-nat-two-tier"
      name: "🌐 Two-Tier VPC with NAT Gateway"
      short_tagline: "Secure two-tier network with public & private subnets."
      overview: >
        This advanced networking project provisions a two-tier VPC architecture with
        public and private subnets. A NAT Gateway in the public subnet enables the
        private EC2 instance to reach the internet for updates, while remaining
        inaccessible from the public internet.
      aws_services:
        - "VPC"
        - "Public Subnet"
        - "Private Subnet"
        - "Internet Gateway"
        - "NAT Gateway"
        - "Route Tables & Associations"
        - "EC2 Instances"
        - "Elastic IP (for NAT)"
      highlights:
        - "Creates a custom VPC with segmented public and private subnets."
        - "Configures an Internet Gateway and public route table."
        - "Deploys a NAT Gateway for outbound access from private subnet."
        - "Launches an EC2 instance in each subnet (public + private)."
      learning_focus:
        - "Production-style network segmentation."
        - "Public vs private subnet routing strategies."
        - "Using NAT for secure outbound-only internet access."
      difficulty: "Advanced 🧠"

  how_to_run:
    common_steps:
      - "cd into any project folder, e.g. 01-ec2-webserver/"
      - "Update terraform.tfvars with your AWS region and credentials."
      - "Run terraform init to initialize the working directory."
      - "Run terraform plan to preview infrastructure changes."
      - "Run terraform apply -auto-approve to create resources."
    commands:
      init: "terraform init"
      plan: "terraform plan"
      apply: "terraform apply -auto-approve"
      destroy: "terraform destroy -auto-approve"
    note: >
      💡 Always destroy resources after testing to avoid unexpected AWS charges.

  prerequisites:
    - "✅ Active AWS Account"
    - "✅ Terraform installed locally"
    - "✅ AWS credentials configured (via terraform.tfvars, env vars, or profile)"
    - "✅ Basic familiarity with AWS & networking concepts"

  author:
    name: "Balwant Singh"
    tagline: "Learning Cloud & DevOps by building real projects ☁️"
    contacts:
      linkedin: "https://www.linkedin.com/in/balwant-singh-aa024b37b/"
      github: "https://github.com/balwant2711"
