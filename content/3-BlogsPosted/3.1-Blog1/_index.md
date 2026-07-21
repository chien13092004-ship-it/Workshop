---
title: "Blog 1 - Session Policies in Amazon EKS Pod Identity"
date: 2026-06-29
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

# SESSION POLICIES IN AMAZON EKS POD IDENTITY

Amazon EKS Pod Identity now supports Session Policies, allowing IAM permissions to be restricted for individual pods without creating multiple IAM roles.

## Key points to know

* Session Policies are inline IAM policies.
* Permissions are limited by the intersection of the IAM Role and the Session Policy.
* Session Policies can only reduce permissions.
* A single IAM Role can be shared across multiple workloads.
* Helps implement the Principle of Least Privilege.
* Supports both same-account and cross-account access.
* Reduces IAM Role management complexity.
* Can be configured using the AWS Console, CLI or SDK.

This feature makes Amazon EKS Pod Identity more secure, scalable and easier to manage in Kubernetes environments.

## Image

![Blog 1](/images/blog1.jpg)

## Link

https://www.facebook.com/groups/awsstudygroupfcj/permalink/2203023237129303/?rdid=X5P0romMAosoDmk5#

## Guide

https://docs.aws.amazon.com/eks/latest/userguide/pod-identities.html