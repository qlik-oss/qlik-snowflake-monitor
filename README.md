> [!IMPORTANT]
> This project is _community supported_. This means that you should not contact
> Qlik Support for help with these apps. See below for additional information
> on how to raise issues on this repository to ask for help.

# Qlik Snowflake Monitor Application

Leveraging Qlik Sense, this app uncovers invaluable insights about your Snowflake costs, usage, inventory, security, performance and contract utilization.

## Installing / Updating

### Installation

1. Install the Qlik Sense application into a monitoring space using the [guided interactive installer](https://community.qlik.com/t5/Official-Support-Articles/Installing-the-Qlik-Snowflake-Monitoring-application-in-Qlik/ta-p/2455224) within Qlik Application Automation, or by manually downloading the [Qlik Sense file](/app/QlikSnowflakeMonitor.qvf) and importing it to your Qlik Cloud tenant.
2. Set up a Snowflake Role/User & Warehouse for collecting monitoring data using the [snowflake monitoring SQL script](/resources/QlikSnowflakeMonitor.sql).
3. Create a Data Connection to your Snowflake instance in the same space as the Snowflake Monitoring app was installed.
    - [Create a Snowflake Connection](https://help.qlik.com/en-US/connectors/Subsystems/ODBC_connector_help/Content/Connectors_ODBC/Snowflake/Create-Snowflake-connection.htm) to the warehouse: `USER: QLIK_MONITORING | ROLE: QLIK_MONITORING_ROLE | WAREHOUSE: MONITORING_WH` which was created by the SQL script you ran in step 2.
    - Save the connection with name `SNOWFLAKE_MONITORING_DATA`.
    - ![Snowflake Settings](/images/screenshot_snowflake_connection.png)
4. Create a REST Connection:
    * Configure target URL: `https://github.com/qlik-oss/qlik-snowflake-monitor/raw/main/manifest.json`.
    * Check the `Allow WITH CONNECTION` checkbox.
    * Save the connection with name `REST Monitoring Versioning API`.
    * ![REST Settings](/images/screenshot_rest_connection.png)

### Updating

Update the Qlik Sense application using the [guided interactive installer](https://community.qlik.com/t5/Official-Support-Articles/Installing-the-Qlik-Snowflake-Monitoring-application-in-Qlik/ta-p/2455224) within Qlik Application Automation, or by manually downloading the [Qlik Sense file](/app/QlikSnowflakeMonitor.qvf) and importing it to your Qlik Cloud tenant into the existing space, and replacing any published copies.

## App Summary

To help Qlik customers manage costs more effectively, Qlik has developed an analytics app designed to provide insights about your Snowflake costs, usage, inventory, security, performance and contract utilization. This app utilizes Qlik's Associative Engine to connect directly to your Snowflake instance and reveal insights from Snowflake's detailed metadata, offering valuable information that traditional query-based tools and Snowflake's own reports are unable to provide.

## Overview

![Overview Page](/images/screenshot_overview.jpg)

The initial entry point of the Snowflake monitor offers an overview of key KPIs being tracked, along with a glimpse of your contract status to ensure spending is aligned. By simply selecting a KPI of interest, you can delve deeper into your Snowflake environment.

Note: This dashboard is compatible with both the Standard and Enterprise versions of Snowflake.

## Cost
![Costs Page](/images/screenshot_cost.jpg)

The Costs view provides a detailed analysis of your expenses over time, allowing you to compare them with previous periods. Dive deep into your costs by examining Users, Databases, Roles, and more to uncover potential cost-saving opportunities within your Snowflake environment. Additionally, explore a value growth perspective to identify areas where costs are either expanding or contracting across key dimensions.

## Usage
![Usage Page](/images/screenshot_usage.jpg)

The Usage dashboard delves into your warehouse and workload activities, analyzing query volumes over time to pinpoint peak usage periods within your warehouses. This insight allows for identifying opportunities to streamline queries across fewer warehouses in your Snowflake environment. Additionally, you can track your most engaged users and the frequency of their queries, providing valuable information on their activity patterns.

## Inventory
![Inventory Page](/images/screenshot_inventory.jpg)

The Inventory sheet offers a comprehensive view of your databases, schemas, tables and views, providing an useful overview of your data and tracking its growth trends. Users can easily filter through their environment to see which inventory items they have access to. Additionally, uncovering unused databases within this view can potentially identify areas where storage costs can be optimized.

## Security
![Security Page](/images/screenshot_security.jpg)

The Security view provides a comprehensive overview of your roles, users, and RBAC permissions, allowing you to identify who has access to specific items. Leveraging the power of the Qlik Associative Engine, this feature enables easy filtering of database objects to understand access control. Additionally, you can track login history trends to monitor how users interact with your system.

## Performance
![Performance Page](/images/screenshot_performance.jpg)

Performance metrics within Snowflake are crucial for optimizing query performance. By analyzing which queries utilize caching and identifying where queries are spilling to remote or local storage, you can effectively optimize your warehouse sizes. Additionally, monitoring warehouse suspend times can help uncover further cost-saving opportunities within your Snowflake environment.

## Support policy

This app is provided as-is and is not supported by Qlik. Over time, the APIs and
metrics used by the app may change, so it is advised to monitor this repository
for updates, and to update the app promptly when new versions are available.

If you have issues while using this app, support is provided on a best-efforts
basis by contributors to this project.

If you have an issue:

* Review the FAQ section in this readme to see if your issue is a common one
* Review open and closed [issues](/../../issues)
* Open a [new issue](/../../issues/new), following the issue template

If you are able to resolve the issue, then close your issue with the resolution,
and if you feel inclined, open a PR with your proposed changes so that we can
consider including the improvement in the next release of the app.

Thank you for your support!
