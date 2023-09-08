<!DOCTYPE html>
<html>

<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>aws cloudwatch</title>
  <link rel="stylesheet" href="https://stackedit.io/style.css" />
</head>

<body class="stackedit">
  <div class="stackedit__html"><h2 id="amazon-cloudwatch">Amazon CloudWatch</h2>
<p>Amazon CloudWatch is a service used for monitoring and observing resources in real-time, built for DevOps engineers, developers, site reliability engineers (SREs), and IT managers. CloudWatch provides users with data and actionable insights to monitor their respective applications, stimulate system-wide performance changes, and optimize resource utilization. CloudWatch collects monitoring and operational data in the form of logs, metrics, and events, providing its users with an aggregated view of AWS resources, applications, and services that run on AWS. The CloudWatch can also be used to detect anomalous behavior in the environments, set warnings and alarms, visualize logs and metrics side by side, take automated actions and troubleshoot issues.</p>
<h3 id="terminologies-related-to-amazon-cloudwatch"><strong>Terminologies related to Amazon Cloudwatch</strong></h3>
<h4 id="metrics"><strong>Metrics</strong></h4>
<ul>
<li>It represents a time-ordered set of data points that are published to Amazon CloudWatch</li>
<li>All data point is marked with a timestamp</li>
<li>Metric is a variable that is monitored and data points are the value of that variable over time</li>
<li>They are uniquely defined by a name, namespace, and zero or more dimensions</li>
<li>Metric math is used to query multiple cloudwatch metrics and use math expressions to create new time-series based on these metrics</li>
</ul>
<h4 id="dimensions"><strong>Dimensions</strong></h4>
<ul>
<li>A dimension is a name/value pair which uniquely identifies a metric</li>
<li>Dimensions are the unique identifiers for a metric, so whenever you add a unique name/value pair to one of the metrics, you are creating a new variation of that metric.</li>
</ul>
<h4 id="statistics"><strong>Statistics</strong></h4>
<ul>
<li>Statistics are metric data aggregations over specified periods of time</li>
<li>The few available statistics on Cloudwatch are maximum, minimum, sum, average, and sample count.</li>
</ul>
<h4 id="alarm"><strong>Alarm</strong></h4>
<ul>
<li>It is used to automatically initiate actions on our behalf</li>
<li>It watches a single metric over a specified time period and performs one or more specified actions based on the value of the metric</li>
<li>The estimated AWS charges can also be monitored using the alarm</li>
</ul>
<h4 id="percentiles"><strong>Percentiles</strong></h4>
<ul>
<li>It represents the relative weightage of the data in a dataset</li>
<li>It helps the user to get a better understanding of the distribution of metric data</li>
</ul>
<h4 id="cloudwatch-dashboard"><strong>Cloudwatch dashboard</strong></h4>
<ul>
<li>A user-friendly Cloudwatch console is available which is used for monitoring resources in a single view.</li>
<li>There is no limit on the number of cloudwatch dashboards you can create.</li>
<li>These dashboards are global and not region-specific</li>
</ul>
<h4 id="cloudwatch-agent"><strong>Cloudwatch agent</strong></h4>
<ul>
<li>It is required to be installed</li>
<li>It collects logs and system-level metrics from EC2 instances and on-premises servers</li>
</ul>
<h4 id="cloudwatch-events"><strong>Cloudwatch Events:</strong></h4>
<ul>
<li>Cloudwatch events help you to create a set of rules that match with any event(i.e stopping of EC2 instance).</li>
<li>These events can be routed to one or more targets like AWS Lambda functions, Amazon SNS Topics, Amazon SQS queues, and other target types.</li>
<li>Cloudwatch Events observes the operational events continuously and whenever there is any change in the state of the event, it performs the action by sending notifications, activating lambda, etc.</li>
<li>An  <strong>event</strong>  indicates a change in the AWS environment. Whenever there is a change in the state of AWS resources, events are generated.</li>
<li><strong>Rules</strong>  are used for matching events and routing to targets.</li>
<li><strong>Target</strong> process events. They include Amazon EC2 instances, AWS Lambda functions, etc. A target receives the events in JSON format.</li>
</ul>
<h4 id="cloudwatch-logs"><strong>Cloudwatch logs:</strong></h4>
<ul>
<li>Amazon Cloudwatch logs enable you to store, monitor, and access files from AWS resources like Amazon EC2 instances, Route53, etc.</li>
<li>It also helps you to troubleshoot your system errors and maintain the logs in highly durable storage.</li>
<li>It also creates log of information about the DNS queries that Route 53 receives</li>
</ul>
<h3 id="amazon-cloudwatch-create">Amazon Cloudwatch Create</h3>
<p>Notifying  <em>gfg</em>  website management team when the instance on which  <em>gfg</em> website is hosted stops Whenever the CPU utilization of instance (on which GeeksForGeeks website is hosted ) goes above 80%, cloudwatch event is triggered. This cloudwatch event then activates the SNS topic which sends the alert email to the attached  <em>gfg</em> subscribers.</p>
<p><strong>Step 1:</strong> Let us assume that you have already launched an instance with the name tag ‘instance’.</p>
<p><a href="https://media.geeksforgeeks.org/wp-content/uploads/20200706210304/image1.jpg"><img src="https://media.geeksforgeeks.org/wp-content/uploads/20200706210304/image1.jpg" alt=""></a></p>
<p><strong>Step 2:</strong>  Go to SNS topic dashboard and click on create a topic</p>
<p><a href="https://media.geeksforgeeks.org/wp-content/uploads/20200706210012/image2.jpg"><img src="https://media.geeksforgeeks.org/wp-content/uploads/20200706210012/image2.jpg" alt=""></a></p>
<p><strong>Step 3:</strong>  You will be directed to this dashboard. Now specify the name and display name.</p>
<p><a href="https://media.geeksforgeeks.org/wp-content/uploads/20200706210014/image3.jpg"><img src="https://media.geeksforgeeks.org/wp-content/uploads/20200706210014/image3.jpg" alt=""></a></p>
<p><strong>Step 4:</strong> Scroll down and click on create the topic.</p>
<p><a href="https://media.geeksforgeeks.org/wp-content/uploads/20200706210015/image4.jpg"><img src="https://media.geeksforgeeks.org/wp-content/uploads/20200706210015/image4.jpg" alt=""></a></p>
<p><strong>Step 5:</strong>  The SNS topic is created successfully.</p>
<p><a href="https://media.geeksforgeeks.org/wp-content/uploads/20200707111723/image51.jpg"><img src="https://media.geeksforgeeks.org/wp-content/uploads/20200707111723/image51.jpg" alt=""></a></p>
<p><strong>Step 6:</strong> Go to the SNS topic dashboard and click on  <em>gfgtopic</em> link.</p>
<p><a href="https://media.geeksforgeeks.org/wp-content/uploads/20200706210018/image6.jpg"><img src="https://media.geeksforgeeks.org/wp-content/uploads/20200706210018/image6.jpg" alt=""></a></p>
<p><strong>Step 7</strong>: Under the subscriptions section, Click on Create subscription.</p>
<p><a href="https://media.geeksforgeeks.org/wp-content/uploads/20200706210019/image7.jpg"><img src="https://media.geeksforgeeks.org/wp-content/uploads/20200706210019/image7.jpg" alt=""></a></p>
<p><strong>Step 8</strong>: Select  <strong>Email</strong> as protocol and specify the email address of subscribers in Endpoint. Click on create the subscription. Now Go to the mailbox of the specified email id and click on Subscription confirmed.</p>
<p><a href="https://media.geeksforgeeks.org/wp-content/uploads/20200706213053/image81.jpg"><img src="https://media.geeksforgeeks.org/wp-content/uploads/20200706213053/image81.jpg" alt=""></a></p>
<p><strong>Step 9:</strong>  Go to the cloudwatch dashboard on the AWS management console. Click on Metrics in the left pane.</p>
<p><a href="https://media.geeksforgeeks.org/wp-content/uploads/20200706210024/image11.jpg"><img src="https://media.geeksforgeeks.org/wp-content/uploads/20200706210024/image11.jpg" alt=""></a></p>
<p><strong>Step 10</strong>: In  <strong>All metrics</strong>  section click on EC2</p>
<p><a href="https://media.geeksforgeeks.org/wp-content/uploads/20200706210026/image12.jpg"><img src="https://media.geeksforgeeks.org/wp-content/uploads/20200706210026/image12.jpg" alt=""></a></p>
<p><strong>Step 11</strong>: Click on Per-instance metrics</p>
<p><a href="https://media.geeksforgeeks.org/wp-content/uploads/20200706210027/image13.jpg"><img src="https://media.geeksforgeeks.org/wp-content/uploads/20200706210027/image13.jpg" alt=""></a></p>
<p><strong>Step 12</strong>: Select the instance you launched</p>
<p><a href="https://media.geeksforgeeks.org/wp-content/uploads/20200706210030/image15.jpg"><img src="https://media.geeksforgeeks.org/wp-content/uploads/20200706210030/image15.jpg" alt=""></a></p>
<p><strong>Step 13</strong>: Go to Graphed metrics, click on the bell icon</p>
<p><a href="https://media.geeksforgeeks.org/wp-content/uploads/20200706210030/image15.jpg"><img src="https://media.geeksforgeeks.org/wp-content/uploads/20200706210030/image15.jpg" alt=""></a></p>
<p><strong>Step 14:</strong>  This dashboard shows the components of Amazon Cloudwatch such as Namespace, Metric Name, Statistics, etc</p>
<p><a href="https://media.geeksforgeeks.org/wp-content/uploads/20200706210031/image16.jpg"><img src="https://media.geeksforgeeks.org/wp-content/uploads/20200706210031/image16.jpg" alt=""></a></p>
<p><strong>Step 15:</strong> Select the greater threshold. Also, specify the amount( i.e 80 ) of the threshold value. Click on Next.</p>
<p><a href="https://media.geeksforgeeks.org/wp-content/uploads/20200706210033/image17.jpg"><img src="https://media.geeksforgeeks.org/wp-content/uploads/20200706210033/image17.jpg" alt=""></a></p>
<p><strong>Step 16</strong>: Click on Select an existing SNS topic, also mention the name of the SNS topic you created now.</p>
<p><a href="https://media.geeksforgeeks.org/wp-content/uploads/20200707103648/image181.jpg"><img src="https://media.geeksforgeeks.org/wp-content/uploads/20200707103648/image181.jpg" alt=""></a></p>
<p><strong>Step 17</strong>: Specify the name of alarm and description which is completely optional. Click on Next and then click on Create alarm.</p>
<p><a href="https://media.geeksforgeeks.org/wp-content/uploads/20200706210035/image19.jpg"><img src="https://media.geeksforgeeks.org/wp-content/uploads/20200706210035/image19.jpg" alt=""></a></p>
<p><strong>Step 18</strong>: The alarm is successfully created.</p>
<p><a href="https://media.geeksforgeeks.org/wp-content/uploads/20200706210039/image22.jpg"><img src="https://media.geeksforgeeks.org/wp-content/uploads/20200706210039/image22.jpg" alt=""></a></p>
<p><strong>Step 19</strong>: You can see the graph which notifies whenever CPU utilization goes above 80%.</p>
<p><a href="https://media.geeksforgeeks.org/wp-content/uploads/20200706213442/image23.jpg"><img src="https://media.geeksforgeeks.org/wp-content/uploads/20200706213442/image23.jpg" alt=""></a></p>
<h3 id="use-cases-for-cloudwatch">Use cases for CloudWatch</h3>
<ul>
<li>CloudWatch can be used to monitor the performance of AWS resources, applications, and infrastructure components in real-time</li>
<li>CloudWatch allows users to set up alarms that trigger notifications or automated actions in response to changes in the state of their resources.</li>
<li>CloudWatch can be used to store, search, and analyze log data from various AWS services, applications, and infrastructure components.</li>
<li>CloudWatch can be used to monitor the performance of EC2 instances, RDS databases, and other resources, which can then be used to trigger automatic scaling events.</li>
</ul>
<h3 id="advantages-of-amazon-cloudwatch"><strong>Advantages of Amazon Cloudwatch</strong></h3>
<ul>
<li>A large amount of data is produced by web applications nowadays so amazon cloudwatch acts as a dashboard that contains the organized collection of whole data.</li>
<li>It improves the total cost of ownership by providing alarms and also takes automated actions when there is an error in limits provided.</li>
<li>Applications and resources can be optimized by examining the logs and metric data.</li>
<li>Detailed Insights from the application are provided through data like CPU utilization, capacity utilization, memory utilization, etc</li>
<li>It provides a great platform to compare and contrast the data produced by various AWS services.</li>
</ul>
<h3 id="disadvantages-of-amazon-cloudwatch">Disadvantages of Amazon Cloudwatch</h3>
<ul>
<li>Cloud Watch can be expensive, especially for large-scale monitoring and logging needs.</li>
<li>Cloud Watch may not be able to handle large amounts of log data, especially during spikes in usage, making it difficult to maintain a consistent level of monitoring and logging.</li>
<li>The monitoring and logging processes of CloudWatch can consume significant system resources, impacting the overall performance of an application.</li>
<li>Integrating CloudWatch with other AWS services and third-party tools can be challenging.</li>
<li>Setting up and managing CloudWatch can be complex, especially for users who are not familiar with cloud-based systems.</li>
</ul>
</div>
</body>

</html>
