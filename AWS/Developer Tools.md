<!DOCTYPE html>
<html>

<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Developer Tools</title>
  <link rel="stylesheet" href="https://stackedit.io/style.css" />
</head>

<body class="stackedit">
  <div class="stackedit__html"><h1 id="developer-tools">Developer Tools</h1>
<h2 id="code-commit">Code Commit</h2>
<p>AWS CodeCommit is a fully managed source control service provided by Amazon Web Services (AWS). It is designed to help software development teams securely store and manage their source code repositories in the cloud using the Git version control system. CodeCommit offers a range of features to streamline the development process and facilitate collaboration among team members. Here’s an overview of AWS CodeCommit and its key features:</p>
<ol>
<li>
<p><strong>Secure and Scalable Repositories</strong>: CodeCommit provides secure and scalable Git repositories that can store your source code, project files, and other development assets. Repositories are stored in AWS, which means you can benefit from the security, durability, and availability of AWS infrastructure.</p>
</li>
<li>
<p><strong>Git-Compatible</strong>: CodeCommit supports Git, a popular and widely-used distributed version control system. This allows developers to leverage familiar Git workflows and commands for branching, merging, committing, and tracking changes in their codebase.</p>
</li>
<li>
<p><strong>Collaboration and Access Control</strong>: You can create and manage user roles and permissions to control who has access to your repositories and what actions they can perform. This enables secure collaboration among team members while maintaining control over the codebase.</p>
</li>
<li>
<p><strong>Pull Requests and Code Reviews</strong>: CodeCommit facilitates the process of code reviews and collaboration through pull requests. Developers can propose changes, create pull requests, and have their code reviewed by peers before merging it into the main codebase.</p>
</li>
<li>
<p><strong>Triggers and Notifications</strong>: You can set up triggers to automatically invoke AWS Lambda functions or other actions when specific events occur in your CodeCommit repositories. This can help automate tasks like code validation, testing, and deployment.</p>
</li>
<li>
<p><strong>Encryption and Security</strong>: CodeCommit offers encryption at rest and in transit to ensure the security of your source code. It integrates with AWS Identity and Access Management (IAM) for fine-grained access control.</p>
</li>
<li>
<p><strong>Regional Data Residency</strong>: You can choose the AWS region in which to create your CodeCommit repositories, allowing you to adhere to data residency and compliance requirements.</p>
</li>
</ol>
<p>Overall, AWS CodeCommit aims to simplify source code management and collaboration for development teams while providing the scalability, security, and integration capabilities of the AWS cloud.</p>
<h2 id="creating-an-aws-codecommit-repository"><strong>Creating an AWS CodeCommit Repository</strong></h2>
<p><strong>Here are the steps:</strong></p>
<ul>
<li>Set up a CodeCommit repository.</li>
<li>Activate the CodeCommit console.</li>
<li>Choose the AWS Region in which you want to establish the repository.</li>
<li>Click the ‘Create Repository’ button on the ‘Repositories’ page.</li>
<li>Give a name to the ‘Repository name’ field on the ‘Create Repository’ page. Make sure your name is no more than 100 characters long.</li>
<li>This is a completely optional step. Provide a description for the repository in the ‘Description’ field. This allows other users to understand why this repository was created.</li>
<li>This is a completely optional step. Choose the ‘Add tag’ icon and enter a repository tag, which acts as an attribute name and aids in the organization and management of AWS resources.</li>
<li>Select the ‘Create’ option.</li>
</ul>
<p>Congrats, you have created your first AWS CodeCommit repository</p>
<h2 id="code-build">Code Build</h2>
<p>AWS CodeBuild is a fully managed continuous integration and continuous delivery (CI/CD) service provided by Amazon Web Services (AWS). It helps automate the process of building, testing, and packaging your code changes, making it easier to deliver high-quality software quickly and reliably. CodeBuild eliminates the need for you to set up and manage your own build servers, allowing you to focus more on writing code and less on infrastructure management.</p>
<p>Key features and concepts of AWS CodeBuild:</p>
<ol>
<li>
<p><strong>Build Environments</strong>: CodeBuild provides customizable build environments, which are Docker containers that include the necessary build tools, runtime, and dependencies for your project. You can use predefined environments provided by AWS or create your own custom environments using Docker images.</p>
</li>
<li>
<p><strong>Build Specification</strong>: To configure how CodeBuild builds your project, you use a build specification file (usually named <code>buildspec.yml</code>). This file defines the build steps, environment variables, artifacts to be produced, and post-build actions. The build specification file is typically stored alongside your source code in your version control system.</p>
</li>
<li>
<p><strong>Source Integration</strong>: CodeBuild integrates with various source code repositories like AWS CodeCommit, GitHub, Bitbucket, and others. When changes are pushed to the repository, CodeBuild can automatically trigger a build based on webhooks or integration with CI/CD pipelines.</p>
</li>
<li>
<p><strong>Build Phases</strong>: A build in CodeBuild consists of several sequential phases, such as installing dependencies, building code, running tests, and producing artifacts. Each phase is defined in the build specification file and can include commands, scripts, or other instructions.</p>
</li>
<li>
<p><strong>Build Logs and Notifications</strong>: CodeBuild provides detailed build logs, allowing you to diagnose issues and troubleshoot failures. It also supports integration with AWS CloudWatch Logs and can send build notifications to Amazon SNS, AWS Chatbot, or other messaging services.</p>
</li>
<li>
<p><strong>Build Artifacts</strong>: After a successful build, CodeBuild can generate and store build artifacts, such as binaries, packages, or deployment files. These artifacts can be used in subsequent stages of your CI/CD pipeline or deployed to AWS services like Amazon S3 or AWS Elastic Beanstalk.</p>
</li>
<li>
<p><strong>Scalability</strong>: CodeBuild automatically scales the compute resources based on your build workload, ensuring that builds run efficiently and complete in a timely manner. You are charged based on the build time and the amount of resources used.</p>
</li>
<li>
<p><strong>Security</strong>: CodeBuild provides options for securely managing build environment access, such as AWS Identity and Access Management (IAM) roles and resource policies. You can control which AWS resources the build process can access.</p>
</li>
<li>
<p><strong>Integration with CI/CD Pipelines</strong>: While CodeBuild can be used as a standalone service, it is often integrated into broader CI/CD pipelines using services like AWS CodePipeline, Jenkins, or other third-party tools. This integration allows you to automate the entire software release process.</p>
</li>
</ol>
<p>AWS CodeBuild is well-suited for projects of varying sizes and complexities, ranging from simple code builds to complex multi-step pipelines. It supports a wide range of programming languages, frameworks, and build tools, making it a versatile choice for automating your build and test processes in the AWS ecosystem.</p>
<p><strong><em>Create a CodeBuild Project</em></strong></p>
<p>We will use  <strong>CodeBuild project</strong>  to test and build the above sample Java app and prepares the  <strong>artifact</strong>  (<strong>WAR</strong>  file) which we will use it later for deployment.</p>
<p>Search CodeBuild service in AWS console navigation panel and then click on  <strong>Create Build project</strong>.</p>
<p>As you can see below, we need to fill out  <strong>CodeBuild Project Configuration.</strong> Mention  <strong>Project</strong>  <strong>Name</strong>  ,  <strong>Description</strong>  with some  <strong>Tags</strong>  as per your choice.</p>
<p><img src="https://blog2opstree.files.wordpress.com/2020/10/image-17.png?w=1024" alt=""></p>
<p>Then next part is  <strong>Source</strong>. This section will describe the source provider from where  <strong>CodeBuild</strong>  will fetch your source code.</p>
<p>It can be  <strong>CODECOMMIT</strong>  |  <strong>CODEPIPELINE</strong>  |  <strong>GITHUB</strong>  |  <strong>S3</strong>  |  <strong>BITBUCKET</strong>  |  <strong>GITHUB_ENTERPRISE</strong>  |  <strong>NO_SOURCE</strong></p>
<p>In our case it’s  <strong>S3</strong>. We will store our source code as a zip in s3 bucket spring3-hibernate-app-bucket. Mention s3 object key as well and that will be the name of source code file that you have uploaded in s3 bucket.</p>
<p><img src="https://blog2opstree.files.wordpress.com/2020/10/image-19.png?w=1024" alt=""></p>
<p>Next step is to define  <strong>Environment</strong>  on which  <strong>CodeBuild</strong>  project will run. You can use  <strong>AWS Managed Image</strong>  or your  <strong>Custom Image</strong>  from  <strong>ECR</strong>. For simplicity I am using AWS managed image here as Amazon Linux 2 OS.</p>
<p>Then you need to select  <strong>Service Role</strong>.  <strong>AWS</strong>  by default provides you a new service role which will give your  <strong>CodeBuild</strong>  project access to  <strong>S3</strong>  ,  <strong>CloudWatch</strong>  logs etc as per your configuration.</p>
<p><img src="https://blog2opstree.files.wordpress.com/2020/10/image-20.png?w=1024" alt=""></p>
<p>Select the compute size of  <strong>CodeBuild</strong>  project as per the requirement. In our case  <strong>3 GB memory</strong>  would be enough.</p>
<p><img src="https://blog2opstree.files.wordpress.com/2020/10/image-21.png?w=1024" alt=""></p>
<p>For more info on <strong>Codebuild</strong> project , refer AWS docs <a href="https://docs.aws.amazon.com/codebuild/latest/userguide/welcome.html">https://docs.aws.amazon.com/codebuild/latest/userguide/welcome.html</a></p>
<p>Now the main part comes which is  <strong>BuildSpec</strong>. Here you need to specifiy what commands you want to run to build your application. So there are two options to do the same :</p>
<p><strong>Use a Buildspec file</strong>  : You need to include this file (by default  <strong>buildspec.yml</strong> filename) in root directory of your source code. (This is what we will do in next step).</p>
<p><strong>OR</strong></p>
<p><strong>Insert Build commands</strong>: You can simply enter commands in the console that you want to run.</p>
<p><img src="https://i.imgur.com/fnf0aEk.png" alt="Imgur"></p>
<p>like this.</p>
<h2 id="code-deploy">Code Deploy</h2>
<p>AWS CodeDeploy is a fully managed deployment service that automates the process of deploying applications to a variety of compute services, including Amazon EC2 instances, Lambda functions, and on-premises servers. It helps developers release new features and updates more reliably and efficiently by automating the deployment process and minimizing downtime.</p>
<p>Key features and concepts of AWS CodeDeploy include:</p>
<ol>
<li>
<p><strong>Deployment Groups</strong>: A deployment group is a set of target instances that you define for a deployment. These instances can be EC2 instances, on-premises servers, or even AWS Lambda functions. Deployment groups allow you to organize your deployment targets based on factors like environment, application component, or version.</p>
</li>
<li>
<p><strong>Deployment Configurations</strong>: A deployment configuration specifies how a deployment is executed, including parameters like the deployment type (in-place or blue/green), the update policy, and the traffic routing configuration (for blue/green deployments).</p>
</li>
<li>
<p><strong>Deployment Types</strong>:</p>
<ul>
<li><strong>In-Place Deployment</strong>: In this mode, the application is deployed directly on the existing instances, replacing the existing version. It’s suitable for applications where a short downtime window is acceptable.</li>
<li><strong>Blue/Green Deployment</strong>: In this mode, a new set of instances (the “blue” environment) is created alongside the existing instances (the “green” environment). The new version of the application is deployed to the blue environment, and once it’s deemed successful, traffic is gradually shifted from the green environment to the blue environment. This helps minimize downtime and allows easy rollback if issues are detected.</li>
</ul>
</li>
<li>
<p><strong>AppSpec File</strong>: An AppSpec file (short for Application Specification) is a YAML or JSON file that you include with your application code. It defines how CodeDeploy should deploy the application, including hooks for pre and post-deployment actions, such as stopping or starting services, running scripts, or migrating databases.</p>
</li>
<li>
<p><strong>Rollbacks</strong>: CodeDeploy allows you to automate rollback actions in case a deployment does not meet specified criteria or if issues are detected during the deployment process. This helps maintain application availability and reliability.</p>
</li>
<li>
<p><strong>Deployment Hooks</strong>: Deployment hooks in the AppSpec file enable you to define actions to be taken at various stages of the deployment process. These hooks provide flexibility to customize the deployment process to fit your application’s requirements.</p>
</li>
<li>
<p><strong>Integration with Other AWS Services</strong>: CodeDeploy can be integrated with other AWS services such as AWS CodePipeline for end-to-end continuous integration and continuous delivery (CI/CD) workflows.</p>
</li>
<li>
<p><strong>CLI and SDKs</strong>: AWS CodeDeploy provides command-line tools (CLI) and software development kits (SDKs) for various programming languages, allowing you to automate deployments and integrate them into your existing development and automation workflows.</p>
</li>
</ol>
<p>AWS CodeDeploy simplifies and automates the deployment process, helping you avoid manual errors, reduce deployment downtime, and achieve consistent and repeatable deployments. It supports a wide range of application types and environments, making it a valuable tool for any developer looking to streamline their deployment process on AWS.</p>
<p><strong><em>Create CodeDeploy App</em></strong></p>
<p>We will use  <strong>Codedeploy</strong>  service to fetch latest  <strong>build</strong>  <strong>artifact</strong>  and deploy it to the target instances one by one. But to make it work , you need to install  <a href="https://docs.aws.amazon.com/codedeploy/latest/userguide/codedeploy-agent-operations-install-cli.html"><strong>codedeploy</strong>–<strong>agent</strong></a> in your Ec2 machines .</p>
<p>So Navigate to CodeDeploy service and click on  <strong>Create Application</strong>. Mention  <strong>CodeDeploy</strong>  app name and select  <strong>Ec2/On-premises</strong>  as a Compute platform as we will be deploying app in Ec2. And then click on  <strong>Create Application</strong></p>
<p><img src="https://blog2opstree.files.wordpress.com/2020/10/image-24.png?w=1024" alt=""></p>
<p>Now we need to create a  <strong>deployment group</strong> which will define on which instances it will deploy  <strong>artifatcs</strong>.</p>
<p>Click on  <strong>Create Deployment Group</strong></p>
<p><img src="https://blog2opstree.files.wordpress.com/2020/10/image-25.png?w=1024" alt=""></p>
<p>Mention  <strong>deployment group</strong>  name. After that provide  <strong>Service role Arn</strong>. You can create a service role in IAM with  <a href="https://console.aws.amazon.com/iam/home?region=ap-southeast-1#/policies/arn%3Aaws%3Aiam%3A%3Aaws%3Apolicy%2Fservice-role%2FAWSCodeDeployRole">AWSCodeDeployRole</a>  IAM policy attach and add  <strong>codedeploy service</strong>  as a Trust entity.</p>
<p>And then you need to specify the type of deployment you need to do … either  <strong>IN-PLACE</strong>  or  <strong>BLUE/GREEN</strong>. In this blog we will be using  <strong>In-place deployment.</strong></p>
<p><img src="https://blog2opstree.files.wordpress.com/2020/10/image-26.png?w=1024" alt=""></p>
<p>Now Select Amazon  <strong>Ec2</strong>  instance in  <strong>Environment Configuration</strong>  and then we need provide tags . On the basis of tags provided  <strong>CodeDeploy</strong>  will fetch target instances. In my case I gave tag  <strong>app:spring3hibernate</strong>  and  <strong>env:prod</strong>  . So whichever  <strong>Ec2</strong>  servers having such tags on them ,  <strong>CodeDeploy</strong>  will deploy  <strong>artifacts</strong>  in them.</p>
<p><img src="https://blog2opstree.files.wordpress.com/2020/10/image-27.png?w=1024" alt=""></p>
<p>Now if you have already installed  <strong>code-deploy agent</strong>  in your  <strong>Ec2</strong>  servers, select Never option … otherwise select other option so that  <strong>System manager</strong> automatically install this agent in your target servers.</p>
<p>In Deployment settings section, select  <strong>CodeDeployDefaultOneAtATime</strong>  which is CodeDeploy inbuilt deployment configuration . You can create custom one too.</p>
<p><img src="https://blog2opstree.files.wordpress.com/2020/10/image-29.png?w=1024" alt=""></p>
<p>So in last part of  <strong>CodeDeploy</strong>  , we need tell  <strong>CodeDeploy</strong>  about the  <strong>Load Balancer</strong> and the target group under which the target instances are attached, so that at the time of deployment  <strong>Load balancer</strong>  will block all traffic from each target server.</p>
<p><strong>NOTE:</strong> Uncheck  <strong>Enable Load Balancing</strong>  in case you dont have target servers under  <strong>load balancer</strong>.</p>
<p><img src="https://blog2opstree.files.wordpress.com/2020/10/image-30.png?w=1024" alt=""></p>
<p>For more info on  <strong>CodeDeploy</strong>, refer AWS docs  <a href="https://docs.aws.amazon.com/codedeploy/latest/userguide/welcome.html">https://docs.aws.amazon.com/codedeploy/latest/userguide/welcome.html</a></p>
<h2 id="code-pipeline">Code Pipeline</h2>
<p>AWS CodePipeline is a fully managed continuous integration and continuous delivery (CI/CD) service that helps you automate and streamline the process of building, testing, and deploying your code changes. It enables you to deliver updates to your applications and services more efficiently, reliably, and frequently. CodePipeline automates the steps of your software release process, making it easier to maintain a consistent and efficient software delivery workflow.</p>
<p>Here’s how AWS CodePipeline works:</p>
<ol>
<li>
<p><strong>Pipeline</strong>: A pipeline in CodePipeline represents the workflow of your software release process. It consists of a series of stages that represent different phases of your CI/CD process, such as source code version control, build, test, and deployment. Each stage contains one or more actions.</p>
</li>
<li>
<p><strong>Source Stage</strong>: The source stage is where you define your source code repository, such as AWS CodeCommit, GitHub, or Amazon S3. CodePipeline monitors this repository for changes, and when a change is detected, it triggers the pipeline to start.</p>
</li>
<li>
<p><strong>Build and Test Stages</strong>: These stages involve actions like building your application code, running automated tests, and generating deployable artifacts. AWS CodeBuild or other build services can be used for this purpose.</p>
</li>
<li>
<p><strong>Deployment Stages</strong>: After successful testing, you can have one or more deployment stages to deploy your application to different environments, such as development, staging, and production. CodePipeline supports deployment to various AWS services like Amazon EC2, AWS Elastic Beanstalk, AWS Lambda, and more.</p>
</li>
<li>
<p><strong>Manual Approval Actions</strong>: You can also add manual approval actions within your pipeline. These actions require human intervention before the pipeline proceeds to the next stage. This is useful for ensuring control and oversight over critical changes.</p>
</li>
<li>
<p><strong>Artifact Store</strong>: Throughout the pipeline, CodePipeline stores the generated artifacts, such as compiled code, binaries, or packaged applications, in a temporary storage location.</p>
</li>
<li>
<p><strong>Visualization and Monitoring</strong>: CodePipeline provides a graphical representation of your pipeline, showing the flow of stages and actions. You can monitor the progress and status of your pipeline in the AWS Management Console or receive notifications through Amazon SNS or other notification services.</p>
</li>
<li>
<p><strong>Integration with Other AWS Services</strong>: CodePipeline can integrate with other AWS developer tools and services, such as AWS CodeDeploy, AWS Elastic Beanstalk, AWS Lambda, AWS CloudFormation, and more, allowing you to create end-to-end workflows that suit your application’s needs.</p>
</li>
</ol>
<p>Using AWS CodePipeline offers several benefits:</p>
<ul>
<li>
<p><strong>Automation</strong>: CodePipeline automates the manual steps involved in deploying your application, reducing the risk of human error and increasing the reliability of your releases.</p>
</li>
<li>
<p><strong>Consistency</strong>: The pipeline ensures that every code change goes through the same process, leading to consistent and repeatable deployments.</p>
</li>
<li>
<p><strong>Speed</strong>: By automating and parallelizing tasks, CodePipeline enables faster delivery of new features and updates to your applications.</p>
</li>
<li>
<p><strong>Flexibility</strong>: You can customize your pipeline to accommodate various development and deployment scenarios.</p>
</li>
</ul>
<p><strong>Create CodePipeline</strong></p>
<p>So Far we have created a  <strong>CodeBuild</strong>  project (which will test and build the artifact from java app) and a  <strong>CodeDeploy</strong>  application which will deploy the build artifact generated by  <strong>CodeBuild</strong>  project. But we need some tool which will integrate both services together and Thats where CodePipeline will help us 🙂</p>
<p>Click on  <strong>Create Pipeline</strong> under  <strong>CodePipeline</strong>  service</p>
<p><img src="https://blog2opstree.files.wordpress.com/2020/10/image-31.png?w=1024" alt=""></p>
<p>Enter  <strong>Pipeline name</strong>  and select  <strong>New Service Role</strong>. In Advanced settings, select custom s3 Location for  <strong>artifact</strong>  store.</p>
<p><img src="https://blog2opstree.files.wordpress.com/2020/10/image-32.png?w=1024" alt=""></p>
<p>Now we need to add  <strong>Source stage</strong>  which will act like a trigger for  <strong>Codepipeline</strong>  execution . So whenever there will be some changes in source,  <strong>CodePipeline</strong>  will start execution .</p>
<p>Select  <strong>Source provider</strong>  as  <strong>S3</strong>  and specify bucket name where your source code will be stored.</p>
<p><img src="https://blog2opstree.files.wordpress.com/2020/10/image-33.png?w=1024" alt=""></p>
<p>And now for  <strong>Build</strong>  <strong>stage</strong>  , we will use the same  <strong>CodeBuild</strong>  project  <strong>“build-spring3hibernate-app”</strong>  that we have created above.</p>
<p><img src="https://blog2opstree.files.wordpress.com/2020/10/image-34.png?w=1024" alt=""></p>
<p>And the last part would be the deploy stage and will specify CodeDeploy project  <strong>“deploy-spring3hibernate-app”</strong>  which we have configured earlier.</p>
<p><img src="https://blog2opstree.files.wordpress.com/2020/10/image-35.png?w=1024" alt=""></p>
<p>Review and click on  <strong>Create Pipeline</strong></p>
<p><img src="https://blog2opstree.files.wordpress.com/2020/10/image-36.png?w=1024" alt=""></p>
<p>For more info on  <strong>CodePipeline</strong>, refer AWS docs  <a href="https://docs.aws.amazon.com/codepipeline/latest/userguide/welcome.html">https://docs.aws.amazon.com/codepipeline/latest/userguide/welcome.html</a></p>
<p><strong><em>Step-4 Trigger CodePipeline</em></strong></p>
<p>Now we just need to trigger our CodePipeline by uploading our source code zip file in s3 bucket.</p>
<p><img src="https://blog2opstree.files.wordpress.com/2020/10/image-49.png?w=1024" alt=""></p>
<p>You have done enough now . It’s time to  <strong>SIT AND RELAX</strong>  . …… 🙂</p>
<p>So  <strong>CodePipeline</strong>  triggered and also completed successfully.  <strong>CodePipeline</strong>  provides  <strong>visualisation</strong>  for us. So in CodePipeline we can see the execution status of each stage in a  <strong>centralised</strong>  place.</p>
<p><img src="https://blog2opstree.files.wordpress.com/2020/10/image-48.png?w=1024" alt=""></p>
<p>Lets test it whether our code is deployed properly or not by simply hitting ALB DNS.</p>
<p><img src="https://blog2opstree.files.wordpress.com/2020/10/screenshot-2020-10-15-at-10.28.21-pm.png?w=1024" alt=""></p>
</div>
</body>

</html>
