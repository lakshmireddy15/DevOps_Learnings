
# Terraform and AWS CLI Setup Guide

## Step 1: Install and Configure AWS CLI

1. **Install AWS CLI v2**
2. Open **Git Bash**, and run:
   ```bash
   aws configure
   ```
   - Enter your **Access Key**
   - Enter your **Secret Key**

## Step 2: Navigate to Terraform Folder

Run the following commands in order:

### Initialize Terraform
```bash
terraform init
```
- This initializes the working directory.
- It will download all required provider plugins.

### Preview Changes
```bash
terraform plan
```
- Used to preview the changes that Terraform will make to your infrastructure.
- Lets you review changes before applying them.

### Apply Changes
```bash
terraform apply
```
- Applies the changes defined in `.tf` configuration files.
- Proceeds to create, update, or delete resources.

### Skip Confirmation
```bash
terraform apply -auto-approve
```
- Skips the manual confirmation step.

## Step 3: Using Outputs from Created Resources

When you create a resource, you can use its output in other resources.  
Example:
```hcl
vpc_security_group_ids = aws_security_group.allow_all.id
```

## Step 4: Variables

- Variables allow you to set default values.
- If you don't want to use default values, you can override them.

### Ways to Override Variables (Precedence Order):

1. **Command Line**
   ```bash
   terraform plan -var "sg_name=cmd_allow_all"
   ```
2. **`.tfvars` File**
   - Use a file like `variables.tfvars` to store variable values.
3. **Environment Variables**
   ```bash
   export TF_VAR_sg_name=env_allow_all
   unset TF_VAR_sg_name  # Unset to fall back to default
   ```
4. **Default Values**
5. **Prompt Input**
   - If no value is provided, Terraform will prompt for it.

## Step 5: Conditions

Use a ternary expression like this:
```hcl
condition ? "this value is true" : "this value is false"
```

## Step 6: Loops

### 1. Count-Based Loops
- Define `count` in the resource block.
- Use `count.index` to iterate over the instances.

### 2. For Loops

Use based on data structure:
- Use `count` if you have a **list**
- Use `for_each` if you have a **map or set**
- Use **dynamic block** for complex nested structures.

## Step 7: Interpolation

- Combine variables with strings using `${}` syntax:
  ```hcl
  "Security group name is ${var.sg_name}"
  ```
