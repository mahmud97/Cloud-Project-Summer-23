Doctor Support Web App
Overview
This is a Laravel-based web application designed to provide support for doctors. This README outlines the steps to deploy the application on AWS using various services like EC2, RDS, VPC, and S3.

Prerequisites
AWS Account
Basic knowledge of AWS services like EC2, RDS, VPC, and S3
Basic understanding of Laravel and PHP
Terminal access for command-line operations
Deployment Steps
Step 1: Create a VPC
Create a Virtual Private Cloud (VPC) with options to create subnets and Internet Gateways (IGWs) for at least two availability zones.

Step 2: Set Up RDS
Create an RDS instance with MySQL. Choose the VPC created in Step 1 and provide a username and master password for database access.
