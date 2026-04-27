# AWS Automated Deployment using CloudFormation + GitHub Actions

## Overview
This project automates AWS resource deployment using:
- CloudFormation (Infrastructure as Code)
- GitHub Actions (CI/CD)

## Resources Created
- SNS Topic with email subscription
- AWS Glue (Connection, Workflow, Trigger, Job)
- AWS Secrets Manager Secret

## Prerequisites
- AWS Account
- IAM user with programmatic access
- GitHub repository

## Required GitHub Secrets
Add these in GitHub → Settings → Secrets:

- AWS_ACCESS_KEY_ID
- AWS_SECRET_ACCESS_KEY

## Deployment Steps
1. Push code to `main` branch
2. GitHub Actions will:
   - Validate template
   - Create Change Set
   - Deploy stack
   - Handle updates automatically

## Parameters Used
- Environment (dev/test/prod)
- ResourcePrefix (e.g., myapp)
- AlertEmail

## Best Practices Implemented
- Parameterized templates
- IAM least privilege
- Tagging strategy
- Change sets before deployment
- Rollback detection
- Modular structure

## Assumptions
- Dummy Glue script location used
- Dummy JDBC connection values used
- Email must be confirmed after SNS subscription

## Outputs
- SNS Topic ARN
- Glue Workflow Name
- Secret ARN
