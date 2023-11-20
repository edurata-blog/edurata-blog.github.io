---
layout: default
title: Architecture, Security and Quotas
nav_order: 10
---

# Architecture

The main services of the AWS architecture are:

- AWS Secrets manager
- AWS DynamoDB
- AWS Step functions
- AWS S3
- AWS EFS
- AWS Lambda
- AWS ECS Fargate
- AWS VPC

{: .info }
We currently start only ECS Fargate containers which means full isolation of each job (step).

{: .info }
Permissions of executions are scoped by an `execution token` that contains metainformation about the user who triggered the execution. The token is then exchanged for scoped AWS credentials that allow the runner to download/upload and in general communicate with AWS. For now only our runners are supported but support for self-hosted runners is in development.

# Quotas

The most important quotas:

- concurrent running jobs 200 -> can be extended.
-
