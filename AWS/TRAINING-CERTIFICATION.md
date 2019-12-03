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

SSH to EC2 instance:

```shell
chmod 400 <name>.pem
```

1st ensure that only we current user can read the file. Now SSH

```shell
ssh -i <name>.pem ec2-user@<IP>
```
