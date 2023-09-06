
# Doctor Support Web App

This is a Laravel-based web application designed to provide support for doctors. This README outlines the steps to deploy the application on AWS.

## Table of Contents

- [Prerequisites](#prerequisites)
- [Deployment Steps](#deployment-steps)
  - [Step 1: VPC Setup](#step-1-vpc-setup)
  - [Step 2: RDS Setup](#step-2-rds-setup)
  - [Step 3: EC2 Setup](#step-3-ec2-setup)
  - [Step 4: Initial Server Setup](#step-4-initial-server-setup)
  - [Step 5: Download Laravel App](#step-5-download-laravel-app)
  - [Step 6: Move Files](#step-6-move-files)
  - [Step 7: S3 Bucket](#step-7-s3-bucket)
  - [Step 8: IAM User](#step-8-iam-user)
  - [Step 9: .env Configs 1](#step-9-env-configs-1)
  - [Step 10: .env Configs 2](#step-10-env-configs-2)
  - [Step 11: Composer and Key](#step-11-composer-and-key)
  - [Step 12: RDS Security Group](#step-12-rds-security-group)
  - [Step 13: Database Setup](#step-13-database-setup)
  - [Step 14: Final Commands](#step-14-final-commands)
  - [Step 15: Apache Configuration](#step-15-apache-configuration)
  - [Step 16: Test](#step-16-test)
  - [Step 17: Admin Setup](#step-17-admin-setup)
- [Additional Steps](#additional-steps)

## Prerequisites

- AWS Account
- Basic knowledge of AWS services like VPC, RDS, EC2, and S3
- Basic understanding of Laravel and PHP
- Terminal access to run commands

## Deployment Steps

### Step 1: VPC Setup

Create a Virtual Private Cloud (VPC) with options to create subnets and Internet Gateways (IGWs) for at least two availability zones.

### Step 2: RDS Setup

Create a MySQL database using Amazon RDS within the VPC created in Step 1. Make sure to select "No public access" and provide a username and master password.

### Step 3: EC2 Setup

Create an Ubuntu EC2 instance in the same VPC and configure its security group to allow HTTP and HTTPS traffic.

### Step 4: Initial Server Setup

Open the terminal of the created EC2 instance and run the following commands:

```bash
sudo apt update -y
sudo apt install apache2 -y
sudo apt install --no-install-recommends php8.1 -y


### Step 5: Download Laravel App

Run the following command to download the Laravel app from GitHub:

```bash
wget https://github.com/mahmud97/Cloud-Project-Summer-23.git
```

### Step 6: Move Files

Move the downloaded Laravel files to the Apache web root directory (`/var/www/html`).

### Step 7: S3 Bucket

Create an Amazon S3 bucket for storing files.

### Step 8: IAM User

Create an IAM user with AmazonS3FullAccess policy and generate access keys.

### Step 9: .env Configs 1

Configure the `.env` file for the Laravel application with basic settings and database credentials.

### Step 10: .env Configs 2

Add AWS S3 and IAM user credentials to the `.env` file.

### Step 11: Composer and Key

Update Composer packages and generate an application key for Laravel.

### Step 12: RDS Security Group

Create and assign a new security group to the RDS instance.

### Step 13: Database Setup

Connect to the RDS MySQL database and create a new database.

### Step 14: Final Commands

Run Laravel migrations and set permissions.

### Step 15: Apache Configuration

Create a new Apache site configuration for the Laravel application.

### Step 16: Test

Access the web app using the EC2 instance's public IP to verify the deployment.

### Step 17: Admin Setup

Insert an admin user into the database for initial testing.


