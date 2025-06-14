# Ansible vs Terraform: Key Points & Setup Guide

## ❌ Disadvantages of Ansible for Infrastructure Provisioning

- **Poor state management**  
  Ansible does not maintain the state of infrastructure.  
  *Example:* If someone manually modifies the infrastructure from the cloud console, Ansible cannot detect those changes and may recreate or duplicate resources.

- **Not ideal for provisioning**  
  Best suited for configuration within servers (e.g., installing packages, setting up services), not for creating or managing cloud infrastructure.

---

## ❌ Disadvantages of Creating Infrastructure Manually

- **Time-consuming**  
  Manual setup takes significantly more time compared to automation.

- **Prone to errors**  
  Increases chances of misconfiguration or inconsistent environments.

- **Difficult to track issues**  
  Troubleshooting becomes hard when there’s no log or history.

- **No version control**  
  Changes cannot be audited or reviewed. No collaboration or rollback options.

---

## ✅ Benefits of Infrastructure as Code (IaC)

- **Version Control**  
  Enables:
  - Change tracking
  - Code reviews
  - Collaboration using Git
  - Rollbacks and audits

- **CRUD Operations Simplified**  
  Easy to Create, Read, Update, and Delete infrastructure through code.

- **Consistency Across Environments**  
  Avoid the "works in dev, fails in prod" issue by replicating the same infra in every environment.

- **Inventory Management**  
  Easily understand what resources are in use by reading the code.

- **Cost Efficiency**  
  - Automatically shut down resources during non-business hours.
  - Schedule start/stop based on usage.

- **Dependency Management**  
  Automatically handles relationships between resources (e.g., attach an instance to a VPC or subnet).

- **Modular Approach**  
  Use reusable Terraform modules for better code structure and DRY principles.

---

## ⚙️ Installing Terraform on Windows

1. **Download Terraform:**
   - Go to [https://www.terraform.io/downloads.html](https://www.terraform.io/downloads.html)
   - Select `AMD64` version for Windows

2. **Extract & Place:**
   - Unzip the Terraform binary
   - Place it in a folder (e.g., `C:\Softwares\Terraform`)

3. **Set System Path:**
   - Go to `System Properties` → `Advanced` → `Environment Variables`
   - Under `System variables`, find `Path` → `Edit` → `Add` the Terraform folder path

4. **Verify Installation:**
   ```bash
   terraform --version
   ```

---

## 🚀 Getting Started with Terraform & AWS

1. **Create Terraform GitHub Repo**
   ```bash
   git clone <your_repo_url>
   cd terraform/
   ```

2. **Define Provider Configuration (`provider.tf`)**
   Example for AWS:
   ```hcl
   provider "aws" {
     region = "us-east-1"
   }
   ```

3. **Configure AWS CLI**
   ```bash
   aws configure
   ```

4. **Terraform Commands**
   ```bash
   terraform init            # Initialize the project
   terraform plan            # Show what will be created/changed
   terraform apply           # Apply changes
   terraform apply -auto-approve  # Apply without manual approval
   ```
