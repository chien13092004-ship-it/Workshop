---
title: "Blog 3 - Scale AWS Storage Gateway AL2023 Migration with Infrastructure as Code"
date: 2026-07-01
weight: 3
chapter: false
pre: " <b> 3.3. </b> "
---

# SCALE AWS STORAGE GATEWAY AL2023 MIGRATION WITH INFRASTRUCTURE AS CODE

Amazon Linux 2 will reach end of support in 2026. AWS recommends migrating Storage Gateway appliances to Amazon Linux 2023 using Infrastructure as Code.

## Key points to know

* Terraform provisions the new EC2 instance.
* Existing network settings are reused automatically.
* Ansible migrates EBS volumes.
* Cache disks are preserved.
* DNS or Elastic IP is reassigned.
* Gateway ID remains unchanged.
* Downtime is minimized.

This Infrastructure as Code solution automates Storage Gateway migration while improving scalability and operational efficiency.

## Image

![Blog 3](/images/blog3.jpg)

## Link

https://www.facebook.com/groups/awsstudygroupfcj/permalink/2200302014068092/?rdid=9X5NjrHKM6BsWmWU#

## Guide

https://docs.aws.amazon.com/storagegateway/