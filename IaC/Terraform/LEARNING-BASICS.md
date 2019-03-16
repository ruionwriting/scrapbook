# Learning the Basics

## Cheat Sheet

### Commands

Simulate the changes. We can user `-out` to specifiy a file to save the plan into.

```shell
terraform plan
```

```shell
terraform plan -out out.terraform
```

```shell
terraform apply out.terraform
```

Run's `plan` and `apply` (recommended for dev only). On completion applies the desired changes into the infrastrucuture.

```shell
terraform apply
```

Destroy all things:

```shell
terraform destroy
```

### AWS

AWS resources `Name` column will have the value defined by the tag `Name`. Example:

```terraform
resource "aws_instance" "example-rui-marques-learning" {
  ami           = "ami-08d658f84a6d84a80"
  instance_type = "t2.micro"
  subnet_id     = "${aws_subnet.eu-west-1a-rui-marques-learning-public.id}"

  tags {
    Name        = "EXAMPLE_RUI_MARQUES_LEARNING"
    OWNER       = "Rui Marques"
    USAGE       = "test/learning"
    BUILT_BY    = "TERRAFORM"
  }
}
```

`ec2_user` is the default user for Amazon Linux and `ubuntu` for Ubuntu Linux.

### Provisioners

> Read the docs: [provisioners](https://www.terraform.io/docs/provisioners/index.html)

1. `file`
1. `chef`
1. `remote-exec`
1. etc

## Errors

1. `Example in getting started guide fails because t2.micro requires a VPC`. The [solution](https://github.com/hashicorp/terraform/issues/4367) is to add the VPC (and subnet) like this:

```terraform
provider "aws" {
  access_key = "ACCESS_KEY_HERE"
  secret_key = "SECRET_KEY_HERE"
  region     = "eu-west-1"
}

resource "aws_instance" "example-rui-marques-learning" {
  ami           = "ami-08d658f84a6d84a80"
  instance_type = "t2.micro"
  subnet_id = "${aws_subnet.eu-west-1a-rui-marques-learning-public.id}"
}

resource "aws_vpc" "example-rui-marques-learning" {
  cidr_block = "10.0.0.0/16"
  enable_dns_hostnames = true
  enable_dns_support = true
}

resource "aws_subnet" "eu-west-1a-rui-marques-learning-public" {
  vpc_id = "${aws_vpc.example-rui-marques-learning.id}"
  cidr_block = "10.0.1.0/25"
  availability_zone = "eu-west-1a"
}
```

## Reminders

1. **What is terraform not?**
  > Terraform is not fit to do configuration management on the software on your machines. Ansible/Chef/Puppet/Salt are better alternatives to do that. Terraform can work together with these tools to provide you CI on your machines. Terraform provides Configuration Management on an infrastructure level, not on the level of software of your machines.
  
## Questions

1. Is it correct to assume that every time we need to change a resource details like SSH key (`key_name`) Terraform will recreate the instance resource?

## Advanced

### Chef Provisioner

- [Using the Chef provisioner with Terraform](https://sdbrett.com/BrettsITBlog/2017/08/using-the-chef-provisioner-with-terraform/)

## Courses

- [Learn DevOps: Infrastructure Automation With Terraform](https://www.udemy.com/learn-devops-infrastructure-automation-with-terraform/)

## Tools

- [Amazon EC2 AMI Locator - Ubuntu](https://cloud-images.ubuntu.com/locator/ec2/)
