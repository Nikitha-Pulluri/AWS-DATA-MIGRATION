# AWS Tools for Infrastructure Assessment and Discovery

This document provides a brief overview of two AWS services, **AWS Systems Manager** and **Amazon CloudWatch**, and how they can be useful during the **infrastructure assessment phase**, particularly when preparing for migration. While these services are commonly used, this focuses on their potential for discovering information about your environment.

## AWS Systems Manager

AWS Systems Manager is a service with a **collection of capabilities**. It helps you get **visibility and control** over your resources, including both cloud and **on-premises resources**.

The core idea is installing a **Systems Manager agent** on your physical or virtual machines, whether they are in the cloud or on-premises. Once the agent is installed and configured, it reports information back to the Systems Manager service.

You can use Systems Manager to **collect inventory information** from these machines. This includes details such as:

*   Operating system version and patch level
*   Application configurations
*   Installed applications
*   Other deployment details

Collecting this inventory information can be very **useful when planning to migrate your application**. Systems Manager lets you collect **software configuration and inventory information** about your fleet of servers and the software installed on them. This helps you understand what is available in your environment and what you need to be aware of.

Systems Manager can be useful even if some of your workload is still on-premises, provided those machines have the SSM agent installed and are sending data to the service. You can then **pull inventory reports** from the service to see what is currently running on those machines.

## Amazon CloudWatch

Amazon CloudWatch is primarily a **monitoring and management service**. It is useful for monitoring both your cloud-based resources and **on-premises resources**.

CloudWatch provides **data and actionable insights** from your application and infrastructure resources, whether they are on-premises, hybrid, or in other cloud environments.

Similar to Systems Manager, you can install a **CloudWatch agent** on your servers. This agent can then report information to the CloudWatch service. This information can include performance metrics like:

*   CPU utilization
*   Average performance
*   Peak utilization

Collecting this performance and operational data in the form of **logs and metrics from a single platform** allows for easier access and analysis compared to monitoring in separate systems. If data from your servers, network, and databases is collected by CloudWatch, this information can help you **make informed decisions about your migration**.

Both AWS Systems Manager and Amazon CloudWatch, when their respective agents are installed on servers (including on-premises machines), can provide valuable insights during the assessment phase of migrating your infrastructure.
