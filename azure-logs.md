### [Azure monitor and logging](https://docs.microsoft.com/en-us/azure/azure-monitor/overview)

Logging and monitoring the health of your services is a vital component of production applications. You need to be able to determine the causes of failures. You also need to identify any problems before they occur.

Azure Monitor is an important tool to help you in this process. It enables you to gather monitoring and diagnostic information about the health of your services. You can use this information to visualize and analyze the causes of problems that might occur in your app.

Azure Monitor collects two fundamental types of data: metrics and logs. Metrics tell you how the resource is performing, and the other resources that it's consuming. Logs contain records that show when resources are created or modified.

![Azure monitoring](https://docs.microsoft.com/en-us/learn/modules/analyze-infrastructure-with-azure-monitor-logs/media/2-azure-monitor.svg)

Because Azure Monitor is an automatic system, it begins to collect data from these sources as soon as you create Azure resources such as virtual machines and web apps. You can extend the data that Azure Monitor collects by:

Enabling diagnostics: For some resources, such as Azure SQL Database, you receive full information about a resource only after you have enabled diagnostic logging for it. You can use the Azure portal, the Azure CLI, or PowerShell to enable diagnostics.
Adding an agent: For virtual machines, you can install the Log Analytics agent and configure it to send data to a Log Analytics workspace. This agent increases the amount of information that's sent to Azure Monitor.

You use the Kusto Query Language to query log information for your services running in Azure. A Kusto query is a read-only request to process data and return results.
