# React Static Website Deployment on AWS with Terraform

This project demonstrates how to deploy a React static website to **Amazon S3**, with **CloudFront** as a CDN, all managed using **Terraform**.

## ��� Live URLs

- **CloudFront CDN URL:** [https://d12215vuojrebb.cloudfront.net](https://d12215vuojrebb.cloudfront.net)
- **S3 Static Website URL:** [http://my-react-bucket-0621.s3-website-us-east-1.amazonaws.com](http://my-react-bucket-0621.s3-website-us-east-1.amazonaws.com)

---

## ��� Project Structure
.
├── main.tf                # Terraform configuration for S3, CloudFront, and IAM

├── variables.tf           # Input variable definitions

├── outputs.tf             # Output values like URLs

├── build/                 # Production-ready React app files (after `npm run build`)

└── README.md              # Project documentation
���️ Prerequisites

AWS CLI configured (aws configure --profile terraformuser)

Terraform installed

Node.js & npm installed

A working React project (npx create-react-app my-app)

��� Deployment Steps

**1. Build the React App**
```bash
npm install
npm run build
```
**2. Initialize Terraform**
```bash
terraform init
```
**3. Apply Infrastructure**
```bash
terraform apply -auto-approve
```
You will be prompted to enter the bucket name, e.g., my-react-bucket-0621.
![Screenshot (247)](https://github.com/user-attachments/assets/6fceda3a-0da8-4fd9-b2b6-b0adcf0a0c8a)

**4. Upload Build Files to S3**
```bash
aws s3 sync build/ s3://my-react-bucket-0621 --profile terraformuser
```

��� Tear Down
To destroy all provisioned AWS resources:
```bash
terraform destroy -auto-approve
```

��� Notes
aws_s3_bucket_public_access_block is configured to allow public access.

CloudFront is used for HTTPS and global distribution.

All resources are deployed to the us-east-1 region.


**⚠️ Challenges Faced**

**S3 Bucket Naming Conflict**: Encountered a BucketAlreadyExists error due to global uniqueness constraint.

**Permissions Error**: Access denied errors when applying the bucket policy due to BlockPublicPolicy being enabled by default. Solved by explicitly setting aws_s3_bucket_public_access_block.

**AWS Account Confusion**: Initially deployed to an unintended AWS account. Fixed by properly configuring a named profile (terraformuser) with correct credentials.

**Missing Build Folder**: After uninstalling the React app, the build/ directory was missing, requiring re-creation of the app and rebuild.

**Slow Installations**: npm install was slow due to network conditions or large dependencies.

**Terraform Resource Duplication**: Duplicate aws_s3_bucket_policy declarations caused initialization errors. Solved by cleaning up redundant blocks.
![Screenshot (246)](https://github.com/user-attachments/assets/b0848f36-0c9f-45c2-a679-72b4c6dbbcc6)


