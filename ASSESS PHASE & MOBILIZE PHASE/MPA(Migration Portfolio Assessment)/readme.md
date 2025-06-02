# Migration Portfolio Assessment (MPA)

When planning a move to the cloud, it's essential to assess your current environment and create a solid plan. The **Migration Portfolio Assessment tool**, or **MPA**, is designed for this purpose.

It is a **partner only tool**. Only specific types of AWS partners, not every partner, have access to it. It is not available directly to customers through the standard AWS console.

## What MPA Does

MPA helps partners work with customers during the **assess and mobilize phases** of a cloud migration. It aligns with planning activities during the mobilize phase.

The core function of MPA is **analysis, normalization, and planning**. It is crucial to understand that **this tool is not a data collection tool itself**.

## How Data Gets into MPA

Since MPA does not collect data, you must **feed data into it** from other sources. This data describes your on-premise environment. You can bring data collected separately using:

*   **Application Discovery Service (ADS)**
*   **Migration Evaluator (formerly TSO Logic)**
*   **Exported files** in standard formats like CSV or Excel from other tools or your CMDB.

You import this data into the MPA tool. You may need to resolve any issues or outliers found in the data during the import process, and you can map header information from your files if it doesn't match the tool's expected format.

## Key Capabilities and Features

Once data is imported, MPA provides several powerful capabilities:

*   **Business Case Creation**: Generate a business case to justify migrating to AWS. This includes estimating cost savings compared to running things on-premise.
*   **Total Cost of Ownership (TCO) Calculation**: Analyze your current on-premise costs (including power, manpower, hardware refresh) and estimate your potential costs on AWS. You can compare scenarios based on different regions or timeframes.
*   **Instance Recommendations**: Get recommendations for AWS EC2 instance types and database services based on the utilization and characteristics of your on-premise servers. This includes suggestions for payment options like On-Demand, Reserved Instances, or Savings Plans.
*   **Migration Planning**:
    *   **Application Prioritization**: Help decide which applications should be migrated first based on business criticality or other factors you define.
    *   **Dependency Grouping**: Create groups of applications and servers that depend on each other and need to be migrated together to ensure they continue to function.
    *   **Migration Wave Planning**: Plan migration activities over time by organizing applications into migration waves.
*   **Data Normalization**: Identify and handle data outliers to ensure accurate calculations and planning.
*   **Scenario Comparison**: Compare different migration scenarios (e.g., migrating to different AWS regions, using different instance types) to see how they impact cost estimations and recommendations.
*   **Assumption Management**: Review and modify underlying assumptions (like hardware refresh cycles, analysis duration, labor costs) that the tool uses for its calculations, and see how changes impact the outputs.

You can also view imported data and analysis through predefined or custom **dashboards**.

## Accessing MPA

MPA is a web-based tool with a separate user interface. You access it through a specific portal, not the main AWS console. You typically need an employee or a **partner central member** login to gain access.

Within the tool, partners can create separate **portfolios** to keep data organized, especially when working with multiple customers or departments.

In summary, MPA is a sophisticated tool available to specific AWS partners that takes data from other discovery sources to analyze environments, build business cases based on estimated costs, and create detailed migration plans.
