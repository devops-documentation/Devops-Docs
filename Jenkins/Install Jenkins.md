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

