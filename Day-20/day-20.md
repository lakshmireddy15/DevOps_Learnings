# terraform-aws-instance

- **variables**  
- **locals**  
- **functions**  
- **resources**  
- **outputs** --- instance_id  
- **data sources**  
- **readme.md**

---

# roboshop-ec2

```hcl
modules "roboshop" {
    source = "../terraform-aws-instance"
    #mandatory values and values should be given
    var-name = value
    # we can also overide the deafault values
}

output "name" {
    module.roboshop.instance_id  # you will get instance id as a output
}
```

---

# VPC:

**entrance ---> village ----> streets ---> Roads**  
**IGW ----> VPC -------> Subnets ----> Routes**

SYS1 ---> SYS2 --->(small connection) CONNECT means networking.  
Here for multiple system connections we use IGW

### Example:
- **pincode** --- 500032  
- **VPC** ---> CIDR  
- **subnets** -----> streets

**32 bits = 4 * 8**  
**Why we are creating 2 availability zones:**  
Because of disaster recovery  
1 region at least has 2 availability zones

---

## Manual VPC creation:

- VPC ----> vpc only ---> name --> CIDR = 10.0.0.0/16 ---> create vpc  
- Now need to attach IGW  
  - Internet gateway ---> name --> Attach to VPC --> create  

### Now we will create subnets:

- subnets ---> create subnet ---> name ---> name-public--1a ---> subnet CIDR block = 10.0.1.0/24 ---> create  
- subnets ---> create subnet ---> name ---> name-public--1b ---> subnet CIDR block = 10.0.2.0/24 ---> create  

- subnets ---> create subnet ---> name ---> name-private--1a ---> subnet CIDR block = 10.0.11.0/24 ---> create  
- subnets ---> create subnet ---> name ---> name-private--1b ---> subnet CIDR block = 10.0.12.0/24 ---> create  

- subnets ---> create subnet ---> name ---> name-database--1a ---> subnet CIDR block = 10.0.21.0/24 ---> create  
- subnets ---> create subnet ---> name ---> name-database--1b ---> subnet CIDR block = 10.0.22.0/24 ---> create  

---

### Now we will create route tables for each:

- route table ---> create route table ---> roboshop public ---> vpc ---> create  
  - public means ----> 0.0.0.0/0 ---> internet notation ----> Internet gateway  
  - attach route to public ----> vpc ---> route tables ---> edit and attach  
  - Here the request will come from local and internet gateway  

- route table ---> create route table ---> roboshop private ---> vpc ---> create  
- route table ---> create route table ---> roboshop database ---> vpc ---> create  

---

### Summary:

- create VPC  
- Create IGW  
- attach VPC to IGW  
- create 2 public subnets  
- create 2 private subnets  
- create 2 database subnets  
- create public route  
- add internet as a route through IGW  
- attach public 1a and public 1b  
- create private route  
- attach private 1a and private 1b  
- create database route  
- attach database 1a and database 1b  
