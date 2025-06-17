terraform-aws-instance
    variables
    locals
    functions
    resources
    outputs --- instance_id
    data sources
    readme.md 

roboshop-ec2

modules "roboshop" {
    source = "../terraform-aws-instance"
    #mandatory values and values should be given
    var-name = value
    # we can also overide the deafault values

}

output "name" {
    module.roboshop.instance_id  # you will get instance id as a output
}

VPC:

entrance --->village ----> streets ---> Roads
IGW ---->    VPC -------> Subnets ----> Routes

SYS1 ---> SYS2 --->(small connection) CONNECT means networking . He for multiple system connections we use IGW

Example:
pincode ---500032
VPC ---> CIDR
subents -----> streets

32 bits = 4 * 8
why we are creatin 2 availablity zones:
beacuse of disater recovery
1 region altest have 2 availablity zones

manual VPC creation :

VPC ----> vpc only ---> name --> CIDR = 10.0.0.0/16 ---> create vpc
now need to attach IGW
internet gateway ---> name --> Attach to VPC --> create
now we will create subnets
subnets ---> create subnet ---> name ---> name-public--1a ---> subenet cidr block 
=10.0.1.0/24 ---> create
subnets ---> create subnet ---> name ---> name-public--1b ---> subenet cidr block 
=10.0.2.0/24 ---> create

subnets ---> create subnet ---> name ---> name-private--1a ---> subenet cidr block 
=10.0.11.0/24 ---> create
subnets ---> create subnet ---> name ---> name-private--1b ---> subenet cidr block 
=10.0.12.0/24 ---> create

subnets ---> create subnet ---> name ---> name-database--1a ---> subenet cidr block 
=10.0.21.0/24 ---> create
subnets ---> create subnet ---> name ---> name-database--1b ---> subenet cidr block 
=10.0.22.0/24 ---> create

Now we will create route tables for each

route table ---> create route table ---> roboshop public ---> vpc ---> create
public means ----> 0.0.0.0/0 ---> internet notation----> Internet gateway
attach route to public----> vpc ---> route tables ---> edit and attach

Here the request will come from local and internet gateway

route table ---> create route table ---> roboshop private ---> vpc ---> create

route table ---> create route table ---> roboshop database ---> vpc ---> create


---------------------
create VPC
Create IGW
attach VPC to IGW
create 2 public subnets
create 2 private subnets
create 2 database subnets
create public route
add inetrent as a route throught IGW
attach public 1a and public 1b
create private route
attach private 1a and private 1b
create database route
attach database 1a and database 1b


