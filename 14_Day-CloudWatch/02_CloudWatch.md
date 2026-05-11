## What is CloudWatch? 

- CloudWatch is a monitoring and observability service provided by AWS that allows you to collect and track metrics, collect and monitor log files, set alarms, and automatically react to changes in your AWS resources. It provides insights into the performance and health of your applications and infrastructure.
- It is a free service
- used for Monitoring, Alerting, Tracking and Logging
- It is like a GateKeeper of Watchman for the AWS resources and applications.
- It keeps an eye on the performance and health of your resources and applications, and it can alert you if there are any issues or anomalies. It also allows you to track the performance of your resources and applications over time, so you can identify trends and make informed decisions about how to optimize them. Additionally, it provides logging capabilities, allowing you to collect and analyze log data from your resources and applications for troubleshooting and debugging purposes. Overall, CloudWatch is a powerful tool for monitoring and managing your AWS resources and applications effectively.

- **Reduce-Maintainence** & **Increase-Security**
- Cloud watch does not directly able to scale and cost optimization but informs other resources to do so.
- e.g Lambda functions can apply actions on the basis of cloud watch metrics and alarms to scale up or down the resources.
- Cloud watch is gatekeeper so it tells about the resources status and performance. And other resources can take actions.
- Metrics are the data points that CloudWatch collects and analyzes to provide insights into the performance and health of your resources and applications.
- In organizations, we use the average metric to measure the CPU utilization of an EC2 instance. e.g if the average CPU utilization is above 80% for a certain period of time, we can set an alarm to notify us or trigger an action to scale up the resources.
- If the CPU hits the 100% utilization for just fraction of seconds, it may not be a cause for concern. Though it is an issue but not a critical one.
- On aws, we uses the SNS topic service to send notifications when an alarm is triggered. Simple Notification Service (SNS) is a message delivery service that lets you send messages to users or devices that you specify.
- 


### CloudWatch Metrics
- **Monitoring**: Performance and health of your AWS resources and applications.
- **Real-life metrics**: Actual metrics that you can see in the CloudWatch console.
- **Alarms**: Allows you to set thresholds for your metrics and receive notifications when those thresholds are breached.
- **Log insights**: Allows you to analyze and visualize log data from your resources and applications.
- **Custom metrics**: Allows you to create your own metrics and send them to CloudWatch for monitoring and analysis.
- **Cost Optimizatin**: Helps you optimize your AWS costs by identifying and eliminating unnecessary resources.
