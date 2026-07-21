---
title: "Blog 3 - Mở rộng quy mô di chuyển AWS Storage Gateway AL2023 bằng Infrastructure as Code"
date: 2026-07-01
weight: 3
chapter: false
pre: " <b> 3.3. </b> "
---

# MỞ RỘNG QUY MÔ DI CHUYỂN AWS STORAGE GATEWAY AL2023 BẰNG INFRASTRUCTURE AS CODE

Amazon Linux 2 sẽ kết thúc hỗ trợ vào năm 2026. AWS khuyến nghị di chuyển các thiết bị Storage Gateway sang Amazon Linux 2023 bằng phương pháp Infrastructure as Code.

## Những điểm chính cần biết

* Terraform triển khai phiên bản EC2 mới.
* Các thiết lập mạng hiện có được tái sử dụng tự động.
* Ansible di chuyển các ổ đĩa EBS.
* Các ổ đĩa bộ nhớ đệm (Cache Disk) được giữ nguyên.
* DNS hoặc Elastic IP được gán lại.
* Gateway ID không thay đổi.
* Thời gian gián đoạn được giảm thiểu.

Giải pháp Infrastructure as Code này tự động hóa quá trình di chuyển Storage Gateway, đồng thời cải thiện khả năng mở rộng và hiệu quả vận hành.

## Hình ảnh

![Blog 3](/images/blog3.jpg)

## Liên kết

https://www.facebook.com/groups/awsstudygroupfcj/permalink/2200302014068092/?rdid=9X5NjrHKM6BsWmWU#

## Hướng dẫn

https://docs.aws.amazon.com/storagegateway/