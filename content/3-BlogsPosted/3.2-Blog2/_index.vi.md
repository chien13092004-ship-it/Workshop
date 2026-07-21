---
title: "Blog 2 - Tự động hóa phân tích hợp đồng với Doczy.ai trên AWS"
date: 2026-06-30
weight: 2
chapter: false
pre: " <b> 3.2. </b> "
---

# TỰ ĐỘNG HÓA PHÂN TÍCH HỢP ĐỒNG VỚI DOCZY.AI TRÊN AWS

Doczy.ai™ là nền tảng phân tích tài liệu sử dụng Trí tuệ nhân tạo (AI), giúp tự động hóa quá trình phân tích hợp đồng bằng các dịch vụ Generative AI của AWS. Nền tảng này cải thiện đáng kể độ chính xác trong việc trích xuất dữ liệu so với các hệ thống truyền thống dựa trên quy tắc.

## Những điểm chính cần biết

* Amazon Cognito xác thực người dùng.
* Amazon S3 lưu trữ các hợp đồng được tải lên.
* AWS Lambda kích hoạt Amazon Textract.
* Amazon Textract trích xuất văn bản và siêu dữ liệu.
* Smart Chunking giúp bảo toàn cấu trúc tài liệu.
* Amazon ECS chạy các tác vụ AI.
* Amazon Bedrock thực hiện phân tích hợp đồng.
* Snowflake lưu trữ dữ liệu đã được xử lý.
* Amazon CloudWatch giám sát hệ thống.
* AWS Secrets Manager bảo vệ thông tin xác thực.

Kiến trúc này minh họa cách các dịch vụ AI của AWS giúp nâng cao khả năng xử lý tài liệu và phân tích hợp đồng trong doanh nghiệp.

## Hình ảnh

![Blog 2](/images/blog2.jpg)

## Liên kết

https://www.facebook.com/groups/awsstudygroupfcj/permalink/2199556717475955/?rdid=PDmR1hagSXBb7pXj#

## Hướng dẫn

https://docs.aws.amazon.com/bedrock/