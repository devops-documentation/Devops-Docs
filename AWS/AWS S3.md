# What is S3?

Let's look at AWS S3. S3 is an easy-to-use, scalable, and cheap storage service from Amazon. You can use S3 to store any amount of data for a wide range of use cases.

Static website hosting, data archival, and software delivery are a few general scenarios where S3 would be a perfect tool.

You can easily push and pull data with S3 using the AWS SDK. S3 also supports a number of popular programming languages, so you can use your existing stack and integrate S3 pretty easily.

![Screenshot-2020-08-10-at-6.14.06-PM](https://www.freecodecamp.org/news/content/images/2020/08/Screenshot-2020-08-10-at-6.14.06-PM.png)

AWS Console

S3 also offers a great user interface via the  [AWS console](https://aws.amazon.com/console/). You can use it to view the data pushed to S3 along with additional options such as security and version control.

## Buckets

In S3, files are stored in buckets. Buckets are similar to folders on your computer.

Every bucket has its own unique name which can be used only once. For example, if there is a bucket called “freecodecamp”, neither you nor anyone else can re-use the same bucket name.

This is useful to uniquely identify resources and for static website hosting with domain names.

There are no limits on the number of files you can store in a bucket. Buckets also provide additional features such as version control and  [policies](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html).

You can also use different buckets for a single application. For example, an app that stores medical records can use two buckets: one for private customer data and another public bucket that contains whitepapers.

S3 is also an object-based storage service which means S3 considers each file an object. Every object can have its own metadata that includes the name, size, date, and other information.

## S3 storage types


Amazon S3 offers different storage classes, each optimized for specific use cases and cost considerations. These storage classes allow you to choose the right level of durability, availability, and performance for your data while managing costs effectively. As of my knowledge cutoff date in September 2021, here are the main storage classes offered by Amazon S3:

1.  **S3 Standard**: This is the default storage class and provides high durability, availability, and low latency. It is suitable for frequently accessed data and is designed for general-purpose storage.
    
2.  **S3 Intelligent-Tiering**: This storage class uses machine learning to automatically move objects between two access tiers: frequent and infrequent access. It's designed to optimize costs for data with unknown or changing access patterns.
    
3.  **S3 One Zone-Infrequent Access (S3 One Zone-IA)**: This class stores data in a single availability zone and is ideal for infrequently accessed data that can be recreated if lost. It offers a lower cost compared to standard storage.
    
4.  **S3 Glacier**: Glacier is designed for long-term archival and data retention. It offers lower storage costs but longer retrieval times. Data retrieval can take minutes to hours.
    
5.  **S3 Glacier Deep Archive**: This is the lowest-cost storage class and is designed for archival data that is rarely accessed. Retrieval times can take several hours.
    
6.  **S3 Outposts**: This storage class is designed for data that needs to be stored on-premises using AWS Outposts, which is a service that extends AWS infrastructure to on-premises locations.
    
7.  **S3 Replication**:
    
    -   **S3 Cross-Region Replication (CRR)**: Replicates objects from one bucket in a source AWS region to a bucket in a different target AWS region.
    -   **S3 Same-Region Replication (SRR)**: Replicates objects between buckets in the same region but in different accounts.

It's important to note that AWS may have introduced new storage classes or made changes after my knowledge cutoff date. I recommend checking the official AWS documentation for the most up-to-date information on S3 storage classes and their features, benefits, and pricing.


## Why Use S3?

Companies like Netflix, Dropbox, and Reddit are avid users of S3. The popular file storage system Dropbox built its entire storage capacity on top of Amazon S3.

Let’s look at some of the core features of S3 and understand why it's so popular among enterprises and startups alike.

### It's Affordable

S3 is cheap. I mean super cheap compared to other storage solutions. And with S3, you only pay for what you use. There are no upfront costs, no setup. It's just plug and play.

In addition to affordable pricing, S3 offers a Free tier. This free tier comes with 5GB of storage space, 20,000 GET Requests, 2,000 PUT, COPY, POST, or LIST Requests and 15GB of Data Transfer. The free tier is available every month for the first year.

With S3 you can avoid paying for space or bandwidth you might not even need.

### It's Scalable

S3 scales with your application. Since you pay only for that you use, there is no limit to the data you can store in S3.

This is helpful during multiple scenarios, especially during an unexpected surge in user growth. You don’t have to buy extra space. S3 has you covered.

### It's Secure

One of the many reasons companies prefer S3 is its inclination towards security. While you have to secure custom server setups, S3 is secure by default.

This does not mean you cannot store publicly accessible information in S3. S3 locks up all your data with high security unless you explicitly configure not to.

S3 also maintains compliance programs, such as PCI-DSS, HIPAA/HITECH, FedRAMP, EU Data Protection Directive, and FISMA, to help you meet your industry’s regulatory requirements.

### It Has Versioning

Versioning means keeping multiple copies of a file and tracking its changes over time. This is useful, especially when you handle sensitive data.

You can also retrieve accidentally deleted files when you enable versioning with S3.

## S3 Use Cases

### Static Website Hosting

You can use S3 as a static website hosting platform. The difference between static and dynamic websites is that dynamic websites receive and process user input. Static websites are used only for displaying information.

With the advent of  [Single Page Applications](https://en.wikipedia.org/wiki/Single-page_application), you can host a complete web app on S3, often free of charge.

Frameworks like React and Angular have made user input processing happen within the browser. You can build a SPA that listens to third party APIs and host it within S3.

S3 also has great support for routing, so you can use your own custom domain as well.

I recently wrote an article on hosting a React web app using S3 and  [you can find the article here](https://medium.com/@manishmshiva/aws-s3-hosting-a-react-web-app-on-aws-s3-2ff2e8ca78dd).

### Analytics

You can run queries on your S3 data without moving your data to an analytics platform. This makes S3 a great use case for building powerful analytics applications.

S3 offers multiple options including S3 Select, Amazon Athena, and Amazon Redshift Spectrum. You can also combine these with  [AWS Lambda](https://aws.amazon.com/lambda/)  to perform data processing on the fly.

### File Sharing

Amazon S3 can be also used as a cheap file sharing solution. Like I mentioned earlier in the article, the famous file sharing service Dropbox was first built on top of S3.

With flexible security policies, you can configure your S3 buckets with custom permissions for different customers. S3 also offers  [transfer acceleration](https://aws.amazon.com/s3/transfer-acceleration/#:~:text=S3%20Transfer%20Acceleration%20%28S3TA%29%20reduces,to%20S3%20for%20remote%20applications.)  to speed up large file transfers across longer distances.


# Creating an S3 Bucket 

Sign in to the AWS Management console. After sign in

-   Move to the S3 services. After clicking on S3

-   To create an S3 bucket, click on the "Create bucket". On clicking the "Create bucket" button

![Imgur](https://i.imgur.com/WCweshy.png)


- Enter the bucket name which should look like DNS address, and it should be resolvable. A bucket is like a folder that stores the objects. A bucket name should be unique. A bucket name should start with the lowercase letter, must not contain any invalid characters. It should be 3 to 63 characters long.

![Imgur](https://i.imgur.com/nIAbOox.png)

- Under Object Ownership, to disable or enable ACLs and control ownership of objects uploaded in your bucket, choose one of the following settings:

ACLs disabled:

Bucket owner enforced (default) – ACLs are disabled, and the bucket owner automatically owns and has full control over every object in the bucket. ACLs no longer affect access permissions to data in the S3 bucket. The bucket uses policies exclusively to define access control.

By default, ACLs are disabled. A majority of modern use cases in Amazon S3 no longer require the use of ACLs. We recommend that you keep ACLs disabled, except in unusual circumstances where you must control access for each object individually. For more information, see Controlling ownership of objects and disabling ACLs for your bucket.

ACLs enabled:

Bucket owner preferred – The bucket owner owns and has full control over new objects that other accounts write to the bucket with the bucket-owner-full-control canned ACL.

If you apply the Bucket owner preferred setting, to require all Amazon S3 uploads to include the bucket-owner-full-control canned ACL, you can add a bucket policy that allows only object uploads that use this ACL.

Object writer – The AWS account that uploads an object owns the object, has full control over it, and can grant other users access to it through ACLs.

![Imgur](https://i.imgur.com/WjYP1Fo.png)

- Under Block Public Access settings for this bucket, choose the Block Public Access settings that you want to apply to the bucket.

By default, all four Block Public Access settings are enabled. We recommend that you keep all settings enabled, unless you know that you need to turn off one or more of them for your specific use case. For more information about blocking public access, see Blocking public access to your Amazon S3 storage.

![Imgur](https://i.imgur.com/hS0xDgx.png)


-   Click on the "Create" button. Now, the bucket is created.
-   Now, click on ypur bucket  to upload a file in this bucket. On clicking, the screen appears is shown below:

![Imgur](https://i.imgur.com/ocFyx2D.png)



-   Click on the "Add files" button.

![Imgur](https://i.imgur.com/5LNMtuG.png)

-   Add the  **jtp.jpg**  file.

-   Click on the "upload" button.

![Imgur](https://i.imgur.com/ueZljWI.png)

From the above screen, we observe that the "Screenshot(1).png" has been successfully uploaded to the bucket "bucket-7066".

-   Move to the properties of the object  **"Screenshot(1).png"**  and click on the object URL to run the file appearing on the right side of the screen

-   On clicking the object URL, the screen appears is shown below:

![Creating an S3 Bucket](https://static.javatpoint.com/tutorial/aws/images/aws-creating-s3-bucket12.png)

From the above screen, we observe that we are not allowed to access the objects of the bucket.

-   To overcome from the above problems, we need to set the permissions of a bucket, i.e., "bucket-7066" 
- Click on the  **"Actions"**  dropdown and then click on the "Make public".

![Imgur](https://i.imgur.com/9NUFLZV.png)

- click on make public

![Imgur](https://i.imgur.com/dgdYBVY.png)

-   Now, click on the Object URL of an object to run the file.

![Imgur](https://i.imgur.com/u97Kk4u.png)








