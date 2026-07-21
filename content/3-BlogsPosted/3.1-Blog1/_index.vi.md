---
title: "Blog 1 - Session Policies trong Amazon EKS Pod Identity"
date: 2026-06-29
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

# SESSION POLICIES TRONG AMAZON EKS POD IDENTITY

Amazon EKS Pod Identity hiện hỗ trợ **Session Policies**, cho phép giới hạn quyền IAM cho từng Pod mà không cần tạo nhiều IAM Role khác nhau.

## Những điểm chính cần biết

* Session Policies là các IAM Policy dạng inline.
* Quyền truy cập được giới hạn bởi phần giao nhau giữa IAM Role và Session Policy.
* Session Policies chỉ có thể thu hẹp quyền truy cập.
* Một IAM Role có thể được chia sẻ cho nhiều workload khác nhau.
* Giúp áp dụng nguyên tắc **Least Privilege** (cấp quyền tối thiểu).
* Hỗ trợ cả truy cập cùng tài khoản và khác tài khoản.
* Giảm độ phức tạp trong việc quản lý IAM Role.
* Có thể cấu hình bằng AWS Management Console, AWS CLI hoặc AWS SDK.

Tính năng này giúp Amazon EKS Pod Identity an toàn hơn, có khả năng mở rộng tốt hơn và dễ quản lý hơn trong môi trường Kubernetes.

## Hình ảnh

![Blog 1](/images/blog1.jpg)

## Liên kết

https://www.facebook.com/groups/awsstudygroupfcj/permalink/2203023237129303/?rdid=X5P0romMAosoDmk5#

## Hướng dẫn

https://docs.aws.amazon.com/eks/latest/userguide/pod-identities.html