<!DOCTYPE html>
<html>

<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Lamda</title>
  <link rel="stylesheet" href="https://stackedit.io/style.css" />
</head>

<body class="stackedit">
  <div class="stackedit__html"><h1 id="lamda">Lamda</h1>
<p>AWS Lambda is the new computing system that offers a variety of benefits like real-time data processing and custom back-end service. With so much information available about AWS Lambda, it can be hard to know what it is without an introduction.</p>
<h2 id="what-is-aws-lambda"><strong><strong>What is AWS Lambda?</strong></strong></h2>
<p>AWS Lambda is a serverless compute service offered by Amazon Web Services (AWS). It allows you to run code without provisioning or managing servers. With Lambda, you can execute your code in response to various events, such as changes to data in an Amazon S3 bucket, updates to a DynamoDB table, HTTP requests via API Gateway, and more.</p>
<h2 id="when-to-use-lambda">When To Use Lambda?</h2>
<p>AWS lambda is very helpful when you know how to write code but you don’t know how to provision the underlying infrastructure in AWS. AWS lambda will scale up the applications rapidly when there is sudden incoming traffic and scale down to zero when the incoming traffic is reduced.</p>
<h3 id="use-cases-of-aws-lambda">Use Cases Of AWS Lambda</h3>
<p>AWS Lambda can be used for a wide range of use cases across different industries. Here are some common use cases for AWS Lambda:</p>
<ol>
<li>
<p><strong>Real-time Data Processing:</strong> Lambda functions can process real-time streams of data, such as logs, sensor readings, or social media feeds. You can analyze, transform, and aggregate data as it arrives, enabling real-time insights and actions.</p>
</li>
<li>
<p><strong>Serverless APIs:</strong> You can use Lambda functions to build serverless APIs using Amazon API Gateway. This allows you to expose backend services without managing traditional server infrastructure.</p>
</li>
<li>
<p><strong>Automated File Processing:</strong> Lambda functions can automatically process files uploaded to Amazon S3. This can include tasks like image or video transcoding, data validation, or extracting information from documents.</p>
</li>
<li>
<p><strong>Data ETL (Extract, Transform, Load):</strong> Lambda can be used to extract data from various sources, transform it into the desired format, and load it into a data warehouse or database for analysis.</p>
</li>
<li>
<p><strong>IoT Data Processing:</strong> Lambda functions can process and analyze data generated by Internet of Things (IoT) devices, enabling real-time decision-making and insights from IoT data.</p>
</li>
<li>
<p><strong>User Authentication and Authorization:</strong> Lambda can handle authentication and authorization logic for user access to resources, making it an essential part of serverless authentication services.</p>
</li>
<li>
<p><strong>Image and Video Processing:</strong> Lambda functions can resize images, generate thumbnails, or transcode videos on-the-fly as they are requested, reducing the need for manual pre-processing.</p>
</li>
<li>
<p><strong>Scheduled Tasks and Cron Jobs:</strong> Lambda can be scheduled to run tasks at specific intervals, such as regular backups, data synchronization, or generating reports.</p>
</li>
<li>
<p><strong>Backend for Mobile and Web Applications:</strong> Lambda can serve as the backend logic for mobile and web applications, handling tasks such as user registration, user-generated content processing, and more.</p>
</li>
</ol>
<h2 id="aws-lambda-key-features">AWS Lambda Key Features</h2>
<ol>
<li>
<p><strong>Serverless Architecture:</strong> You don’t need to worry about server provisioning, scaling, or maintenance. AWS handles the infrastructure management, allowing you to focus solely on your code.</p>
</li>
<li>
<p><strong>Event-Driven:</strong> Lambda functions are triggered by events from various AWS services, as well as custom events. This makes it easy to build reactive and event-driven applications.</p>
</li>
<li>
<p><strong>Pay-as-You-Go Pricing:</strong> You are charged based on the number of requests and the execution time of your code. You only pay for the computing resources used during the execution of your code.</p>
</li>
<li>
<p><strong>Language Support:</strong> AWS Lambda supports a variety of programming languages, including Node.js, Python, Java, Go, Ruby, and more. This enables you to write functions in the language you’re most comfortable with.</p>
</li>
<li>
<p><strong>Scalability:</strong> AWS Lambda automatically scales your code in response to incoming requests or events. It can handle thousands of requests per second or just one request per day, depending on your needs.</p>
</li>
<li>
<p><strong>Stateless:</strong> Each Lambda function execution is stateless, meaning it doesn’t retain information between invocations. However, you can use other AWS services (like DynamoDB or S3) to store persistent data.</p>
</li>
<li>
<p><strong>Customizable:</strong> You can configure various settings for your Lambda functions, including memory allocation, timeout duration, and environment variables.</p>
</li>
</ol>
<h2 id="how-does-aws-lambda-work">How Does AWS Lambda Work?</h2>
<p>Start off by uploading the code to AWS Lambda. From there, set up the code to trigger from other AWS services, HTTP endpoints, or mobile apps. AWS Lambda will only run the code when it’s triggered and will also only use the computing resources needed to run it. The user has to pay only for the compute time used.</p>
<h2 id="aws-lambda-pricing">AWS Lambda Pricing</h2>
<p>AWS Lambda pricing is based on two main factors: the number of requests and the compute time used by your Lambda functions. Here’s a breakdown of the pricing components for AWS Lambda:</p>
<ol>
<li>
<p><strong>Requests:</strong> You are charged based on the total number of requests made to your Lambda functions. This includes both invocations and event source notifications. There are different pricing tiers based on the total number of requests in a given month.</p>
</li>
<li>
<p><strong>Compute Time:</strong> You are billed for the actual compute time (measured in gigabyte-seconds) consumed by your Lambda functions. This is the time your code takes to execute. The pricing is based on the amount of memory allocated to your function, with higher memory configurations generally resulting in faster execution times.</p>
</li>
</ol>
<p>AWS Lambda also offers a free tier, which includes a certain amount of compute time and requests per month at no cost. The specific free tier limits may change over time, so it’s important to check the AWS Lambda pricing page for the most up-to-date information.</p>
<p>Additionally, there are no charges for idle time when your Lambda function is not processing requests.</p>
<p>It’s important to note that there might be additional costs associated with using other AWS services in conjunction with Lambda, such as data storage (Amazon S3, Amazon DynamoDB), data transfer, and other related services.</p>
<p>For the most current and detailed information about AWS Lambda pricing, including specific pricing tiers, free tier limits, and any potential discounts, please visit the official AWS Lambda Pricing page on the AWS website: <a href="https://aws.amazon.com/lambda/pricing/">https://aws.amazon.com/lambda/pricing/</a></p>
<p>Regenerate</p>
<h2 id="getting-started-with-aws-lambda">Getting started with AWS Lambda</h2>
<p>Follow the steps mentioned below to create your own customized AWS lambda functions by using the AWS console. <a href="https://www.geeksforgeeks.org/amazon-web-services-setting-up-an-aws-account/">Create an AWS account.</a></p>
<h3 id="steps-for-creating-aws-lambda-functions-using-the-aws-console">Steps for Creating AWS Lambda Functions using the AWS Console</h3>
<p><strong><strong>Step 1:</strong></strong> Log in to your AWS console and search for Lambda. As shown in the following image.</p>
<p><img src="https://i.imgur.com/TwsnCC8.png" alt="Imgur"></p>
<p><strong><strong>Step 2:</strong></strong> Click on Create function.</p>
<p><img src="https://i.imgur.com/CnQHj35.png" alt="Imgur"></p>
<p><strong><strong>Step 3:</strong></strong> Here we are going to use a sample hello world program by using a blueprint enter function name and scroll down click on create lamda.</p>
<p><img src="https://i.imgur.com/Mck96Am.png" alt="Imgur"></p>
<p><strong><strong>Step 4:</strong></strong> Successfully our function is created.</p>
<p><img src="https://i.imgur.com/2hIZz9N.png" alt="Imgur"></p>
</div>
</body>

</html>
