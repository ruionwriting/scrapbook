# Tranning and Certification

## AWS Certified Developer - Associate

Certification details: https://aws.amazon.com/certification/certified-developer-associate/

Exam guide: https://d1.awsstatic.com/training-and-certification/docs-dev-associate/AWS_Certified_Developer_Associate-Exam_Guide_EN_1.4.pdf

Learning progress (completed):

- [AWS Developer: The Big Picture](https://app.pluralsight.com/library/courses/aws-developer-big-picture/table-of-contents). Pluralsight course.

### Learning Notes (temp)

Test AWS CLI credentials:
  
```shell
aws ec2 describe-instances --profile **PROFILE-NAME**
{
  "Reservations": []
}
```

Download keys and SSH to EC2 instance:

```shell
chmod 400 <pem-file>
```

1st ensure that only we current user can read the file. Now SSH

```shell
ssh -i <pem-file> ec2-user@<ec2-ip>
```

Installing Node, before updating OS:

```shell
sudo yum update
```

Add source repository:

```shell
$ curl -sL https://rpm.nodesource.com/setup_12.x | sudo bash -

...

## Run `sudo yum install -y nodejs` to install Node.js 12.x and npm.
## You may also need development tools to build native addons:
     sudo yum install gcc-c++ make
## To install the Yarn package manager, run:
     curl -sL https://dl.yarnpkg.com/rpm/yarn.repo | sudo tee /etc/yum.repos.d/yarn.repo
     sudo yum install yarn
```

Copy sample Node project to EC2 instance:

```shell
scp -r -i <pem-file> ./<project-folder> ec2-user@<ec2-ip>:/home/ec2-user/<project-name>
```

Add load to test ASG (using ApacheBench on macOS against DNS name A-Record):

> We might need to [Enable Auto Scaling Group Metrics](https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-instance-monitoring.html#as-enable-group-metrics).

> We can use any other tool (Postman, for example).

```shell
ab -n 100 -c 5 http://LOAD_BALANCER_DNS_NAME/
```

