<!DOCTYPE html>
<html>

<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>aws EC2</title>
  <link rel="stylesheet" href="https://stackedit.io/style.css" />
</head>

<body class="stackedit">
  <div class="stackedit__html"><h2 id="launch-an-instance">Launch an instance</h2>
<p>Amazon EC2 allows you to create virtual machines, or instances, that run on the AWS Cloud. Quickly get started by following the simple steps below.</p>
<p><strong>1)Name and tags:</strong></p>
<p><strong>2)Application and OS Images (Amazon Machine Image):</strong><br>
An Amazon Machine Image (AMI) is a pre-configured virtual machine image that you can use to launch an instance. AMIs include the operating system, application software, and other settings that you need to run your application.</p>
<p>There are two main types of AMIs:</p>
<ul>
<li><strong>Application AMIs:</strong>  These AMIs are pre-configured with the application software that you need to run your application. For example, there are AMIs available for popular applications such as Apache Tomcat, MySQL, and WordPress.</li>
<li><strong>Operating system AMIs:</strong>  These AMIs are pre-configured with an operating system, such as Amazon Linux or Windows Server. You can then install the application software that you need on the operating system.</li>
</ul>
<p>You can also create your own AMIs. This is useful if you want to create a custom image that includes your own application software or settings.</p>
<p>To launch an instance from an AMI, you need to specify the AMI ID in the AWS Management Console or in the AWS CLI. You can also specify other parameters, such as the instance type and the amount of memory and storage that you need.</p>
<p>Once you have launched an instance, you can connect to it using SSH or RDP. You can then install the application software that you need and start running your application.</p>
<p>Here are some of the benefits of using AMIs:</p>
<ul>
<li><strong>Pre-configured:</strong>  AMIs are pre-configured with the operating system and application software that you need to run your application. This saves you time and effort from having to install and configure the software yourself.</li>
<li><strong>Secure:</strong>  AMIs are scanned for security vulnerabilities before they are made available to the public. This helps to ensure that your applications are running on a secure platform.</li>
<li><strong>Scalable:</strong>  AMIs can be scaled to meet the needs of your application. For example, if you need to increase the number of instances that are running your application, you can simply launch more instances from the same AMI.</li>
</ul>
<p>If you are developing or deploying applications on AWS, you should use AMIs. AMIs are a convenient and secure way to get your applications up and running quickly.</p>
<p><strong>3)Instance type:</strong><br>
An EC2 instance type is a type of virtual machine (VM) that you can launch on Amazon Elastic Compute Cloud (EC2). Instance types are defined by the number of CPU cores, the amount of memory, the amount of storage, and the networking capabilities.</p>
<p>There are many different instance types available, each with its own strengths and weaknesses. When choosing an instance type, you need to consider the needs of your application.</p>
<p>Here are some of the factors to consider when choosing an instance type:</p>
<ul>
<li><strong>CPU:</strong>  The number of CPU cores determines how many concurrent tasks your instance can run.</li>
<li><strong>Memory:</strong>  The amount of memory determines how much data your instance can store and process.</li>
<li><strong>Storage:</strong>  The amount of storage determines how much data your instance can store.</li>
<li><strong>Networking:</strong>  The networking capabilities determine how fast your instance can communicate with other instances and with the internet.</li>
</ul>
<p>Once you have considered the needs of your application, you can choose the instance type that is best suited for your needs.</p>
<p>Here are some of the most popular instance types:</p>
<ul>
<li><strong>General purpose:</strong>  These instance types are a good choice for a wide variety of workloads.</li>
<li><strong>Compute-optimized:</strong>  These instance types are a good choice for workloads that require a lot of CPU power.</li>
<li><strong>Memory-optimized:</strong>  These instance types are a good choice for workloads that require a lot of memory.</li>
<li><strong>Storage-optimized:</strong>  These instance types are a good choice for workloads that require a lot of storage.</li>
<li><strong>GPU-optimized:</strong>  These instance types are a good choice for workloads that require a lot of graphical processing power.</li>
</ul>
<p>If you are not sure which instance type to choose, you can use the AWS Instance Selector tool to help you choose the right instance type for your needs.</p>
<p>Here are some of the benefits of using EC2 instance types:</p>
<ul>
<li><strong>Scalability:</strong>  EC2 instance types can be scaled up or down to meet the needs of your application. This makes it easy to start small and scale as your application grows.</li>
<li><strong>Cost-effectiveness:</strong>  EC2 instance types are priced based on the amount of CPU, memory, and storage that you use. This makes it easy to find an instance type that fits your budget.</li>
<li><strong>Security:</strong>  EC2 instance types are secure by default. You can also add additional security features to your instances as needed.</li>
</ul>
<p>If you are developing or deploying applications on AWS, you should use EC2 instance types. EC2 instance types are a flexible and cost-effective way to get your applications up and running quickly.</p>
<p><strong>4)Key pair (login):</strong><br>
A key pair in AWS is a set of public and private keys that you use to authenticate to your EC2 instances. The public key is stored on your computer and the private key is stored in AWS.</p>
<p>When you launch an EC2 instance, you specify the key pair that you want to use. The instance will then use the public key to authenticate to your computer.</p>
<p>You can use a key pair to connect to your EC2 instance using SSH. To do this, you need to use the private key to generate an SSH key. You can then use the SSH key to connect to your instance.</p>
<p>Here are some of the benefits of using key pairs:</p>
<ul>
<li><strong>Security:</strong>  Key pairs are a secure way to authenticate to your EC2 instances. The private key is stored in AWS and is not accessible to anyone else.</li>
<li><strong>Ease of use:</strong>  Key pairs are easy to use. You can simply specify the key pair when you launch an EC2 instance and then use SSH to connect to the instance.</li>
<li><strong>Scalability:</strong>  Key pairs can be used to connect to multiple EC2 instances. This makes it easy to manage and administer your EC2 instances.</li>
</ul>
<p>If you are using EC2 instances, you should use key pairs to authenticate to your instances. Key pairs are a secure and easy way to connect to your instances.</p>
<p>Here are the steps on how to create a key pair in AWS:</p>
<ol>
<li>Go to the AWS Management Console and open the EC2 console.</li>
<li>In the left navigation pane, select Key Pairs.</li>
<li>Click Create Key Pair.</li>
<li>Enter a name for the key pair and click Create.</li>
<li>The key pair will be downloaded to your computer as a .pem file.</li>
</ol>
<p>Here are the steps on how to connect to an EC2 instance using SSH:</p>
<ol>
<li>Open a terminal window.</li>
<li>Navigate to the directory where the .pem file is located.</li>
<li>Run the following command:</li>
</ol>
<hr>
<pre><code>ssh -i &lt;key-pair-name&gt;.pem ec2-user@&lt;instance-public-ip&gt;
</code></pre>
<p>For example, to connect to an instance with the public IP address 192.168.1.100 and the key pair named my-key-pair, you would run the following command:</p>
<pre><code>ssh -i my-key-pair.pem ec2-user@192.168.1.100
</code></pre>
<p>You will be prompted to enter the password for the key pair. Once you have entered the password, you will be connected to the EC2 instance.</p>
<p><strong>5)Network settings:</strong></p>
<p>AWS provides a variety of network settings that you can use to configure your EC2 instances. These settings allow you to control how your instances communicate with each other, with the internet, and with other AWS services.</p>
<p>Here are some of the most important network settings:</p>
<ul>
<li><strong>VPC:</strong>  A VPC is a virtual private cloud that you can use to isolate your EC2 instances from other networks.</li>
<li><strong>Subnet:</strong>  A subnet is a logical division of a VPC. Subnets can be used to group your EC2 instances together and to control how they communicate with each other.</li>
<li><strong>Internet gateway:</strong>  An internet gateway allows your EC2 instances to communicate with the internet.</li>
<li><strong>Virtual private gateway:</strong>  A virtual private gateway allows your EC2 instances to communicate with other AWS services over a private network.</li>
<li><strong>Route table:</strong>  A route table determines where network traffic is sent.</li>
<li><strong>Security group:</strong>  A security group allows you to control how network traffic is allowed to reach your EC2 instances.</li>
</ul>
<p>When configuring your network settings, you need to consider the needs of your application. For example, if your application needs to be able to access the internet, you will need to create an internet gateway and attach it to your VPC. If your application needs to communicate with other AWS services, you will need to create a virtual private gateway and attach it to your VPC.</p>
<p>You can also use security groups to control how network traffic is allowed to reach your EC2 instances. For example, you can create a security group that only allows incoming traffic from a specific IP address or from a specific range of IP addresses.</p>
<p>Here are some of the benefits of using network settings in AWS:</p>
<ul>
<li><strong>Security:</strong>  Network settings can be used to control how your EC2 instances communicate with each other, with the internet, and with other AWS services. This helps to improve the security of your applications.</li>
<li><strong>Scalability:</strong>  Network settings can be scaled to meet the needs of your application. For example, you can add more subnets to your VPC as your application grows.</li>
<li><strong>Cost-effectiveness:</strong>  Network settings are priced based on the amount of traffic that you use. This makes it easy to find a network setting that fits your budget.</li>
</ul>
<p>If you are developing or deploying applications on AWS, you should use network settings. Network settings are a fundamental part of AWS networking and can help you to improve the security, scalability, and cost-effectiveness of your applications.</p>
<p><strong>6)Configure storage:</strong></p>
<ul>
<li><strong>Elastic Block Store (EBS):</strong>  EBS is a block storage service that provides persistent storage for your EC2 instances. EBS volumes are available in a variety of sizes and performance levels.</li>
</ul>
<p><strong>7)Advanced details:</strong></p>
<p>There are a number of advanced details that you can configure for your EC2 instances. These details can be used to customize the performance, security, and functionality of your instances.</p>
<p>Some of the most important advanced details include:</p>
<ul>
<li><strong>Instance profile:</strong>  An instance profile is a set of IAM permissions that are assigned to an EC2 instance. Instance profiles can be used to control what permissions your instance has to access AWS resources.</li>
<li><strong>Security groups:</strong>  Security groups control the traffic that is allowed to reach your EC2 instances. You can create security groups to allow specific traffic, such as SSH traffic or HTTP traffic.</li>
<li><strong>Tags:</strong>  Tags are key-value pairs that you can assign to your EC2 instances. Tags can be used to organize your instances, control access to your instances, and track your costs.</li>
<li><strong>EBS encryption:</strong>  EBS encryption can be used to encrypt your EBS volumes. This helps to protect your data from unauthorized access.</li>
<li><strong>EBS snapshots:</strong>  EBS snapshots can be used to back up your EBS volumes. This helps to protect your data from accidental deletion or corruption.</li>
<li><strong>Auto scaling:</strong>  Auto scaling can be used to automatically scale your EC2 instances up or down based on demand. This helps to ensure that you have the right number of instances running to meet your needs.</li>
</ul>
<p>These are just a few of the advanced details that you can configure for your EC2 instances. For more information, please refer to the AWS documentation.</p>
<p>Here are some additional things to keep in mind when configuring advanced settings in EC2 AWS:</p>
<ul>
<li>The advanced settings that you can configure will depend on the instance type that you are using.</li>
<li>You should carefully consider the needs of your application when configuring the advanced settings.</li>
<li>You should test the settings before you deploy them in production.</li>
</ul>
<h2 id="launching-instance">Launching Instance</h2>
<p>On the  <strong>Amazon EC2 console</strong>  dashboard, click  <strong>Launch instance</strong>.</p>
<p>The  <strong>Launch an instance</strong>  page is displayed.</p>
<ol>
<li>
<p>Figure 1 Launch an Instance</p>
<p><img src="https://i.imgur.com/tdH0qhE.png" alt="Imgur"></p>
</li>
<li>
<p>Under  <strong>Application and OS Images (Amazon Machine Image)</strong>  section you can select an AMI that contains the software that is required to act as a web server, such as Linux, Apache, and your website. To select an AMI, perform one of the following:</p>
<ul>
<li>
<p><strong>Search bar</strong></p>
<p>To search through all the available AMIs, enter a keyword in the AMI search bar and press  <strong>Enter</strong>. To select an AMI, click  <strong>Select</strong>.</p>
<p>For example, enter  Aruba  in the search bar and press  <strong>Enter</strong>  to view a list of  Aruba  AMIs. To select an AMI, click  <strong>Select</strong>.</p>
<p>Figure 2 Search Bar</p>
<p><img src="https://www.arubanetworks.com/techdocs/central/2.5.6/content/resources/images/vgw/aruba-ami.png" alt=""></p>
</li>
<li>
<p><strong>Recents</strong></p>
<p>The AMIs that you’ve recently used.</p>
<p>Select  <strong>Recently launched</strong>  or  <strong>Currently in use</strong>, and then, from  <strong>Amazon Machine Image (AMI)</strong>, select an AMI.</p>
</li>
<li>
<p><strong>My AMIs</strong></p>
<p>The private AMIs that you own, or private AMIs that have been shared with you.</p>
<p>Select  <strong>Owned by me</strong>  or  <strong>Shared with me</strong>, and then, from  <strong>Amazon Machine Image (AMI)</strong>, select an AMI.</p>
</li>
<li>
<p><strong>Quick Start</strong></p>
<p>AMIs are grouped by operating system (OS) to help you get started quickly.</p>
<p>First select the OS that you need, and then, from  <strong>Amazon Machine Image (AMI)</strong>, select an AMI. To select an AMI that is eligible for the free tier, make sure that the AMI is marked  <strong>Free tier eligible</strong>.</p>
</li>
<li>
<p><strong>Browse more AMIs</strong></p>
<p>Click  <strong>Browse more AMIs</strong>  to browse the full AMI catalog.</p>
<ul>
<li>
<p>To search through all available AMIs, enter a keyword in the search bar and then press  <strong>Enter</strong>.</p>
</li>
<li>
<p>To search by category, click  <strong>Quickstart AMIs</strong>,  <strong>My AMIs</strong>,  <strong>AWS Marketplace AMIs</strong>, or  <strong>Community AMIs</strong>.</p>
<ul>
<li>
<p><strong>AWS Marketplace</strong>—The AWS Marketplace is an online store where you can buy software that runs on AWS, including AMIs. In the AWS Marketplace, find a suitable AMI by browsing the categories or using the search functionality. To choose a product, Click  <strong>Select</strong>. A dialog box opens with an overview of the product you have selected. You can view the pricing information, as well as any other information that the vendor has provided. When you are ready, click  <strong>Continue</strong>.</p>
</li>
<li>
<p><strong>Community AMIs</strong>— In Community AMIs you can find AMIs that AWS community members have made available for others to use. AMIs from Amazon or a verified partner are marked  <strong>Verified provider</strong>.</p>
</li>
</ul>
</li>
</ul>
</li>
</ul>
<p>Figure 3 Application and OS Images (Amazon Machine Image)</p>
<p><img src="https://www.arubanetworks.com/techdocs/central/2.5.6/content/resources/images/vgw/ami.png" alt=""></p>
</li>
<li>
<p>Under  <strong>Instance type</strong>  section, select an instance type for your instance. The instance type defines the hardware configuration and size of the instance to launch.</p>
<p>Figure 4 Instance Type</p>
<p><img src="https://www.arubanetworks.com/techdocs/central/2.5.6/content/resources/images/vgw/instance-type.png" alt=""></p>
<p>c5d instance is only available on specific zones. For more information, see  <a href="https://docs.aws.amazon.com/ec2/index.html">Amazon Elastic Compute Cloud Documentation</a>.</p>
</li>
<li>
<p>Under  <strong>Key pair (login)</strong>  section, select an existing key pair or click  <strong>Create new key pair</strong>  to create a new one.</p>
<p>Figure 5 Key Pair</p>
<p><img src="https://www.arubanetworks.com/techdocs/central/2.5.6/content/resources/images/vgw/instnce-key-pair.png" alt=""></p>
</li>
<li>
<p>Under  <strong>Network settings</strong>  section, perform the following:</p>
<ul>
<li>
<p><strong>VPC</strong>— Select an existing VPC for your instance.</p>
</li>
<li>
<p><strong><a href="https://www.arubanetworks.com/techdocs/central/2.5.6/content/sd-branch/vgw/vgw_man-aws-launch-ec2-instnc.htm#">Subnet</a></strong>—Select the subnet that does not have a network interface.</p>
</li>
<li>
<p><strong><a href="https://www.arubanetworks.com/techdocs/central/2.5.6/content/sd-branch/vgw/vgw_man-aws-launch-ec2-instnc.htm#">Firewall</a>  (security groups)</strong>—To select an existing security group for the VPC, click  <strong>Select existing security group.</strong></p>
<p>If you want to use the created network interface, leave the  <strong>Common security groups</strong>  field empty.</p>
<p>Figure 6 Network Settings</p>
<p><img src="https://www.arubanetworks.com/techdocs/central/2.5.6/content/resources/images/vgw/ntwrk-settings.png" alt=""></p>
</li>
</ul>
</li>
<li>
<p>Under  <strong>Advanced network configuration</strong>  section, leave the  <strong>Network interface 1</strong>  as default.</p>
<p>Figure 7 Advanced Network Configuration</p>
<p><img src="https://www.arubanetworks.com/techdocs/central/2.5.6/content/resources/images/vgw/advncd-ntwrk-cfg.png" alt=""></p>
<p><strong>Advanced network configuration</strong>  is available only if you select a subnet.</p>
</li>
<li>
<p>To add a new network interface, click  <strong>Add network interface</strong>  and perform the following:</p>
<ul>
<li>
<p><strong>Network interface</strong>—Select network interface you created from the drop-down list.</p>
</li>
<li>
<p><strong>Description</strong>—(Optional) A description for the new network interface.</p>
</li>
<li>
<p><strong>Subnet</strong>—Select a subnet to create the new network interface. For the primary network interface (eth0), this is the subnet in which the instance is launched. If you’ve entered an existing network interface for eth0, the instance is launched in the subnet in which the network interface is located.</p>
</li>
<li>
<p><strong>Primary IP</strong>—A private IPv4 address from the range of your subnet. Leave blank to let Amazon EC2 choose a private IPv4 address for you.</p>
</li>
<li>
<p><strong>Delete on termination</strong>—Define whether the network interface is deleted when the instance is deleted.</p>
<p>Figure 8 Advanced Network Configuration - Network Interface 2</p>
<p><img src="https://www.arubanetworks.com/techdocs/central/2.5.6/content/resources/images/vgw/netwrk-inrfc-2.png" alt=""></p>
<p>Similarly, add the other two network interfaces and select the created subnets.</p>
</li>
</ul>
</li>
<li>
<p>Under  <strong>Configure storage</strong>  section, enter the size and type of the volume based on your license. For more information on Virtual Gateway sizing, see  <a href="https://www.arubanetworks.com/techdocs/central/2.5.6/content/sd-branch/vgw/vgw_overview.htm#Virtual_gateway_size">Virtual Gateway Sizing</a>.</p>
<p>Figure 9 Configure Storage</p>
<p><img src="https://www.arubanetworks.com/techdocs/central/2.5.6/content/resources/images/vgw/cfg-strge.png" alt=""></p>
</li>
<li>
<p>Under  <strong>Advance Details</strong>  section, enter the user data generated from  Aruba Central.</p>
<p>Figure 10 Entering User Data</p>
<p><img src="https://www.arubanetworks.com/techdocs/central/2.5.6/content/resources/images/vgw/user-data.png" alt=""></p>
</li>
<li>
<p>In the  <strong>Summary</strong>  panel, enter the number of instances to launch and review the instance configuration.</p>
</li>
</ol>
<pre><code>Figure 11 Summary Panel

![](https://www.arubanetworks.com/techdocs/central/2.5.6/content/resources/images/vgw/smmry-pnl.png)
</code></pre>
<ol start="11">
<li>Click  <strong>Launch instance</strong>.</li>
</ol>
<h2 id="target-group">Target group:</h2>
<p>A target group is a collection of EC2 instances, Lambda functions, or container instances that you want to distribute traffic to. When you create a load balancer, you specify one or more target groups. The load balancer then routes traffic to the targets in the target groups based on the health of the targets and the load balancing algorithm that you choose.</p>
<p>There are two types of target groups:</p>
<ul>
<li><strong>Application Load Balancer target groups:</strong>  These target groups are used by Application Load Balancers to distribute traffic to EC2 instances or containers that are running your application.</li>
<li><strong>Network Load Balancer target groups:</strong>  These target groups are used by Network Load Balancers to distribute traffic to EC2 instances that are running your application.</li>
</ul>
<p>When you create a target group, you need to specify the following:</p>
<ul>
<li>The type of target group.</li>
<li>The protocol that the target group uses.</li>
<li>The port that the target group listens on.</li>
<li>The health check settings for the target group.</li>
<li>The tags for the target group.</li>
</ul>
<p>You can also specify the following optional settings:</p>
<ul>
<li>The stickiness policy for the target group.</li>
<li>The deregistration delay for the target group.</li>
</ul>
<p>Here are some of the benefits of using target groups in AWS:</p>
<ul>
<li><strong>Load balancing:</strong>  Target groups allow you to distribute traffic evenly across your EC2 instances or containers. This helps to improve the performance of your application by preventing any one instance or container from becoming overloaded.</li>
<li><strong>High availability:</strong>  Target groups can be used to improve the availability of your application by routing traffic to healthy instances or containers even if some instances or containers are unavailable.</li>
<li><strong>Scalability:</strong>  Target groups can be used to scale your application by adding or removing instances or containers as needed. This helps to ensure that your application can handle the amount of traffic that it receives.</li>
<li><strong>Security:</strong>  Target groups can be used to protect your application from attacks by filtering traffic and blocking malicious requests.</li>
</ul>
<p>If you are developing or deploying applications on AWS, you should use target groups. Target groups are a fundamental part of AWS and can help you to improve the performance, availability, and security of your applications.</p>
<p>Here are some additional things to keep in mind when creating target groups in AWS:</p>
<ul>
<li>You can create multiple target groups in your AWS account.</li>
<li>You can create target groups in different regions and Availability Zones.</li>
<li>You can create target groups that can handle different types of traffic, such as HTTP traffic or HTTPS traffic.</li>
<li>You can create target groups that can distribute traffic to different types of targets, such as EC2 instances or containers.</li>
</ul>
<p>To create a target group in AWS, you need to follow these steps:</p>
<ol>
<li>
<p>Go to the AWS Management Console and open the Elastic Load Balancing console.<br>
<img src="https://i.imgur.com/NHMycOb.png" alt="Imgur"></p>
</li>
<li>
<p>select Target Groups.<br>
<img src="https://i.imgur.com/NHMycOb.png" alt="Imgur"></p>
</li>
<li>
<p>Click Create Target Group.<br>
<img src="https://i.imgur.com/p4NW7fJ.png" alt="Imgur"></p>
</li>
<li>
<p>Select the type of target group that you want to create.<br>
<img src="https://i.imgur.com/9wuqviA.png" alt="Imgur"></p>
</li>
<li>
<p>Enter a name for the target group.<br>
<img src="https://i.imgur.com/S9wMe3K.png" alt="Imgur"></p>
</li>
<li>
<p>Select the instances or Lambda functions that you want to add to the target group.<br>
<img src="https://i.imgur.com/DWHEETx.png" alt="Imgur"></p>
</li>
<li>
<p>For an Application Load Balancer, select the protocol that you want to use.<br>
<img src="https://i.imgur.com/BHYNKwB.png" alt="Imgur"></p>
</li>
<li>
<p>For a Network Load Balancer, select the ports that you want the target group to listen on.<br>
<img src="https://i.imgur.com/ZTUo2la.png" alt="Imgur"></p>
</li>
<li>
<p>Select the instances or Lambda functions that you want to add to the target group.<br>
<img src="https://i.imgur.com/DWHEETx.png" alt="Imgur"></p>
</li>
<li>
<p>Select the health check settings for the target group.<br>
<img src="https://i.imgur.com/6Ys31vC.png" alt="Imgur"></p>
</li>
<li>
<p>Select instance and Click Create.<br>
<img src="https://i.imgur.com/3EUmxtB.png" alt="Imgur"></p>
</li>
</ol>
<h2 id="load-balancer">Load balancer:</h2>
<p>To create a load balancer in AWS, you need to follow these steps:</p>
<ol>
<li>
<p>Go to the AWS Management Console and open the Elastic Load Balancing console.<br>
<img src="https://i.imgur.com/NHMycOb.png" alt="Imgur"></p>
</li>
<li>
<p>select Load Balancers.<br>
<img src="https://i.imgur.com/NHMycOb.png" alt="Imgur"></p>
</li>
<li>
<p>Click Create Load Balancer.<br>
<img src="https://i.imgur.com/v6zeQnE.png" alt="Imgur"></p>
</li>
<li>
<p>Select the type of load balancer that you want to create.<br>
<img src="https://i.imgur.com/bn4cbr1.png" alt="Imgur"></p>
</li>
<li>
<p>Enter a Load Balancer name, select the scheme and IP address type<br>
<img src="https://i.imgur.com/AbAtN4x.png" alt="Imgur"></p>
</li>
<li>
<p>For an Application Load Balancer, select the VPC and Availability Zones where you want to create the load balancer.<br>
<img src="https://i.imgur.com/uYvu6b3.png" alt="Imgur"></p>
</li>
</ol>
<p>6.Enter a security group<br>
<img src="https://i.imgur.com/86SLcFI.png" alt="Imgur"><br>
7.  Select the ports that you want the load balancer to listen on.<br>
<img src="https://i.imgur.com/j9iwbWk.png" alt="Imgur"></p>
<ol start="8">
<li>
<p>Select the target groups for the load balancer.<br>
<img src="https://i.imgur.com/cAI0i3y.png" alt="Imgur"></p>
</li>
<li>
<p>Click Create.<br>
<img src="https://i.imgur.com/1863Z9A.png" alt="Imgur"></p>
</li>
</ol>
<p>The load balancer will be created and you can start using it.</p>
<p>Here are some additional things to keep in mind when creating a load balancer in AWS:</p>
<ul>
<li>You can create multiple load balancers in your AWS account.</li>
<li>You can create load balancers in different regions and Availability Zones.</li>
<li>You can create load balancers that can handle different types of traffic, such as HTTP traffic or HTTPS traffic.</li>
<li>You can create load balancers that can distribute traffic to different types of targets, such as EC2 instances or containers.</li>
</ul>
<p>I hope this helps! Let me know if you have any other questions.</p>
<p>Here are some of the benefits of using a load balancer in AWS:</p>
<ul>
<li><strong>Load balancing:</strong>  A load balancer distributes traffic evenly across your EC2 instances. This helps to improve the performance of your application by preventing any one instance from becoming overloaded.</li>
<li><strong>High availability:</strong>  A load balancer can be used to improve the availability of your application by distributing traffic to healthy instances even if some instances are unavailable.</li>
<li><strong>Scalability:</strong>  A load balancer can be used to scale your application by adding or removing instances as needed. This helps to ensure that your application can handle the amount of traffic that it receives.</li>
<li><strong>Security:</strong>  A load balancer can be used to protect your application from attacks by filtering traffic and blocking malicious requests.</li>
</ul>
<p>If you are developing or deploying applications on AWS, you should use a load balancer. Load balancers are a fundamental part of AWS and can help you to improve the performance, availability, and security of your applications.</p>
<h2 id="creating-a-launch-template">Creating a Launch Template:</h2>
<ol>
<li>On the navigation pane, under  <strong>Launch Templates</strong>, click  <strong>Launch Templates</strong>.</li>
<li>Click  <strong>Create launch template</strong>.</li>
<li>On the  <strong>Basic settings</strong>  page, do the following:
<ul>
<li>
<p>For  <strong>Name</strong>, enter a name for your launch template.</p>
</li>
<li>
<p>For  <strong>Description</strong>, enter a description for your launch template.<img src="https://i.imgur.com/41vjqLZ.png" alt="Imgur"></p>
</li>
<li>
<p>For  <strong>AMI ID</strong>, choose the AMI ID for the instance type you want to launch.<br>
<img src="https://i.imgur.com/HSCE1s9.png" alt="Imgur"></p>
</li>
<li>
<p>For  <strong>Instance type</strong>, choose the instance type you want to launch.<br>
<img src="https://i.imgur.com/nuxKD1S.png" alt="Imgur"></p>
</li>
</ul>
</li>
<li>On the  <strong>Advanced settings</strong>  page, do the following:
<ul>
<li>For  <strong>Network</strong>, choose the VPC and subnets you want the instance to be launched in.</li>
<li>For  <strong>Security groups</strong>, choose the security groups you want to associate with the instance.</li>
<li>For  <strong>Storage</strong>, choose the EBS volumes you want to attach to the instance.</li>
<li>For  <strong>Tags</strong>, add tags to your instance.</li>
<li>On the  <strong>Review</strong>  page, review your settings and click  <strong>Create</strong><br>
<img src="https://i.imgur.com/Kt5x6lE.png" alt="Imgur"></li>
</ul>
</li>
</ol>
<ul>
<li></li>
</ul>
<h2 id="create-aauto-scaling"><strong>Create aAuto Scaling:</strong></h2>
<ol start="5">
<li>
<p>Go to the AWS Management Console and select  <strong>Auto Scaling</strong>.</p>
</li>
<li>
<p>Click  <strong>Create Auto Scaling group</strong>.</p>
</li>
<li>
<p>On the <strong>Choose launch template or configuration</strong> page, do the following:</p>
<ul>
<li>For <strong>Auto Scaling group name</strong>, enter a name for your Auto Scaling group.<br>
<img src="https://i.imgur.com/Vu2F6B5.png" alt="Imgur"></li>
<li>For <strong>Launch template</strong>, choose an existing launch template.  If you don’t have a launch template, you can create one by clicking  <strong>Create  launch template</strong>.</li>
<li>For <strong>Launch template version</strong>, choose whether the Auto Scaling group uses the default, the latest, or a specific version of the launch template when scaling out.<br>
<img src="https://i.imgur.com/AxeQVkv.png" alt="Imgur"></li>
</ul>
</li>
<li>
<p>On the  <strong>Choose instance launch options</strong>  page, do the following:</p>
<ul>
<li>For  <strong>VPC</strong>, choose a VPC for your Auto Scaling group.</li>
<li>For  <strong>Subnets</strong>, choose one or more subnets in the specified VPC.</li>
<li>For  <strong>Auto scaling group size</strong>, specify the desired capacity for your Auto Scaling group.<br>
<img src="https://i.imgur.com/wu8Sfjg.png" alt="Imgur"></li>
</ul>
</li>
<li>
<p>Select a <strong>Load Balancer Type</strong>:<br>
<img src="https://i.imgur.com/gp8Wn0p.png" alt="Imgur"></p>
</li>
<li>
<p>For  <strong>Auto scaling group size</strong>, specify the desired capacity for your Auto Scaling group</p>
</li>
</ol>
<p><img src="https://i.imgur.com/3fkcAjp.png" alt="Imgur"><br>
7.Finally Click <strong>Create Auto Scaling group</strong><br>
<img src="https://i.imgur.com/ZffPzsm.png" alt="Imgur"></p>
</div>
</body>

</html>
