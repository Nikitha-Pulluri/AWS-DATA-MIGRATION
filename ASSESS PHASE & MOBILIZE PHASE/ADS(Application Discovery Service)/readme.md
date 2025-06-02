# Application Discovery Service (ADS)

Understanding your current environment is a key step in planning your cloud migration. The **Application Discovery Service**, often called ADS, helps with this.

## What ADS Does

ADS collects details about your on-premise servers and databases. This includes information like:

*   Server names, IP addresses, and hardware specs.
*   Resource use like CPU, memory, and disk.
*   Database types and versions.
*   **Network connections** between servers.

This collected information is used for planning your migration. It can help you map dependencies between applications.

## How to Collect Data

ADS offers several ways to gather data from your data center:

*   **Agent-based collector**: Install a small software agent directly on supported Windows and Linux servers. This agent collects data every fifteen minutes. It can capture network connections and running processes.
*   **Agentless collector**: For VMware vCenter environments, you can deploy a virtual machine that collects data from vCenter without installing agents on individual VMs. This is faster to get started. It sends data every sixty minutes and can discover database types, but doesn't capture network connections or running processes within the OS.
*   **Import**: You can also import existing inventory data from files (like CSV) that you might have gathered using other tools or processes.

## Where the Data Goes

Data collected by ADS is sent to **AWS Migration Hub**. Migration Hub is a central place for managing migration processes.

You must set a **Home Region** in Migration Hub, which is where your collected data will be stored. This is important for compliance and security.

From Migration Hub, you can:

*   **View and monitor** the collected server and application data.
*   **Group servers into applications** based on logical relationships, not just physical servers.
*   **Visualize network connections** between servers.

Optionally, you can enable **Athena Export**. This automatically sends your collected data to an Amazon S3 bucket. Once in S3, you can use services like:

*   **Amazon Athena**: Run SQL queries on your data.
*   **Amazon QuickSight**: Create dashboards and visualize your infrastructure data.

Setting up Athena Export involves deploying other AWS services like Kinesis Data Firehose and AWS Glue, which may incur costs.

## Getting Started

ADS is generally a **free service**. However, using features like Athena Export may cost money.

ADS is accessed through the **AWS console**, specifically via Migration Hub. It is considered a **self-service** tool.

To use ADS, you need:

*   An AWS account.
*   Credentials (an IAM user with specific permissions) for the collector software to send data. A managed policy called `ApplicationDiscoveryAgentAccess` is available.

Installing agents involves downloading and running software, providing your credentials, and ensuring network connectivity to the ADS endpoint. Automation tools are recommended for installing agents on many servers.

This tool is aligned with the **Assess** and **Mobilize** phases of migration.
