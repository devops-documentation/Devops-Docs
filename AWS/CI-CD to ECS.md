<h1 id="quick-ci-cd-from-github-actions-with-aws-ecr-ecs-creating-a-serverless-docker-container">Quick CI-CD from GitHub Actions with AWS ECR, ECS creating a serverless Docker container</h1>
<p>There are so many ways to configure your project CI-CD pipeline when deploying to Amazon Web Services (AWS). In this tutorial, I will give the rundown of how to set up a serverless docker container using AWS ECR ECS that would be suitable as a starting point for a smaller size startup or MVP project.</p>
<p>This opinionated CI-CD setup is quick and relatively simple but gives you the power of scaling only when needed and automating your deployment process;</p>
<p><code>Github Actions &gt; Docker Image &gt; ECR &gt; ECS &gt; AWS Fargate</code></p>
<p>The setup we will create can be split into what we will do in Github, docker, and AWS;</p>
<p><strong>Github</strong><br>
— Setting up our project<br>
— Create a Git Action<br>
— Deployment using Git Action</p>
<p><strong>AWS</strong><br>
— Get AWS Security Credentials<br>
— Set up AWS ECR<br>
— Set Task Definitions<br>
— Add ECS Cluster<br>
— ECS Service</p>
<p>Take a look.</p>
<h1 id="github">Github</h1>
<h2 id="setting-up-our-project">Setting up our project</h2>
<p>Navigate to the source code repository.  In this repo we need to add Dockerfile</p>
<pre><code>FROM openjdk:17-alpine
COPY target/api-*.jar /app.jar
EXPOSE 5050
CMD ["java", "-jar", "/app.jar"]
</code></pre>
<p>You want to create your own Dockerfile. After creating Dockerfile push to repository</p>
<h1 id="git-action">Git Action</h1>
<p>Next, let’s set up git actions:</p>
<p>Github &gt;  <code>actions</code>  &gt; search for  <code>ECS</code>  &gt;  <code>Deploy to Amazon ECS</code>  &gt; Set up this workflow by clicking  <code>Configure</code>;</p>
<p><img src="https://miro.medium.com/v2/resize:fit:828/format:webp/1*dJjy1acMprpFM0sN3AN3Ww.png" alt=""></p>
<p>The <code>aws.yml</code> file code view opens up;<br>
<img src="https://miro.medium.com/v2/resize:fit:828/format:webp/1*-QdxgqD9C5gWYX-BvAgQXw.png" alt=""></p>
<p>In the  <code>aws.yml</code>  file, I made some changes such as setting up a hook so you can run the action without committing a push change using the  <code>workflow_dispatch</code>  hook instead of having every change in the branch create a deployment. changed the environments variables such as branch name, task definition name, container name, service, and cluster.</p>
<pre><code>        name: Java CI with Maven
    	on:
    	  push:
    	    branches:
    	      - &lt;your branch name&gt;
    	  workflow_dispatch:  # Run workflow manually
    	jobs:
    	  build:
    	    runs-on: Linux
        steps:
          - uses: actions/checkout@v3  # Check out the repository
          - name: Set up JDK 17
            uses: actions/setup-java@v3
            with:
              java-version: '17'
              distribution: 'temurin'
              cache: maven  # Cache Maven dependencies
          - name: Build with Maven
            run: mvn package  # Build the Java application using Maven
          - name: Build Docker Image
            run: |
              docker image prune -f -a  # Remove all running Docker images
              docker build -t [your image name] .  # Build a Docker image
              docker tag [your image name]:latest &lt;your ECR repository name&gt;  # Tag the Docker image
          - name: Push Image to ECR
            run: |
              aws ecr get-login-password --region [your AWS region] | docker login --username AWS --password-stdin 349295925195.dkr.ecr.ap-south-2.amazonaws.com  # Log in to ECR
              docker push [your ECR repository name]  # Push the Docker image to ECR
              aws ecs describe-task-definition --task-definition [your task definition name] --query taskDefinition --region [your region] &gt; task-definition.json  # Describe task definition and save to JSON file
          - name: Configure AWS credentials
            uses: aws-actions/configure-aws-credentials@v1
            with:
              aws-access-key-id: ${{ secrets.AWS_ACCESS_KEY_ID_ECOHEX_API }}  # Access key ID
              aws-secret-access-key: ${{ secrets.AWS_SECRET_ACCESS_KEY_ECOHEX_API }}  # Secret access key
              aws-region: [your region]  # AWS region
</code></pre>
<p>Here are a few things you should replace with your actual values:</p>
<ol>
<li>Replace <code>&lt;your branch name&gt;</code> with the name of the branch you want to trigger the workflow on.</li>
<li>Replace <code>[your image name]</code> with the name you want to give to your Docker image.</li>
<li>Replace <code>&lt;your ECR repository name&gt;</code> with the name of your Amazon ECR repository.</li>
<li>Replace <code>[your AWS region]</code> with the AWS region you’re using.</li>
<li>Replace <code>[your task definition name]</code> with the name of your AWS ECS task definition.</li>
</ol>
<h1 id="aws-ecr">AWS ECR</h1>
<p>Before starting the workflow we want to create ECR repository. To create repository<br>
navigate to aws :<br>
Go here:  <a href="https://console.aws.amazon.com/ecr/home?region=us-east-1#">https://console.aws.amazon.com/ecr/home</a></p>
<p>Set the name and create the repo;</p>
<p><img src="https://miro.medium.com/v2/resize:fit:1400/format:webp/1*PhYd-9tjv_2yyieVVOQcVA.png" alt=""></p>
<p>Copy the URI —</p>
<p><code>[account Id].dkr.ecr.[region].amazonaws.com/**myrepo**</code></p>
<p>Copy the  <code>Docker</code>  specific image  <code>URI</code>, it will look like this;</p>
<p><img src="https://miro.medium.com/v2/resize:fit:828/format:webp/1*OvJzKokHGpDslPeyfuji2g.png" alt=""></p>
<h1 id="aws-security-credentials"><strong>AWS Security Credentials</strong></h1>
<p>Next, we will set access keys to deploy our container to AWS;</p>
<p>You can get these in;</p>
<ol>
<li>Go to:  <a href="http://aws.amazon.com/">http://aws.amazon.com/</a></li>
<li>Search for IAM &amp; create a IAM user</li>
<li>After creating user go to security credentials</li>
<li>Click &gt;  <strong>Create New Access Key</strong></li>
</ol>
<p><img src="https://miro.medium.com/v2/resize:fit:1400/format:webp/1*WIL9ek2DJmlXDvuA9l0iCg.png" alt=""></p>
<p>Store your key and secret;</p>
<p><img src="https://miro.medium.com/v2/resize:fit:828/format:webp/1*PmTWL05nERzvtqLAn5bvwQ.jpeg" alt=""></p>
<h2 id="attach-polities">Attach polities</h2>
<p>Next, let set two polices to user<br>
<img src="https://i.imgur.com/QN7vgfk.png" alt="Imgur"></p>
<p>Next, let’s set the secret that we will be using in our deployment.</p>
<p>Project  <code>Settings</code>  &gt;  <code>Secrets</code>  &gt;  <code>Actions</code>  and set these up from the values in your AWS account;</p>
<p><a href="https://github.com/%5Byour-repo%5D/new-repo/settings/secrets/actions">https://github.com/[your-repo]/new-repo/settings/secrets/actions</a></p>
<ul>
<li>AWS_ACCESS_KEY_ID — your access key id</li>
<li>AWS_SECRET_ACCESS_KEY — your secret access key</li>
</ul>
<p><img src="https://miro.medium.com/v2/resize:fit:828/format:webp/1*O1u0HJijlwv77kAdUO8Sig.png" alt=""></p>
<p>Instead of storing the static passwords, which is more secured is to use static credentials. That can be done with <code>OpenID</code> connect, this allows reduce the need to store AWS credentials as long-lived GitHub secrets: <a href="https://docs.github.com/en/actions/deployment/security-hardening-your-deployments/configuring-openid-connect-in-amazon-web-services">https://docs.github.com/en/actions/deployment/security-hardening-your-deployments/configuring-openid-connect-in-amazon-web-services</a></p>
<h1 id="start-workflow">Start Workflow</h1>
<p>Next, start the workflow</p>
<p><img src="https://i.imgur.com/kjsVn4u.png" alt="Imgur"></p>
<p>after build was completed it look like this ;</p>
<h2 id="ecr-—-task-definitions">ECR — Task Definitions</h2>
<p>Next, I am setting the task definitions. You can read more about the task def in the AWS Docs:  <a href="https://docs.aws.amazon.com/AmazonECS/latest/developerguide/task_definition_parameters.html">https://docs.aws.amazon.com/AmazonECS/latest/developerguide/task_definition_parameters.html</a></p>
<p>Link:  <a href="https://console.aws.amazon.com/ecs/home?region=us-east-1#/taskDefinitions">https://console.aws.amazon.com/ecs/home</a></p>
<p>Create  <code>new task definitions</code></p>
<p><img src="https://i.imgur.com/yNgbEVj.png" alt="Imgur"></p>
<p><code>Fargate</code> &gt; Next Step</p>
<p><img src="https://i.imgur.com/dWitIKX.png" alt="Imgur"><br>
- Task Definition Name: <strong>123</strong><br>
- Role &gt; ecsTaskExecutionRole<br>
Pick how much you want<br>
- Task memory (GB) &gt; 0.5 GB<br>
- Task CPU (vCPU) &gt; 0.25 GBOpen port 80 and 8000 or whatever port you set;</p>
<h2 id="add-container">Add container</h2>
<p><img src="https://i.imgur.com/QbduDcG.png" alt="Imgur"></p>
<pre><code>Name &gt; 5678
Image &gt; Docker image URI we stored;  
[account Id].dkr.ecr.[region].amazonaws.com/**myrepo**:latestMemory Limits (MiB) &gt; Soft limit &gt; 1024  
Port mappings (add whatever ports you want open) &gt;  
    80  
    8000  
</code></pre>
<p>And create Task definition</p>
<h2 id="add-ecs-cluster--">Add ECS Cluster -</h2>
<p>Next, create a Cluster in ECS clusters:  <a href="https://console.aws.amazon.com/ecs/v2/clusters">https://console.aws.amazon.com/ecs/v2/clusters</a></p>
<p><img src="https://miro.medium.com/v2/resize:fit:828/format:webp/1*1b1M8RhwMElnlP-ll2ntSQ.png" alt=""></p>
<p>I picked the name <code>development-cluster</code><br>
<img src="https://miro.medium.com/v2/resize:fit:1400/format:webp/1*mmJ7NkW8Pe6bjsvbc4iqfw.png" alt=""></p>
<p>We can see our <code>development-cluster</code> listed;</p>
<p><img src="https://miro.medium.com/v2/resize:fit:1400/format:webp/1*1easDBgbW_5f1cbIbnTO3g.png" alt=""></p>
<h1 id="cs-service">CS Service</h1>
<p>Next, create a service. Click the  <code>development-cluster</code>cluster or use the URL;<br>
<a href="https://us-east-1.console.aws.amazon.com/ecs/home">https://us-east-1.console.aws.amazon.com/ecs/home</a>  &gt; Services tab</p>
<p><img src="https://miro.medium.com/v2/resize:fit:1400/format:webp/1*XOyCBt6YKsy3KfQAFK8dFw.png" alt=""></p>
<pre><code>Click Services tab &gt; create- Launch type &gt; FARGATE  
- Service name: **development-service**  
- Number of tasks: 1  
- Next StepLoad balancing- Cluster VPC &gt; first item  
- Subnets &gt; first item  
- Security groups &gt; Edit &gt; 80, 8000 &gt; Save  
- Load balancer type &gt; ALB 
- - Service Auto Scaling &gt; Do not adjust the service’s desired count  
- Next step  
- Create service  
- View service
</code></pre>
<p><img src="https://miro.medium.com/v2/resize:fit:828/format:webp/1*6aQxa2YkguoPIbVJMznJBg.png" alt=""></p>
<p><img src="https://miro.medium.com/v2/resize:fit:828/format:webp/1*MOGjxLbDystA4-s9nRfoEA.png" alt=""></p>
<p>Once you complete setting up the service. It will take a few mins;</p>
<p><code>Last status: pending ... running ...</code></p>
<p><img src="https://i.imgur.com/0UgGYWr.png" alt="Imgur"></p>
<h1 id="deployment-using-git-action">Deployment using Git Action</h1>
<p>This is the final git actions workflow <code>.yml</code> code</p>
<pre><code>name: Java CI with Maven
on:
  push:
    branches:
      - &lt;your-branch-name&gt;
  workflow_dispatch: # run workflow manually
jobs:
  build:
    runs-on: Linux

steps:
  - name: Checkout Repository
    uses: actions/checkout@v2

  - name: Set up JDK 17
    uses: actions/setup-java@v2
    with:
      java-version: '17'
      distribution: 'temurin'
      cache: maven

  - name: Build with Maven
    run: mvn package

  - name: Build Docker Image
    run: |
      docker image prune -f -a
      docker build -t &lt;your-image-name&gt; .
      docker tag &lt;your-image-name&gt;:latest &lt;your-ecr-repository-name&gt;

  - name: Push Image to ECR
    run: |
      aws ecr get-login-password --region &lt;your-aws-region&gt; | docker login --username AWS --password-stdin &lt;your-ecr-repository-uri&gt;
      docker push &lt;your-ecr-repository-uri&gt;
      aws ecs describe-task-definition --task-definition &lt;your-task-definition-name&gt; --query taskDefinition --region &lt;your-region&gt; &gt; task-definition.json

  - name: Configure AWS credentials
    uses: aws-actions/configure-aws-credentials@v1
    with:
      aws-access-key-id: ${{ secrets.AWS_ACCESS_KEY_ID_ECOHEX_API }}
      aws-secret-access-key: ${{ secrets.AWS_SECRET_ACCESS_KEY_ECOHEX_API }}
      aws-region: &lt;your-region&gt;

  - name: Fill in the new image ID in the Amazon ECS task definition
    id: task-def
    uses: aws-actions/amazon-ecs-render-task-definition@v1
    with:
      task-definition: task-definition.json
      container-name: &lt;your-container-name&gt;
      image: &lt;your-ecr-repository-uri&gt;:latest

  - name: Deploy Amazon ECS task definition
    uses: aws-actions/amazon-ecs-deploy-task-definition@v1
    with:
      task-definition: ${{ steps.task-def.outputs.task-definition }}
      service: &lt;your-service-name&gt;
      cluster: &lt;your-cluster-name&gt;
      wait-for-service-stability: true
</code></pre>
<p>Please make sure to replace the placeholders like <code>&lt;your-branch-name&gt;</code>, <code>&lt;your-image-name&gt;</code>, <code>&lt;your-ecr-repository-name&gt;</code>, <code>&lt;your-aws-region&gt;</code>, <code>&lt;your-ecr-repository-uri&gt;</code>, <code>&lt;your-task-definition-name&gt;</code>, <code>&lt;your-region&gt;</code>, <code>&lt;your-container-name&gt;</code>, <code>&lt;your-service-name&gt;</code>, and <code>&lt;your-cluster-name&gt;</code> with appropriate values according to your project and setup.</p>
<p>Now we are ready to deploy our Docker container using the  <code>Deploy to Amazon ECR</code>  git-action we set. If you recall I set it up to deploy using the workflow from a branch instead of automatic deployment, so follow this step to deploy;</p>
<p><code>Click Actions &gt; Deploy to Amazon ECS &gt; Run workflow &gt; Branch: main &gt; Run workflow;</code></p>
<p><img src="https://miro.medium.com/v2/resize:fit:828/format:webp/1*WMV5b8qmnkQ9yEdda75biQ.png" alt=""></p>
<p>This could be easily changed to deploy on a  <code>main</code>  branch push instead.</p>
<p>Click the deployment to confirm all went well, of fix any errors you have;</p>
<p><img src="https://miro.medium.com/v2/resize:fit:828/format:webp/1*4GVwpHdhOZqN3GvDuqxjdA.png" alt=""></p>
<p>If you check ECR the repo should have the image tag with the container we deployed;</p>
<p><img src="https://miro.medium.com/v2/resize:fit:828/format:webp/1*Fv-HQ_ObdANp8U930EGPVg.png" alt=""></p>
<p>And also check the task is running or not.</p>
<p><img src="https://miro.medium.com/v2/resize:fit:828/format:webp/1*okNoCwJkXMzrJtgcm8XVMA.png" alt=""></p>

