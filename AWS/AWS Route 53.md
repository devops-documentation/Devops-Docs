# What is AWS Route 53?
AWS Route 53 is an AWS Managed Service that references traditional DNS ports and is highly available, scalable, and fully managed.

The AWS Route 53 service mainly uses the concept of records, allowing you to route traffic for a particular domain according to the requirements. Each record contains details such as domain or subdomain, record type, Value of record type, routing policy, and TTL.

AWS Route 53 also allows you to check the health of your resources. Furthermore, AWS Route 53 is also a domain registrar, so anyone can purchase the domain they wish to if it is available.

## Hosted Zone


An Amazon Web Services (AWS) Hosted Zone is a domain name system (DNS) service that allows you to manage and control the DNS records for your domain. In simpler terms, it provides a way to associate human-readable domain names (like "example.com") with their corresponding IP addresses or other resources.

Here are some of the key uses and benefits of hosted zones:

- **Domain Name Management**: Hosted zones allow you to manage the DNS records for your domain names. You can configure records like A records (IPv4 addresses), AAAA records (IPv6 addresses), MX records (mail servers), CNAME records (aliases), TXT records (text information), and more.

- **Domain Name Resolution**: Hosted zones enable the resolution of human-readable domain names (like example.com) into IP addresses that computers use to locate resources on the internet.

- **Subdomain Management**: You can create and manage subdomains within a hosted zone. For example, you can have a hosted zone for example.com and create subdomains like blog.example.com or app.example.com.

- **Traffic Routing and Load Balancing**: Hosted zones allow you to set up DNS-based traffic routing, including weighted round-robin and latency-based routing. This is useful for load balancing traffic across multiple resources, such as servers or data centers.

- **Health Checks**: Route 53 can perform health checks on your resources and adjust DNS routing based on the health of those resources. This helps in directing traffic away from unhealthy resources.

- **Domain Registration and Transfer**: When you register a new domain or transfer an existing domain to Route 53, AWS automatically creates a hosted zone for that domain. This makes it easy to start managing your domain's DNS records.

- **Global Traffic Management**: Route 53's Global Traffic Management feature uses multiple AWS regions to route traffic to the endpoint that provides the best performance for the user.

- **Alias Record**s: Hosted zones support alias records, which allow you to map your domain or subdomain to specific AWS resources (like Amazon S3 buckets, CloudFront distributions, or Load Balancers) using an AWS-specific routing mechanism.

- **Private DNS**: Hosted zones can also be configured as private zones, allowing you to manage DNS records within your Virtual Private Cloud (VPC) and enabling DNS resolution for internal resources.










# Integrating AWS Route 53 with an EC2 Instance
You have a basic idea about AWS Route 53, which is excellent. But do you know AWS Route 53 integrates with various AWS services such as CloudFront, AWS EC2, load balancer, etc.?

But in this tutorial, you will learn to integrate the EC2 instance with AWS Route 53. Perform the following steps.

1. Open your favorite web browser, navigate the AWS Management Console, and log in
2. While in the Console, click on the search bar at the top, search ‘Route 53‘, and click Route 53 on the results.

3. Next, click Hosted zones → Create hosted zone to create a new hosted zone. The hosted zone will contain all the records related to your domain.

![Imgur](https://i.imgur.com/OGnlAvJ.png)

4. On the Create hosted zone, enter the Domain name that you want AWS Route 53 to route traffic. Optionally, add a Description to identify this zone better. Lastly, select Public hosted zone as type; this option means you’re routing the domain traffic on the internet.

![Imgur](https://i.imgur.com/Ro1Yha0.png)

5. After you create a hosted zone, you will see the hosted zone appear in the Hosted zones. In the hosted zone, create a new record by clicking on the Create record button.

![Imgur](https://i.imgur.com/nPJk613.png)

6. On the Quick create record page, add the record name you want to create. For example, if the DNS record is testawsec2.automateinfra.com, type testawsec2as the record name.

![Imgur](https://i.imgur.com/7x5QeLO.png)

On the Record type, choose option A – Routes traffic to an IPv4 address and some AWS resources.

Type the target IP address inside the Value field. If there are multiple target IP addresses, enter them per line.

Finally, click Create records.

![Imgur](https://i.imgur.com/22MGiS6.png)

7. After creating the record, you will see the record (testawsec2.automateinfra.com) under the Records section.

![Imgur](https://i.imgur.com/badnrpK.png)

