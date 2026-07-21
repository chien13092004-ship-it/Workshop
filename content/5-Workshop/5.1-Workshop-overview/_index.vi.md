---
title : "Giới thiệu"
date : 2026-01-01
weight : 1
chapter : false
pre : " <b> 5.1. </b> "
---

#### Tổng quan về giải pháp

+ **Nền tảng Mua bán Đồ cũ** là một ứng dụng web cloud-native được triển khai trên AWS. Hệ thống cho phép người dùng đăng ký tài khoản, quản lý sản phẩm, tải lên hình ảnh sản phẩm, tìm kiếm sản phẩm và duyệt sản phẩm theo danh mục thông qua một sàn giao dịch trực tuyến tập trung.
+ Ứng dụng được xây dựng bằng **Node.js**, **Express.js**, **MongoDB Atlas** và **EJS**, trong khi các dịch vụ AWS bao gồm **Amazon ECS Fargate**, **Amazon ECR**, **Amazon S3**, **AWS CodeBuild**, **Application Load Balancer**, **Amazon CloudWatch** và **AWS IAM** cung cấp một nền tảng triển khai có khả năng mở rộng, bảo mật và tự động.

#### Tổng quan về workshop

Trong workshop này, bạn sẽ xây dựng và triển khai một ứng dụng **Nền tảng Mua bán Đồ cũ** theo kiến trúc cloud-native trên AWS.

+ **Tầng ứng dụng (Application Layer)** lưu trữ ứng dụng web chạy trên **Amazon ECS Fargate** phía sau **Application Load Balancer (ALB)** nhằm cung cấp khả năng truy cập có khả năng mở rộng và tính sẵn sàng cao cho người dùng.
+ **Tầng lưu trữ (Storage Layer)** lưu trữ dữ liệu ứng dụng trong **MongoDB Atlas** và hình ảnh sản phẩm trong **Amazon S3**, cung cấp khả năng lưu trữ tập trung và đáng tin cậy.
+ **Quy trình triển khai (Deployment Pipeline)** sử dụng **GitHub**, **AWS CodeBuild** và **Amazon ECR** để tự động xây dựng Docker image và triển khai phiên bản mới nhất của ứng dụng lên **Amazon ECS** mỗi khi mã nguồn mới được đẩy lên GitHub.
+ **Giám sát và bảo mật (Monitoring & Security)** sử dụng **Amazon CloudWatch** để giám sát ứng dụng và **AWS IAM** để quản lý quyền truy cập an toàn đối với các tài nguyên AWS.
