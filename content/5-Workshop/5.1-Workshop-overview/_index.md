---
title : "Introduction"
date : 2026-01-01
weight : 1
chapter : false
pre : " <b> 5.1. </b> "
---

#### Solution overview

+ **Second-Hand Marketplace Platform** is a cloud-native web application deployed on AWS. It enables users to register accounts, manage products, upload product images, search products, and browse categories through a centralized online marketplace.
+ The application is built using **Node.js**, **Express.js**, **MongoDB Atlas**, and **EJS**, while AWS services including **Amazon ECS Fargate**, **Amazon ECR**, **Amazon S3**, **AWS CodeBuild**, **Application Load Balancer**, **Amazon CloudWatch**, and **AWS IAM** provide a scalable, secure, and automated deployment platform.

#### Workshop overview

In this workshop, you will build and deploy a cloud-native Second-Hand Marketplace application on AWS.

+ **Application Layer** hosts the web application running on **Amazon ECS Fargate** behind an **Application Load Balancer (ALB)** to provide scalable and highly available access for users.
+ **Storage Layer** stores application data in **MongoDB Atlas** and product images in **Amazon S3**, providing reliable and centralized storage.
+ **Deployment Pipeline** uses **GitHub**, **AWS CodeBuild**, and **Amazon ECR** to automatically build Docker images and deploy the latest application version to Amazon ECS whenever new source code is pushed.
+ **Monitoring & Security** uses **Amazon CloudWatch** for application monitoring and **AWS IAM** for secure access management across AWS resources.

