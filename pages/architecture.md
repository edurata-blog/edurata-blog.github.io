---
layout: default
title: Architecture & Security
nav_order: 9
---

# Architecture

The main services of the AWS architecture are:

- AWS Secrets manager
- AWS DynamoDB
- AWS Step functions
- AWS S3
- AWS EFS
- AWS Lambda
- AWS ECS on EC2 & Fargate
- AWS VPC

{: .info }
Permissions of executions are scoped by an `execution token` that contains metainformation about the user who triggered the execution. The token is then exchanged for scoped AWS credentials that allow the runner to download/upload and in general communicate with AWS. For now only our runners are supported but support for self-hosted runners is in development.
