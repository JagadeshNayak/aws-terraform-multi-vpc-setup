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


**OUTPUT**

Here you can see two images: before and after running terraform apply. In the "after" image, two EC2 instances named "FLIPKART" have been successfully created, and one VPC has also been added. You can clearly observe the changes in the screenshots.
**1. Before creating instances and vpc**

<img width="951" alt="1" src="https://github.com/user-attachments/assets/74aa08d5-879f-4b4d-8512-22ee7e7fc4a9" />

**2.After creating instances and vpc:**

<img width="952" alt="3" src="https://github.com/user-attachments/assets/a011e327-638d-4680-b597-40356fe9dc21" />

**THIS IS THE BEFORE AND AFTER IMAGES OF VPCS**
**1.Before**

<img width="955" alt="2" src="https://github.com/user-attachments/assets/6a853bb0-bbcf-4a9d-8d48-ee382c34e403" />

**2.After creating vpcs from here yoy can the difference **

<img width="958" alt="4" src="https://github.com/user-attachments/assets/9f7d918f-dbae-4aaa-bafc-963d3d82e519" />

**🔐 Security Tips**

**Never commit AWS credentials or private keys**

**Gugulothu Jagadish Nayak**









