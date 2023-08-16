<h1 id="install-jenkins">Install Jenkins</h1>
<p>Open source  <a href="https://jenkins.io/">Jenkins</a>  is a popular tool for test automation and for implementing shifting left through  <a href="https://www.blazemeter.com/blog/cicd-pipeline-jenkins-github">continuous integration</a>  and continuous deployment. Install Jenkins on Windows (learn how on  <a href="https://www.blazemeter.com/blog/how-to-install-jenkins-on-windows">this BlazeMeter blog</a>) or with a WAR (Web application ARchive) file version of Jenkins. This option can be used on any Java-supporting platform or OS.</p>
<p>First, install JDK. Jenkins supports Java 8. Now that Java is installed, we can proceed with installing a Jenkins WAR file.</p>
<ol>
<li>
<p>Download latest <a href="https://get.jenkins.io/war-stable/">War Jenkins Packages</a></p>
</li>
<li>
<p>Next step is copy war file to Tomcat webapps:<br>
<img src="https://i.imgur.com/Y3y49xE.png" alt="Imgur"></p>
</li>
<li>
<p>Now, Open tomcat with URL <a href="http://localhost:8080/jenkins">http://localhost:8080/jenkins</a> in a browser.</p>
</li>
</ol>
<p><img src="https://www.blazemeter.com/sites/default/files/image/2022-06/b1i10.png" alt=""></p>
<ol start="4">
<li>To unlock Jenkins, copy the password from the file intialAdminPassword. This file should be found under the Jenkins installation path. Copy the content of the initialAdminPassword file and paste it into the Administrator password field. Then, click the Continue button.</li>
</ol>
<p><img src="https://www.blazemeter.com/sites/default/files/image/2022-06/b1i11.png" alt=""></p>
<ol start="5">
<li>
<p>You can install either the suggested plugins or selected plugins you choose based on your needs. To keep it simple, we will install the suggested plugins that the Jenkins community finds most useful.<br>
<img src="https://www.blazemeter.com/sites/default/files/image/2022-06/b1i12.png" alt=""></p>
</li>
<li>
<p>Wait until the plugins are completely installed.</p>
</li>
</ol>
<p><img src="https://www.blazemeter.com/sites/default/files/image/2022-06/b1i13.png" alt=""></p>
<ol start="6">
<li>The next thing that you should do is create an Admin user for Jenkins. Then, enter your details and click Save and Continue.</li>
</ol>
<p><img src="https://www.blazemeter.com/sites/default/files/image/2022-06/b1i14.png" alt=""></p>
<ol start="7">
<li>Click on Save and Finish to complete the Jenkins installation</li>
</ol>
<p><img src="https://www.blazemeter.com/sites/default/files/image/2022-06/b1i15.png" alt=""></p>
<ol start="8">
<li>Now, click on the “Start using Jenkins” button to start Jenkins.</li>
</ol>
<p><img src="https://www.blazemeter.com/sites/default/files/image/2022-06/b1i16.png" alt=""></p>
<ol start="9">
<li>Finally, here is the default Jenkins page. Jenkins is now installed and running on Windows, and you are ready to start building your CI/CD pipeline.</li>
</ol>
<p><img src="https://www.blazemeter.com/sites/default/files/image/2022-06/b1i17.png" alt=""></p>
<h1 id="install-on-linux">Install on Linux</h1>
<p>To install Jenkins on a Linux system, you can follow these general steps. Note that the specific commands might vary depending on your Linux distribution. Here, I’ll provide instructions for Debian/Ubuntu and CentOS/RHEL.</p>
<h3 id="debianubuntu">Debian/Ubuntu</h3>
<ol>
<li>
<p>Update the package list:</p>
<pre><code>sudo apt update
</code></pre>
</li>
</ol>
<p><img src="https://i.imgur.com/8FcLpwG.png" alt="Imgur"></p>
<ol start="2">
<li>
<p>Install Java Development Kit (JDK):</p>
<pre><code>sudo apt install default-jdk 
</code></pre>
</li>
</ol>
<p><img src="https://i.imgur.com/sk4iTja.png" alt="Imgur"></p>
<ul>
<li>click on <code>y</code> to continue</li>
</ul>
<ol start="3">
<li>
<p>Add the Jenkins repository key to the system:</p>
<pre><code>wget -q -O - https://pkg.jenkins.io/debian/jenkins.io.key | sudo apt-key add - 
</code></pre>
</li>
</ol>
<p><img src="https://i.imgur.com/HCCqRkk.png" alt="Imgur"></p>
<ol start="4">
<li>
<p>Add the Jenkins repository to the package sources:</p>
<pre><code>sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ &gt; /etc/apt/sources.list.d/jenkins.list' 
</code></pre>
</li>
</ol>
<p><img src="https://i.imgur.com/TutTgK8.png" alt="Imgur"></p>
<ol start="5">
<li>
<p>Update the package list again:</p>
<pre><code>sudo apt update
</code></pre>
</li>
</ol>
<p><img src="https://i.imgur.com/8FcLpwG.png" alt="Imgur"></p>
<ol start="6">
<li>
<p>Install Jenkins:</p>
<pre><code>sudo apt install jenkins 
</code></pre>
</li>
</ol>
<p><img src="https://i.imgur.com/M2Pp6Sk.png" alt="Imgur"></p>
<ol start="7">
<li>
<p>Start the Jenkins service:</p>
<pre><code>   sudo systemctl start jenkins
</code></pre>
</li>
<li>
<p>Enable the Jenkins service to start on boot:</p>
<pre><code>   sudo systemctl enable jenkins
</code></pre>
</li>
<li>
<p>Open your web browser and access Jenkins at public ip address of your ubuntu eg: <code>192.168.33.10:8080</code>. Follow the instructions to complete the setup.</p>
</li>
</ol>
<p><img src="https://i.imgur.com/AQBTLIw.png" alt="Imgur"></p>
<ul>
<li>copy the path to get key and use cat command to see</li>
</ul>
<p><img src="https://i.imgur.com/LO55sTS.png" alt="Imgur"></p>
<p>.  Then, click the Continue button.</p>
<p><img src="https://www.blazemeter.com/sites/default/files/image/2022-06/b1i11.png" alt=""></p>
<ol start="5">
<li>
<p>You can install either the suggested plugins or selected plugins you choose based on your needs. To keep it simple, we will install the suggested plugins that the Jenkins community finds most useful.<br>
<img src="https://www.blazemeter.com/sites/default/files/image/2022-06/b1i12.png" alt=""></p>
</li>
<li>
<p>Wait until the plugins are completely installed.</p>
</li>
</ol>
<p><img src="https://www.blazemeter.com/sites/default/files/image/2022-06/b1i13.png" alt=""></p>
<ol start="6">
<li>The next thing that you should do is create an Admin user for Jenkins. Then, enter your details and click Save and Continue.</li>
</ol>
<p><img src="https://www.blazemeter.com/sites/default/files/image/2022-06/b1i14.png" alt=""></p>
<ol start="7">
<li>Click on Save and Finish to complete the Jenkins installation</li>
</ol>
<p><img src="https://www.blazemeter.com/sites/default/files/image/2022-06/b1i15.png" alt=""></p>
<ol start="8">
<li>Now, click on the “Start using Jenkins” button to start Jenkins.</li>
</ol>
<p><img src="https://www.blazemeter.com/sites/default/files/image/2022-06/b1i16.png" alt=""></p>
<ol start="9">
<li>Finally, here is the default Jenkins page. Jenkins is now installed and running on Windows, and you are ready to start building your CI/CD pipeline.</li>
</ol>
<p><img src="https://www.blazemeter.com/sites/default/files/image/2022-06/b1i17.png" alt=""></p>
<h3 id="centosrhel">CentOS/RHEL</h3>
<ol>
<li>
<p>Install Java Development Kit (JDK):</p>
<pre><code>sudo yum install java-11-openjdk-devel
</code></pre>
</li>
</ol>
<p><img src="https://i.imgur.com/sk4iTja.png" alt="Imgur"></p>
<ul>
<li>click on <code>y</code> to continue</li>
</ul>
<ol start="2">
<li>
<p>Import the Jenkins repository key:</p>
<pre><code>sudo rpm --import https://pkg.jenkins.io/redhat/jenkins.io.key
</code></pre>
</li>
</ol>
<p><img src="https://i.imgur.com/RT7PlOm.png" alt="Imgur"></p>
<ol start="3">
<li>
<p>Add the Jenkins repository:</p>
<pre><code>sudo sh -c 'echo -e "[jenkins]\nname=Jenkins\nbaseurl=http://pkg.jenkins.io/redhat\nenabled=1\ngpgcheck=1" &gt; /etc/yum.repos.d/jenkins.repo' 
</code></pre>
</li>
</ol>
<p><img src="https://i.imgur.com/RT7PlOm.png" alt="Imgur"></p>
<ol start="4">
<li>
<p>Install Jenkins:</p>
<pre><code>sudo yum install jenkins 
</code></pre>
</li>
</ol>
<p><img src="https://i.imgur.com/M2Pp6Sk.png" alt="Imgur"></p>
<ol start="5">
<li>
<p>Start the Jenkins service:</p>
<pre><code>sudo systemctl start jenkins 
</code></pre>
</li>
</ol>
<p><img src="https://i.imgur.com/XRjvlJs.png" alt="Imgur"></p>
<ol start="6">
<li>
<p>Enable the Jenkins service to start on boot:</p>
<pre><code>sudo systemctl enable jenkins
</code></pre>
</li>
</ol>
<p><img src="https://i.imgur.com/z1osJef.png" alt="Imgur"></p>
<ol start="7">
<li>Open your web browser and access Jenkins at <code>http://localhost:8080</code>. Follow the instructions to complete the setup.</li>
</ol>
<p>. To unlock Jenkins, copy the password from the file intialAdminPassword. This file should be found under the Jenkins installation path. Copy the content of the initialAdminPassword file and paste it into the Administrator password field. Then, click the Continue button.</p>
<p><img src="https://www.blazemeter.com/sites/default/files/image/2022-06/b1i11.png" alt=""></p>
<ol start="5">
<li>
<p>You can install either the suggested plugins or selected plugins you choose based on your needs. To keep it simple, we will install the suggested plugins that the Jenkins community finds most useful.<br>
<img src="https://www.blazemeter.com/sites/default/files/image/2022-06/b1i12.png" alt=""></p>
</li>
<li>
<p>Wait until the plugins are completely installed.</p>
</li>
</ol>
<p><img src="https://www.blazemeter.com/sites/default/files/image/2022-06/b1i13.png" alt=""></p>
<ol start="6">
<li>The next thing that you should do is create an Admin user for Jenkins. Then, enter your details and click Save and Continue.</li>
</ol>
<p><img src="https://www.blazemeter.com/sites/default/files/image/2022-06/b1i14.png" alt=""></p>
<ol start="7">
<li>Click on Save and Finish to complete the Jenkins installation</li>
</ol>
<p><img src="https://www.blazemeter.com/sites/default/files/image/2022-06/b1i15.png" alt=""></p>
<ol start="8">
<li>Now, click on the “Start using Jenkins” button to start Jenkins.</li>
</ol>
<p><img src="https://www.blazemeter.com/sites/default/files/image/2022-06/b1i16.png" alt=""></p>
<ol start="9">
<li>Finally, here is the default Jenkins page. Jenkins is now installed and running on Windows, and you are ready to start building your CI/CD pipeline.</li>
</ol>
<p><img src="https://www.blazemeter.com/sites/default/files/image/2022-06/b1i17.png" alt=""></p>

