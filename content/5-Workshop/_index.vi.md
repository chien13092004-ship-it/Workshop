---
title: "Workshop"
date: 2026-01-01
weight: 5
chapter: false
pre: " <b> 5. </b> "
---


# Triển khai Nền tảng Mua bán Đồ cũ trên AWS

#### Tổng quan

Trong workshop này, chúng ta sẽ xây dựng và triển khai **Nền tảng Mua bán Đồ cũ** trên AWS bằng kiến trúc cloud-native.

Hệ thống sử dụng các dịch vụ AWS bao gồm **Amazon ECS Fargate**, **Amazon ECR**, **Amazon S3**, **AWS CodeBuild**, **Application Load Balancer**, **Amazon CloudWatch**, **AWS IAM**, kết hợp với **MongoDB Atlas** để xây dựng một hệ thống có khả năng mở rộng, bảo mật và triển khai tự động.

Trong workshop này, bạn sẽ từng bước chuẩn bị môi trường, cấu hình các dịch vụ AWS, đóng gói ứng dụng bằng Docker, triển khai ứng dụng lên Amazon ECS Fargate, thiết lập quy trình CI/CD và giám sát hệ thống.

#### Nội dung

1. [Tổng quan về workshop](5.1-Workshop-overview/)
2. [Điều kiện tiên quyết](5.2-Prerequisite/)
3. [Chuẩn bị nền tảng dự án](5.3-Project-foundation/)
4. [Cấu hình mạng VPC](5.4-VPC/)
5. [Cấu hình MongoDB Atlas](5.5-MongoDB-Atlas/)
6. [Tích hợp Amazon S3](5.6-Amazon-S3/)
7. [Quản lý thông tin bí mật với AWS Secrets Manager](5.7-Secrets-Manager/)
8. [Đóng gói ứng dụng bằng Docker](5.8-Docker/)
9. [Đẩy Docker image lên Amazon ECR](5.9-Amazon-ECR/)
10. [Triển khai ứng dụng trên Amazon ECS Fargate](5.10-Amazon-ECS/)
11. [Cấu hình Application Load Balancer](5.11-Application-Load-Balancer/)
12. [Cấu hình Amazon Route 53 và AWS Certificate Manager](5.12-Route53-ACM/)
13. [Thiết lập quy trình CI/CD](5.13-CICD/)
14. [Giám sát và thông báo](5.14-Monitoring/)
15. [Kiểm thử toàn bộ hệ thống](5.15-Testing/)
16. [Dọn dẹp tài nguyên](5.16-Cleanup/)