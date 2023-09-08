<!DOCTYPE html>
<html>

<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>aws vpc</title>
  <link rel="stylesheet" href="https://stackedit.io/style.css" />
</head>

<body class="stackedit">
  <div class="stackedit__html"><h2 id="what-is-amazon-vpc">What is Amazon VPC?</h2>
<p>With Amazon Virtual Private Cloud (Amazon VPC), you can launch AWS resources in a logically isolated virtual network that you’ve defined. This virtual network closely resembles a traditional network that you’d operate in your own data center, with the benefits of using the scalable infrastructure of AWS. The following diagram shows an example VPC. The VPC has one subnet in each of the Availability Zones in the Region, EC2 instances in each subnet, and an internet gateway to allow communication between the resources in your VPC and the internet.<br>
<img src="https://i.imgur.com/5KNk66j.png" alt="Imgur"></p>
<h2 id="how-it-works">How it works</h2>
<p>Amazon Virtual Private Cloud (Amazon VPC) gives you full control over your virtual networking environment, including resource placement, connectivity, and security. Get started by setting up your VPC in the AWS service console. Next, add resources to it such as Amazon Elastic Compute Cloud (EC2) and Amazon Relational Database Service (RDS) instances. Finally, define how your VPCs communicate with each other across accounts, Availability Zones, or AWS Regions. In the example below, network traffic is being shared between two VPCs within each Region.<br>
<img src="https://i.imgur.com/Zt1LpMk.png" alt="Imgur"></p>
<p>VPC diagram The following diagram shows a VPC with no additional VPC resources. For example VPC configurations<br>
<img src="https://i.imgur.com/oUMbUKw.png" alt="Imgur"></p>
<p><strong>Default VPCs</strong><br>
When you start using Amazon VPC, you have a default VPC in each AWS Region. A default VPC comes with a public subnet in each Availability Zone, an internet gateway, and settings to enable DNS 56 Amazon Virtual Private Cloud User Guide Default VPC components resolution. Therefore, you can immediately start launching Amazon EC2 instances into a default VPC. You can also use services such as Elastic Load Balancing, Amazon RDS, and Amazon EMR in your default VPC. A default VPC is suitable for getting started quickly and for launching public instances such as a blog or simple website. You can modify the components of your default VPC as needed.</p>
<p><strong>Default VPC components</strong><br>
When we create a default VPC, we do the following to set it up for you:<br>
• Create a VPC with a size /16 IPv4 CIDR block (172.31.0.0/16). This provides up to 65,536 private IPv4 addresses.<br>
• Create a size /20 default subnet in each Availability Zone. This provides up to 4,096 addresses per subnet, a few of which are reserved for our use.<br>
• Create an internet gateway (p. 144) and connect it to your default VPC.<br>
• Add a route to the main route table that points all traffic (0.0.0.0/0) to the internet gateway.<br>
• Create a default security group and associate it with your default VPC.<br>
• Create a default network access control list (ACL) and associate it with your default VPC.<br>
• Associate the default DHCP options set for your AWS account with your default VPC.<br>
<strong>Note:</strong><br>
Amazon creates the above resources on your behalf. IAM policies do not apply to these actions because you do not perform these actions. For example, if you have an IAM policy that denies the ability to call CreateInternetGateway, and then you call CreateDefaultVpc, the internet gateway in the default VPC is still created. The following figure illustrates the key components that we set up for a default VPC.<br>
<img src="https://i.imgur.com/YEvFevv.png" alt="Imgur"></p>
<h2 id="subnet">Subnet:</h2>
<p>A subnet is a range of IP addresses in a VPC (Virtual Private Cloud). Subnets allow you to logically organize your resources in a VPC and to control access to those resources.</p>
<p>For example, you can create a subnet for your public-facing resources, such as web servers, and a subnet for your private-facing resources, such as databases. You can also create subnets in different availability zones to improve the availability of your resources.</p>
<p>Subnets are assigned to a VPC and cannot be moved to another VPC. You can create up to 200 subnets per VPC.</p>
<p>There are two types of subnets in AWS:</p>
<ul>
<li><strong>Public subnets:</strong>  Public subnets have a direct route to the internet gateway. This means that resources in public subnets can access the internet without using a NAT device.</li>
<li><strong>Private subnets:</strong>  Private subnets do not have a direct route to the internet gateway. This means that resources in private subnets can only access the internet through a NAT device.</li>
</ul>
<p>NAT devices (Network Address Translation devices) are used to allow resources in private subnets to access the internet. NAT devices translate the private IP addresses of resources in private subnets to public IP addresses. This allows resources in private subnets to communicate with the internet, while keeping their private IP addresses hidden.</p>
<p>Here are some of the benefits of using subnets in AWS:</p>
<ul>
<li>
<p><strong>Logical organization:</strong>  Subnets allow you to logically organize your resources in a VPC. This can make it easier to manage your resources and to troubleshoot problems.</p>
</li>
<li>
<p><strong>Access control:</strong>  Subnets allow you to control access to your resources. You can use security groups to control which resources can communicate with each other and with the internet.</p>
</li>
<li>
<p><strong>Availability:</strong>  Subnets can be created in different availability zones. This can improve the availability of your resources in the event of a failure in one availability zone.</p>
</li>
<li>
<p><strong>Subnet CIDR blocks:</strong>  Subnets must be assigned a CIDR block, which is a range of IP addresses. The CIDR block for a subnet must be within the CIDR block for the VPC.</p>
</li>
<li>
<p><strong>Subnet availability zones:</strong>  Subnets can be created in one or more availability zones in a region. This can improve the availability of your resources in the event of a failure in one availability zone.</p>
</li>
<li>
<p><strong>Subnet routing:</strong>  Subnets must be associated with a route table. The route table specifies how traffic from the subnet is routed to other subnets, the internet, or other networks.</p>
</li>
<li>
<p><strong>Subnet security groups:</strong>  Subnets can be associated with one or more security groups. Security groups control which traffic is allowed to flow into and out of the subnet.</p>
</li>
<li>
<p><strong>Subnet Sizing</strong> :Amazon VPC supports IPv4 and IPv6 addressing, and has different CIDR block size limits for each. By default, all VPCs and subnets must have IPv4 CIDR blocks—you can’t change this behavior. You can optionally associate an IPv6 CIDR block with your VPC.</p>
</li>
</ul>
<h2 id="internet-gateway-igw">Internet gateway (IGW):</h2>
<p>An internet gateway (IGW) is a horizontally scaled, redundant, and highly available VPC component that allows communication between resources in your VPC and the internet. IGWs are attached to your VPCs and route traffic between your VPC and the internet.</p>
<p>Here are some of the benefits of using an internet gateway in AWS:</p>
<ul>
<li><strong>Allows communication with the internet:</strong>  IGWs allow your resources in your VPC to communicate with the internet. This means that you can host web servers, databases, and other applications in your VPC that can be accessed by users on the internet.</li>
<li><strong>Scalable and reliable:</strong>  IGWs are horizontally scaled, redundant, and highly available. This means that your traffic will not be interrupted if an IGW fails.</li>
<li><strong>Easy to manage:</strong>  IGWs are easy to manage. You can create, attach, and detach IGWs from your VPCs using the AWS Console, the AWS CLI, or the AWS SDKs.</li>
</ul>
<p>Here are some of the key terms related to internet gateways in AWS:</p>
<ul>
<li><strong>CIDR block:</strong>  A CIDR block is a range of IP addresses. An IGW is assigned a CIDR block that is used to route traffic between your VPC and the internet.</li>
<li><strong>Availability zone:</strong>  An availability zone is a physical location in a region. IGWs can be created in one or more availability zones in a region.</li>
<li><strong>Route table:</strong>  A route table specifies how traffic from a subnet is routed to other subnets, the internet, or other networks. An IGW can be associated with a route table to allow traffic from your VPC to the internet.</li>
<li><strong>Security group:</strong>  A security group controls which traffic is allowed to flow into and out of a subnet. An IGW can be associated with one or more security groups to control which traffic is allowed to flow between your VPC and the internet.</li>
</ul>
<h3 id="what-is-an-ip-address-internet-protocol-address">What is an IP address (Internet Protocol address)?</h3>
<p>An Internet Protocol (IP) address is a unique numerical identifier for every device or network that connects to the internet. Typically assigned by an internet service provider (<a href="https://www.techtarget.com/whatis/definition/ISP-Internet-service-provider">ISP</a>), an IP address is an online device address used for communicating across the internet.</p>
<p>There are two versions of IP addresses that are commonly used on the internet:  <a href="https://www.techtarget.com/whatis/definition/IPv4-address-class">IPv4</a>  and  <a href="https://www.techtarget.com/searchnetworking/definition/IPv6-Internet-Protocol-Version-6">IPv6</a>. An IPv4 address is expressed as a set of  <a href="https://www.techtarget.com/whatis/definition/binary-coded-decimal">four dotted decimal numbers</a>, where each  <a href="https://www.techtarget.com/whatis/definition/octet">octet</a>  is separated by a period, such as 192.168.35.4. The three digits in the first octet represent a particular network on the internet while the rest of the digits represent the actual  <a href="https://www.techtarget.com/searchnetworking/definition/host">host</a>  address within the local network, such as a workstation or a server. An IPv6 address represents eight groups of four hexadecimal digits separated by colons, such as 2620:cc:8000:1c82:544c:cc2e:f2fa:5a9b.</p>
<p>Each internet protocol address can send information to other IP addresses through discrete chunks known as  <em>packets</em>. Each  <a href="https://www.techtarget.com/searchnetworking/definition/packet">network packet</a>  contains the data being transferred along with a header containing the  <a href="https://www.techtarget.com/whatis/definition/metadata">metadata</a>  of the packet.</p>
<h3 id="how-do-ip-addresses-work">How do IP addresses work?</h3>
<p>An IP address is part of the  <a href="https://www.techtarget.com/searchnetworking/definition/TCP-IP">TCP/IP</a>  suite of protocols. It works behind the scenes, helping devices and websites connect with each other on the internet.</p>
<p>Every time a request is made to access a website, the requesting computer needs to know where the website resides and how to reach it. This is where the IP address comes into play. The requesting computer connects to the network router, which connects to the  <a href="https://www.techtarget.com/whatis/definition/Web-server">web server</a>  where the website lives. The web server then pulls the website information and sends it back to the requesting computer. Each device in this process – including the computer, router and web server – carries a uniquely identifiable IP address, without which the transfer of information will not take place.</p>
<h3 id="ipv4-vs-ipv6-what’s-the-difference">IPv4 vs IPv6: What’s the difference?</h3>
<p>Both IPv4 and IPv6 identify connected devices on the network. However, there are slight differences in the way they operate. IPv6 is the newer IP version and was introduced to address the limitations IPv4 posed on the availability of IP addresses.</p>
<p>The following is a list of differences between IPv4 and IPv6:</p>
<ul>
<li>IPv4 is 32-bit, whereas IPv6 is 128-bit.</li>
<li>In IPv4, binary bits are separated by a dot (.); IPv6 separates binary bits by a colon (:).</li>
<li>IPv4 follows the numeric addressing method and IPv6 is  <a href="https://www.techtarget.com/whatis/definition/alphanumeric-alphameric">alphanumeric</a>.</li>
<li>IPv4 offers 12 header fields and IPv6 offers eight header fields.</li>
<li>IPv4 has  <a href="https://www.techtarget.com/searchsecurity/definition/checksum">checksum</a>  fields but IPv6 doesn’t.</li>
<li>IPv4 supports broadcast address, which is a type of special address that transmits data packets to every node on the network. IPv6 doesn’t support broadcast, but instead uses a multicast address, which is a logical identifier for a collection of hosts on a network.</li>
<li>IPv4 supports  <a href="https://www.techtarget.com/searchnetworking/definition/variable-length-subnet-mask">Variable Length Subnet Mask</a>, but IPv6 doesn’t.</li>
<li>When mapping to  <a href="https://www.techtarget.com/searchnetworking/definition/MAC-address">media access control addresses</a>, IPv4 uses the  <a href="https://www.techtarget.com/searchnetworking/definition/Address-Resolution-Protocol-ARP">Address Resolution Protocol</a>. IPv6 uses the Neighbor Discovery Protocol, which uses stateless auto-configuration and address resolution.</li>
</ul>
<h3 id="types-of-ip-addresses">Types of IP addresses:</h3>
<p>Here is a list of the five most common types of IP addresses:</p>
<h4 id="private-ip-addresses">1. Private IP addresses</h4>
<p>Each device connected to a home network or a private network carries a  <a href="https://www.techtarget.com/whatis/definition/private-IP-address">private IP address</a>. Private IP addresses are non-internet facing and are only used on an internal network. Devices with private IP addresses might include computers, tablets, smartphones,  <a href="https://www.techtarget.com/searchmobilecomputing/definition/Bluetooth">Bluetooth</a>  devices, smart TVs and printers. With the increasing popularity of  <a href="https://www.techtarget.com/iotagenda/definition/Internet-of-Things-IoT">internet of things</a>  products, the use of private IP addressing is likely to keep growing.</p>
<h4 id="public-ip-addresses">2. Public IP addresses</h4>
<p>An ISP assigns these addresses, which enable a router to communicate with the internet or an outside network. Public IP addresses cover the entire network, meaning multiple devices sharing the same internet connection will also share the same public IP address.</p>
<h4 id="dynamic-ip-addresses">3. Dynamic IP addresses</h4>
<p>These IP addresses are constantly changing and a new  <a href="https://www.techtarget.com/whatis/definition/dynamic-IP-address">dynamic IP address</a>  is assigned to a device every time it connects to the internet. ISPs buy large pools of IP addresses to assign to their customers automatically. They revolve and reuse these addresses between different customers to generate cost savings and to provide easier network management. A dynamic IP address also offers security benefits, as it’s harder for cybercriminals to hack into a network interface if its IP is constantly changing.</p>
<h4 id="static-ip-addresses">4. Static IP addresses</h4>
<p>Unlike dynamic IP addresses,  <a href="https://www.techtarget.com/whatis/definition/static-IP-address">static IP addresses</a>  never change once they’re assigned by the network. While most internet users and businesses don’t require static IP addresses, they’re a requirement for businesses that wish to host their own web servers. A static IP address ensures that all websites and email addresses associated with a certain web server will always have a consistent IP address so it can be reached on the internet.</p>
<h2 id="route-table">Route table:</h2>
<p>A route table in AWS is a collection of routes that determine where network traffic is sent. Each subnet in a VPC must be associated with a route table.</p>
<p>A route table contains a set of rules, called routes, that specify the destination CIDR block and the next hop for that destination. The next hop can be an internet gateway, a virtual private gateway, a NAT gateway, or another subnet.</p>
<p>The default route table for a VPC has a single route that points to the internet gateway. This route is used for all traffic that is not explicitly routed to another destination.</p>
<p>You can create custom route tables to route traffic to specific destinations. For example, you could create a route table that routes traffic to a NAT gateway for all traffic that is destined for the internet.</p>
<p>Route tables are a fundamental part of VPC networking. They allow you to control where network traffic is sent and to ensure that your traffic is routed to the correct destination.</p>
<p>Here are some of the benefits of using route tables in AWS:</p>
<ul>
<li><strong>Centralized control:</strong>  Route tables provide a centralized way to control where network traffic is sent. This makes it easier to manage your network and to troubleshoot problems.</li>
<li><strong>Flexibility:</strong>  Route tables allow you to create custom routing rules to meet your specific needs. This gives you a lot of flexibility in how you route your traffic.</li>
<li><strong>Scalability:</strong>  Route tables can be scaled to meet the needs of your network. As your network grows, you can add more route tables to accommodate the additional traffic.</li>
</ul>
<p>If you are using a VPC in AWS, you should use route tables to control where your network traffic is sent. Route tables are a powerful tool that can help you to manage your network and to ensure that your traffic is routed to the correct destination.</p>
<h2 id="create-a-vpc-in-aws">Create a VPC in AWS</h2>
<p>To create a VPC in AWS, you need to follow these steps:</p>
<p>-Go to the AWS Management Console and open the VPC console.<br>
<img src="https://i.imgur.com/TXgZxRB.png" alt="Imgur"><br>
-select VPCs.<br>
<img src="https://i.imgur.com/NhyaBeR.png" alt="Imgur"></p>
<p>-Click Create VPC.<br>
<img src="https://i.imgur.com/NhyaBeR.png" alt="Imgur"><br>
-Enter a name for your VPC.<br>
<img src="https://i.imgur.com/EJHjhAg.png" alt="Imgur"></p>
<p>-Select the IPv4 CIDR block for your VPC.<br>
<img src="https://i.imgur.com/0abjyVh.png" alt="Imgur"></p>
<p>-Click Create.<br>
<img src="https://i.imgur.com/hoTJOPr.png" alt="Imgur"></p>
<p>-<strong>Creating the subnets</strong><br>
-Then go to Subnets<br>
<img src="https://i.imgur.com/wX6RadS.png" alt="Imgur"><br>
-Click Create Subnet.<br>
<img src="https://i.imgur.com/LBu5vrt.png" alt="Imgur"><br>
-Select the VPC that you want the subnet to be in.<br>
<img src="https://i.imgur.com/ewh8hyJ.png" alt="Imgur"><br>
-(For Public subnets )Enter a name for your subnet,Select the IPv4 CIDR block for your subnet and Select the Availability Zone where you want your subnet to be available.<br>
<img src="https://i.imgur.com/j6Qzdvj.png" alt="Imgur"><br>
-(For Private subnets )Enter a name for your subnet,Select the IPv4 CIDR block for your subnet and Select the Availability Zone where you want your subnet to be available.<br>
<img src="https://i.imgur.com/liSjH92.png" alt="Imgur"></p>
<p>-Click Create.<br>
<img src="https://i.imgur.com/kD3NVyh.png" alt="Imgur"></p>
<p>-Creating the Internet Gateways</p>
<p>-Choose <strong>Internet Gateways</strong></p>
<p><img src="https://i.imgur.com/8QQanQe.png" alt="Imgur"></p>
<p>-Enter <strong>Internet Gateways</strong> name<br>
<img src="https://i.imgur.com/3nrSfC7.png" alt="Imgur"></p>
<p>-Click <strong>Attach to a VPC</strong><br>
<img src="https://i.imgur.com/soT8erS.png" alt="Imgur"></p>
<p>-Select the VPC that created and <strong>Click</strong> Attach Internet Gateways<br>
<img src="https://i.imgur.com/vOO1bgi.png" alt="Imgur"></p>
<p>-Choose <strong>Create route table</strong><br>
<img src="https://i.imgur.com/6EB6rAc.png" alt="Imgur"></p>
<ol>
<li>In the  <strong>Name</strong>  field, enter a name for your route table.</li>
<li>In the  <strong>VPC</strong>  field, select the VPC that you want the route table to be associated with</li>
<li>(Optional) To add tags to your route table, choose <strong>Add tag</strong> and enter the tag key and tag value</li>
<li>Choose <strong>Create route table</strong></li>
</ol>
<p><img src="https://i.imgur.com/EAqJR5a.png" alt="Imgur"></p>
<p>-Then go the rb-public</p>
<p><img src="https://i.imgur.com/6EB6rAc.png" alt="Imgur"></p>
<p>-Then click “<strong>Edit routes</strong>”</p>
<p><img src="https://i.imgur.com/2FDQeaF.png" alt="Imgur"></p>
<p>-Then click “<strong>Add route</strong>”</p>
<p><img src="https://i.imgur.com/SxndM24.png" alt="Imgur"></p>
<p>-Then give <strong>0.0.0.0/0</strong> in then Defination and in the Target select your <strong>Internet Gateway</strong></p>
<p><img src="https://i.imgur.com/cHPh9Ys.png" alt="Imgur"></p>
<p>-Then go to <strong>Subnet associations</strong>  and <strong>click</strong> Edit Subnet associations</p>
<p><img src="https://i.imgur.com/9FTbZ8L.png" alt="Imgur"></p>
<p>-Then go to subnet associations Select your public subets</p>
<p><img src="https://i.imgur.com/Fcov27g.png" alt="Imgur"></p>
<p>-Then create a another route table</p>
<p><img src="https://i.imgur.com/X5onZ2X.png" alt="Imgur"></p>
<p>-Then go to <strong>Subnet associations</strong>  and <strong>click</strong> Edit Subnet associations</p>
<p><img src="https://i.imgur.com/9FTbZ8L.png" alt="Imgur"></p>
<p>-Then go to <strong>subnet associations</strong> Select your private subets</p>
<p><img src="https://i.imgur.com/2h5q6vk.png" alt="Imgur"></p>
<p>-Finall VPC View</p>
<p><img src="https://i.imgur.com/cQqEicV.png" alt="Imgur"></p>
</div>
</body>

</html>
