<h1 id="how-to-use--install-the-aws-cli">How to Use &amp; Install the AWS CLI</h1>
<h2 id="what-is-the-aws-cli-">What is the AWS CLI? |</h2>
<p>The AWS Command Line Interface (CLI) is for managing your AWS services from a terminal session on your own client, allowing you to control and configure multiple AWS services and implement a level of automation.</p>
<p>I will show you how to use the AWS CLI and how to install it on your Windows, Linux, Mac, or Unix Operating System. To see the process to configure the AWS CLI in action.</p>
<h2 id="downloading-and-installing-the-aws-cli">Downloading and installing the AWS CLI</h2>
<p>First, you need to download the AWS CLI. Depending on your operating system, it will require a different method.</p>
<h3 id="linux--macos--unix">Linux / macOS / Unix</h3>
<p><strong>Prerequisites:</strong></p>
<p>You must ensure that you have at least Python 2 version 2.6.5+ or Python 3 version 3.3+ installed. To verify your current version, run the command:</p>
<pre><code>python --version
</code></pre>
<p><strong>Installation:</strong></p>
<p>The recommendation for installing the AWS CLI is to use the bundled installer provided by AWS. The bundled installer includes all dependencies required for the installation.</p>
<ul>
<li>
<p>To begin the installation run the following command:</p>
<pre><code>  curl "https://s3.amazonaws.com/aws-cli/awscli-bundle.zip" -o "awscli-bundle.zip"
</code></pre>
</li>
<li>
<p>Next, you must unzip the downloaded package from step 1:</p>
<pre><code> unzip awscli-bundle.zip
</code></pre>
</li>
</ul>
<p>Once the package in unzipped, you can run the installation:</p>
<pre><code>sudo ./awscli-bundle/install -i /usr/local/aws -b /usr/local/bin/aws
</code></pre>
<p>Using the -b option allows all users to use the AWS CLI from any directory, meaning you will not need to specify the install directory in the user’s $PATH variable.</p>
<h3 id="windows">Windows</h3>
<p><strong>Prerequisites:</strong></p>
<p>You must be running Microsoft Windows XP or later.</p>
<p><strong>Installation:</strong></p>
<p>There are three MSI installers to choose from:</p>
<ul>
<li><a href="https://s3.amazonaws.com/aws-cli/AWSCLI64PY3.msi">64-bit version</a></li>
<li><a href="https://s3.amazonaws.com/aws-cli/AWSCLI32PY3.msi">32-bit version</a></li>
<li><a href="https://s3.amazonaws.com/aws-cli/AWSCLISetup.exe">A CLI Setup file</a> that will automatically detect what you are running and install the appropriate version (64-bit or 32-bit)</li>
</ul>
<ol>
<li>
<p>Select the option required to download the MSI</p>
</li>
<li>
<p>Run the downloaded MSI installer or the CLI setup file, as required</p>
</li>
<li>
<p>Follow the instructions that appear</p>
</li>
</ol>
<p>Once installed, the program files will be stored as shown:</p>
<p><strong>64-bit version</strong></p>
<p>C:\Program Files\Amazon\AWSCLI</p>
<p><strong>32-bit version</strong></p>
<p>C:\Program Files (x86)\Amazon\AWSCLI</p>
<p>To confirm the installation, use the aws –version command at a command prompt.</p>
<h2 id="simple-configuration-of-the-aws-cli">Simple configuration of the AWS CLI</h2>
<p>Once you have installed the AWS CLI, you now need to configure the application to be able to connect to your AWS account. To do so, enter the following from your command prompt:</p>
<pre><code>aws configure
</code></pre>
<p>Through <em>aws configure</em>_,_ the AWS CLI will prompt you for four pieces of information. The first two are required. These are your AWS access key ID and AWS secret access key, which serve as your account credentials. You can generate new credentials within AWS Identity and Access Management (IAM) if you do not already have them. The other information you will need is region and output format, which you can leave as default for the time being.</p>
<pre><code>aws configure 
AWS Access Key ID [None]: AKIAIOSFODNN7EXAMPLE 
AWS Secret Access Key [None]: wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY 
Default region name [None]: us-west-2 
Default output format [None]: json
</code></pre>
<p><img src="https://i.imgur.com/M3rnsR1.png" alt="Imgur"></p>
<p>The default region name simply defines the Region where you requests will be sent to. For all available regions, please see the following: <a href="https://docs.aws.amazon.com/general/latest/gr/rande.html">Regions and Endpoints</a>.</p>
<p>The default output format specifies how the results are formatted. Values that can be used here include:</p>
<ul>
<li>json</li>
<li>text</li>
<li>table</li>
</ul>
<p>The AWS access key ID and AWS secret access key are used to authenticate your AWS account. This authorizes you to carry out specific tasks and functions as defined by your permissions level.</p>
<p>The <strong>AWS access key ID</strong> is made up of 20 random uppercase alphanumeric characters, such as the one displayed on screen.</p>
<p>The <strong>AWS secret access key</strong> is made up of 40 random upper and lowercase alphanumeric and non-alphanumeric characters as displayed.</p>
<p>These access keys can be created for any IAM user who requires authentication from a programmatic perspective, such as when using the AWS CLI.</p>
<h1 id="how-to-use">How To Use</h1>
<ol>
<li><strong>Basic Usage:</strong> Once configured, you can start using the AWS CLI to interact with AWS services. Here are a few basic examples:</li>
</ol>
<ul>
<li><strong>create s3 Bucket:</strong> To create an Amazon S3 bucket using the AWS CLI, you can use the <code>aws s3api create-bucket</code> command. Here’s how you can do it:</li>
</ul>
<pre><code>aws s3api create-bucket --bucket your-bucket-name --region your-preferred-region
</code></pre>
<p><img src="https://i.imgur.com/E1ZDEZp.png" alt="Imgur"></p>
<p>Replace <code>your-bucket-name</code> with the desired name for your S3 bucket, and <code>your-preferred-region</code> with the AWS region where you want to create the bucket (e.g., <code>us-east-1</code> for US East (N. Virginia), <code>us-west-2</code> for US West (Oregon), etc.).</p>
<ul>
<li>
<p><strong>Listing S3 Buckets:</strong> To list your Amazon S3 buckets, use the following command:</p>
<pre><code> aws s3 ls 
</code></pre>
</li>
</ul>
<p><img src="https://i.imgur.com/MuMtyC2.png" alt="Imgur"></p>
<ul>
<li>
<p><strong>Creating an EC2 Instance:</strong> To launch an Amazon EC2 instance, you can use the <code>ec2 run-instances</code> command. For example:</p>
<pre><code> aws ec2 run-instances --image-id ami-12345678 --instance-type t2.micro --key-name MyKeyPair`
</code></pre>
</li>
</ul>
<p><img src="https://i.imgur.com/mGwkeVs.png" alt="Imgur"></p>
<ul>
<li>
<p><strong>Describing EC2 Instances:</strong> To get information about your EC2 instances, you can use the <code>ec2 describe-instances</code> command:</p>
<pre><code>    aws ec2 describe-instances 
</code></pre>
</li>
</ul>
<p><img src="https://i.imgur.com/gYJ6Iyz.png" alt="Imgur"></p>
<ul>
<li>
<p><strong>Listing Lambda Functions:</strong> To list your AWS Lambda functions, you can use the <code>lambda list-functions</code> command:</p>
<pre><code> aws lambda list-functions 
</code></pre>
</li>
</ul>
<p><img src="https://i.imgur.com/CFpwtSj.png" alt="Imgur"></p>
<ol start="2">
<li>
<p><strong>Getting Help:</strong> You can get detailed information about specific commands, options, and parameters by using the <code>--help</code> flag. For example:</p>
<pre><code>aws s3 ls help
</code></pre>
</li>
</ol>
<p><img src="https://i.imgur.com/EUyuHQT.png" alt="Imgur"></p>
<ol start="3">
<li><strong>Additional Resources:</strong> The AWS CLI supports many AWS services, and each service has its own set of commands and options. For more detailed information and examples, refer to the <a href="https://docs.aws.amazon.com/cli/latest/index.html">AWS CLI Command Reference</a>.</li>
</ol>

