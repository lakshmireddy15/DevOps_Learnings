
# Terraform and AWS CLI Setup Guide

## AWS CLI Installation and Configuration

1. **Install AWS CLI v2**
2. **Open Git Bash** and configure AWS CLI:
   ```bash
   aws configure
   ```
   Provide the following when prompted:
   - Access Key ID
   - Secret Access Key

## Terraform Commands

1. **Navigate to the Terraform Folder**
2. **Initialize Terraform**
   ```bash
   terraform init
   ```
   - Initializes an empty working directory.
   - Downloads all provider plugins.

3. **Preview Changes**
   ```bash
   terraform plan
   ```
   - Previews the changes Terraform will make to your infrastructure.
   - Use to review changes before applying.

4. **Apply Changes**
   ```bash
   terraform apply
   ```
   - Applies changes based on `.tf` files.
   - Proceeds to create, update, or delete resources.

5. **Skip Confirmation**
   ```bash
   terraform apply -auto-approve
   ```

## Terraform Output and Resource References

- When a resource is created, it can output a value that can be used by other resources.
  ```hcl
  vpc_security_group_ids = aws_security_group.allow_all.id
  ```

## Variables

- Variables are used to assign default values.
- You can override defaults in multiple ways:

### Precedence Order

1. **Command Line**
   ```bash
   terraform plan -var "sg_name=cmd_allow_all"
   ```
2. **`.tfvars` File** (e.g., `variable.tfvars`)
3. **Environment Variables**
   ```bash
   export TF_VAR_sg_name=env_allow_all
   unset TF_VAR_sg_name  # Reset to use default
   ```
4. **Default Values**
5. **Prompt Input**

## Conditions

```hcl
condition ? "this value is true" : "this value is false"
```

## Loops

### 1. Count-Based Loops

- Define count in the resource block.
- Use `count.index` to iterate.

### 2. For Loops

- **Use `count`** for **lists**
- **Use `for_each`** for **maps or sets**
- **Use `dynamic` block** for complex structures

## Interpolation

- Combine variables with strings:
  ```hcl
  "Hello, ${var.name}"
  ```
