<img src="../assets/HashiCorp Terraform.png" alt="Alt Text" width="400">

# Terraform Beginner's Guide

Terraform by HashiCorp is an Infrastructure as Code tool that allows you to build, change, and version infrastructure safely and efficiently. It supports various cloud providers like AWS, Azure, Google Cloud, and more.

<br>

### **Table of Contents**

- [Overview](#overview)
- [What You'll Need](#what-youll-need)
- [Steps](#steps)
  - [Install Terraform](#install-terraform)
  - [Set Up Your First Terraform Configuration](#set-up-your-first-terraform-configuration)
  - [Initialize Terraform](#initialize-terraform)
  - [Apply the Configuration](#apply-the-configuration)
  - [Destroy the Infrastructure](#destroy-the-infrastructure)
- [Additional Tips](#additional-tips)
- [Conclusion](#conclusion)
- [Resources](#resources)
- [Contribution](#contribution)

<br>

## **Overview**

Terraform by HashiCorp is an Infrastructure as Code tool that simplifies the management of cloud infrastructure by allowing you to define and provision resources in a declarative configuration language.

<br>

## **What You'll Need**

- A computer with access to the command line.
- An account with a cloud provider (AWS, Azure, Google Cloud, etc.), if you plan to manage cloud resources.

<br>

## **Steps**

### **Install Terraform**

1. **Download Terraform**:
   - Visit the [Terraform downloads page](https://www.terraform.io/downloads.html) and download the appropriate package for your operating system.

2. **Install Terraform**:
   - Unzip the downloaded file.
   - Move the `terraform` binary to a directory included in your system's `PATH`.

3. **Verify Installation**:
   - Open a new terminal session.
   - Run `terraform -v` to verify the installation.

<br>

### **Set Up Your First Terraform Configuration**

1. **Create a Directory**:
   - Create a new directory for your Terraform project.
   - Navigate into the directory.

2. **Write Configuration**:
   - Create a new file named `main.tf`.
   - Add the following basic configuration (using AWS as an example):

     ```hcl
     provider "aws" {
       region = "us-west-2"
     }

     resource "aws_instance" "example" {
       ami           = "ami-0c55b159cbfafe1f0"
       instance_type = "t2.micro"
     }
     ```

   - Replace the `ami` value with a valid AMI for your AWS region.

<br>

### **Initialize Terraform**

1. **Initialize the Project**:
   - In your project directory, run:

     ```bash
     terraform init
     ```

   - This command initializes the project, downloads the AWS provider, and sets up the environment.

<br>

### **Apply the Configuration**

1. **Create an Execution Plan**:
   - Run:

     ```bash
     terraform plan
     ```

   - Terraform will display what actions will be performed.

2. **Apply the Configuration**:
   - Execute:

     ```bash
     terraform apply
     ```

   - Confirm the action when prompted.
   - Terraform will create the resources as specified.

<br>

### **Destroy the Infrastructure**

- When you no longer need the resources:

  ```bash
  terraform destroy
  ```

- This command removes all resources created by Terraform.

<br>

## **Additional Tips**

- **Read Terraform Documentation**: For in-depth understanding, refer to the [Terraform documentation](https://www.terraform.io/docs/index.html).
- **Version Control**: Keep your Terraform configurations in version control (like Git) for better management.
- **Modularize Your Terraform Code**: As your infrastructure grows, organize your code into modules for reuse and maintainability.

<br>

## **Conclusion**

Terraform simplifies the management of cloud infrastructure by enabling you to define resources in code. Whether you're managing simple setups or complex multi-cloud environments, Terraform's declarative approach and rich ecosystem make it a powerful tool for infrastructure as code.

<br>

## **Resources**

- [Terraform Official Documentation](https://www.terraform.io/docs/index.html)
- [Terraform Registry](https://registry.terraform.io/) for pre-built modules
- [HashiCorp Learn](https://learn.hashicorp.com/terraform)

<br>

## **Contribution**

Your contributions can make these scripts even better:

- Fork the repository.

- Create a new branch:

  ```bash
  git checkout -b my-awesome-feature
  ```

- Make your invaluable changes.

- Commit your changes:

  ```bash
  git commit -am 'Added some amazing features'
  ```

- Push to the branch:

  ```bash
  git push origin my-awesome-feature
  ```

- Create a new Pull Request targeting the Notes directory.

Contributions are welcome! Feel free to open issues, suggest enhancements, or submit pull requests to improve the script.

<br>

## **Author**

- **Raphael Chookagian** | [GitHub Profile](https://github.com/cesar-group)

## **Date of Latest Revision**

- 12/09/2024

## **License**

- This script is provided as-is without any warranties. Users are advised to review and understand the script before executing it.

- This project is licensed under the MIT License. See the LICENSE file for details.
