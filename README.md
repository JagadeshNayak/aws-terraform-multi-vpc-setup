**🚀Terraform AWS Multi-Instance & VPC Deployment**

This project automates the deployment of two EC2 instances along with two separate VPCs simultaneously using Terraform on an AWS EC2 Ubuntu server.

🧾 Steps to Set Up
✅ 1. Connect to Your EC2 Ubuntu Server

Use your .pem key to SSH into the EC2 instance:

bash
Copy
Edit
ssh -i "your-key.pem" ubuntu@your-ec2-public-ip
**✅ 2. Install Terraform on the EC2 Ubuntu Server**
bash
Copy
Edit
sudo apt update && sudo apt upgrade -y
sudo apt install -y wget unzip

# Download and install Terraform
wget https://releases.hashicorp.com/terraform/1.6.6/terraform_1.6.6_linux_amd64.zip
unzip terraform_1.6.6_linux_amd64.zip
sudo mv terraform /usr/local/bin/

# Verify installation
terraform -version
**✅ 3. Configure AWS CLI with Your Credentials**
You'll need your AWS Access Key, Secret Key, and the Region where you want to deploy the resources.

bash
Copy
Edit
aws configure
**✅ 4. Note Down Your AMI ID**
Find a suitable AMI ID (e.g., Ubuntu) from your AWS Console and copy it. You'll need this while writing your .tf code.

**✅ 5. Create Terraform Configuration File**
Create a file named filename.tf:

bash
Copy
Edit
touch filename.tf
nano filename.tf
Paste the Terraform code from this repository into filename.tf.

**✅ 6. Run Terraform Commands**
bash
Copy
Edit

# Initialize the directory
terraform init

<img width="958" alt="5" src="https://github.com/user-attachments/assets/8fdcb14e-bb4d-40d1-8ce1-6e9134a7b88e" />

# Review the resources
terraform plan

<img width="959" alt="6" src="https://github.com/user-attachments/assets/8a23dc75-27dd-456e-88e3-a5dd77a1eaee" />

# Apply and create infrastructure #
terraform apply
Type yes when prompted.

<img width="957" alt="7" src="https://github.com/user-attachments/assets/634f2b00-e89c-4090-adef-16c03198ebc7" />


**✅ 7. Destroy Infrastructure (When Done)**
bash
Copy
Edit
terraform destroy

<img width="959" alt="8" src="https://github.com/user-attachments/assets/fd8e0ead-d051-40b4-8827-295db5a72811" />

**🛠 Project Features**
Two separate VPCs with distinct CIDR blocks

Two EC2 instances (one in each VPC)

Custom subnets, internet gateways, and route tables

Key pair and security group configuration

📁 Directory Structure
bash
Copy
Edit
terraform-multi-vpc/
│
├── instance.tf         # Main Terraform code

├── variables.tf        # (Optional) Variable definitions

├── outputs.tf          # (Optional) Outputs

├── provider.tf         # AWS provider config

└── README.md

🔐 Security Tips

**Never commit AWS credentials or private keys**

