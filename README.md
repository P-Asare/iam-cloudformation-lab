# IAM Automation Lab – CloudFormation

## Overview

This project demonstrates how to automate the creation of AWS IAM resources using **AWS CloudFormation**. It follows security best practices by using **IAM Groups, Secrets Manager, and least privilege access control**.

---

## What This Project Creates

The CloudFormation template provisions the following resources:

### Secrets Manager

* Generates a **temporary password automatically**
* Stores it securely for IAM user login
* Forces users to reset password at first login

---

### IAM Groups

#### 1. S3Group

* Allows users to list S3 buckets only

#### 2. EC2Group

* Allows users to:

    * View EC2 instances
    * Launch EC2 instances

---

### IAM Users

| Username  | Group    | Permissions                          |
| --------- | -------- | ------------------------------------ |
| ec2-user1 | EC2Group | EC2 access (view + create instances) |
| ec2-user2 | EC2Group | EC2 access (view + create instances) |
| s3-user   | S3Group  | S3 access (list buckets only)        |

---

## Security Features

* Passwords are **auto-generated using AWS Secrets Manager**
* Users are forced to **change password on first login**
* Permissions follow **least privilege principle**
* Access is managed via **IAM Groups (not direct user policies)**

---

## Deployment Steps

1. Push the CloudFormation template to a GitHub repository
2. Connect the repository using **AWS CloudFormation GitSync**
3. Deploy the stack from AWS CloudFormation console
4. Retrieve IAM user credentials from Secrets Manager


## 📂 Repository Structure

```
iam-cloudformation-lab/
│
├── iam-template.yaml
└── README.md
```

---

## 🎯 Key Learning Outcomes

* IAM user and group management
* AWS CloudFormation infrastructure automation
* Secure password handling using Secrets Manager
* Applying least privilege access control
* Git-based infrastructure deployment (GitSync)
