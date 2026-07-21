---
title: "Workshop"
date: 2026-01-01
weight: 5
chapter: false
pre: " <b> 5. </b> "
---


# Deploying a Second-Hand Marketplace Platform on AWS

#### Overview

In this workshop, we will build and deploy a **Second-Hand Marketplace Platform** using a cloud-native architecture on AWS.

The solution leverages AWS managed services including **Amazon ECS Fargate**, **Amazon ECR**, **Amazon S3**, **AWS CodeBuild**, **Application Load Balancer**, **Amazon CloudWatch**, **AWS IAM**, **AWS Secrets Manager**, **Amazon Route 53**, and **AWS Certificate Manager (ACM)**, integrated with **MongoDB Atlas** to provide a scalable, secure, highly available, and automated deployment platform.

Throughout this workshop, you will prepare the project environment, configure AWS infrastructure, integrate external services, containerize the application using Docker, deploy it to Amazon ECS Fargate, configure CI/CD, monitor system performance, and perform end-to-end testing.

#### Content

1. [Workshop overview](5.1-Workshop-overview/)
2. [Prerequisite](5.2-Prerequisite/)
3. [Prepare project foundation](5.3-Project-foundation/)
4. [Configure VPC networking](5.4-VPC/)
5. [Configure MongoDB Atlas](5.5-MongoDB-Atlas/)
6. [Integrate Amazon S3](5.6-Amazon-S3/)
7. [Manage secrets with AWS Secrets Manager](5.7-Secrets-Manager/)
8. [Dockerize the application](5.8-Docker/)
9. [Push Docker image to Amazon ECR](5.9-Amazon-ECR/)
10. [Deploy the application on Amazon ECS Fargate](5.10-Amazon-ECS/)
11. [Configure Application Load Balancer](5.11-Application-Load-Balancer/)
12. [Configure Amazon Route 53 and AWS Certificate Manager](5.12-Route53-ACM/)
13. [Configure CI/CD](5.13-CICD/)
14. [Monitoring and notifications](5.14-Monitoring/)
15. [End-to-end testing](5.15-Testing/)
16. [Clean up resources](5.16-Cleanup/)