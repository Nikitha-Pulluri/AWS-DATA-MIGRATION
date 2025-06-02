# AWS Control Tower and Landing Zones for Cloud Migration

This document explains **AWS Control Tower** and the concept of a **Landing Zone**, especially how they relate to setting up your environment in AWS, particularly for **migration**.

## What is a Landing Zone?

A landing zone is a **well-architected multi-account environment**. It's built following security and compliance best practices. You can think of it as a **zone where you land your workloads** when you migrate or start fresh. It creates a **platform** or foundation that helps your organization quickly launch and deploy applications. A landing zone needs to be **scalable and secure**. Setting one up requires making both **technical and business decisions** about things like your account structure, networking, security, and how access is managed.

A landing zone is a **concept**, not a specific AWS service.

## What is AWS Control Tower?

AWS Control Tower is an AWS service that helps you **set up a landing zone**. Beyond just setting up the landing zone, it also helps you implement best practices in your AWS accounts. Using Control Tower is a **wizard-driven process** that can establish a well-governed, secure, and scalable platform. It can take around 60 to 90 minutes to complete the setup. There is **no charge to use the Control Tower service itself**, but you do pay for the underlying AWS services that it uses or enables, like CloudTrail or AWS Config.

## Key Features of Control Tower

Control Tower offers several important features:

*   **Landing Zone Setup:** It helps you build your initial multi-account structure based on recommended practices.
*   **Guardrails:** These are like rules that implement best practices in your accounts to enforce governance and security. Examples include ensuring that EBS volumes are always encrypted or preventing S3 buckets from being made public. Guardrails can work in preventive and detective ways.
*   **Account Factory:** This provides an easy way to **create new AWS accounts** that are already configured with your organization's defined best practices, security baselines, and guardrails. It uses the Service Catalog service in the background. This feature simplifies giving new teams or developers compliant accounts quickly.
*   **Dashboard:** It gives you a **centralized view** where you can check the compliance status across all your accounts and organizational units in one place.

## What Control Tower Sets Up (Landing Zone Structure)

When you use Control Tower to set up a landing zone, it builds a foundational structure for you:

*   An **AWS Organization** is created, including a **root** and a **management account**. The management account is the one you use to start the Control Tower setup; it's best used only for management tasks and not for running application workloads.
*   It sets up **Organizational Units (OUs)**. It creates a 'security' OU by default, and you can add others for environments like 'dev', 'QA', 'prod', or 'sandbox'.
*   Within the 'security' OU, it creates two specific accounts that need unique email addresses:
    *   **Log Archive account:** This becomes a central location for storing aggregated logs, such as CloudTrail logs, from all the accounts in your organization.
    *   **Audit account:** This is a restricted account designed to allow security and compliance teams to access and audit other accounts within the organization.
*   It can also set up **IAM Identity Center** (which used to be called SSO) to provide a single portal for users to access multiple accounts.
*   It enables services like **CloudTrail** for logging, storing logs centrally in an S3 bucket (optionally with encryption), and can also set up AWS Config and CloudWatch data aggregation.

You must select a **home region** during setup, which is where some configuration will be stored, and **this region cannot be changed later**. You also have the option to deny specific AWS regions across your organization for security or compliance reasons.

## Greenfield vs. Brownfield Deployments

*   **Greenfield:** This term refers to starting completely new in AWS, without existing accounts or infrastructure.
*   **Brownfield:** This refers to building upon or consolidating existing AWS accounts, infrastructure, or organizations.

AWS Control Tower is **suitable for both greenfield and brownfield** deployments. If your organization already has existing AWS accounts or even existing AWS Organizations, you can set up a new landing zone using Control Tower and then **invite your existing accounts** to join the new organization structure managed by Control Tower. This is helpful for bringing together multiple existing environments into a single, well-governed structure.
