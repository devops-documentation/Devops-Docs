<h1 id="jenkins-build-set-up-freestyle-project-in-jenkins">Jenkins Build: Set Up Freestyle Project in Jenkins</h1>
<h2 id="what-is-a-build-job">What Is a Build Job?</h2>
<p>A Jenkins build job contains the configuration for automating a specific task or step in the application building process. These tasks include gathering dependencies, compiling, archiving, or transforming code, and testing and deploying code in different environments.</p>
<p>Jenkins supports several types of build jobs, such as freestyle projects, pipelines, multi-configuration projects, folders, multibranch pipelines, and organization folders.</p>
<h2 id="what-is-a-jenkins-freestyle-project">What is a Jenkins Freestyle Project?</h2>
<p>Jenkins freestyle projects allow users to automate simple jobs, such as running tests, creating and packaging applications, producing reports, or executing commands. Freestyle projects are repeatable and contain both build steps and post-build actions.Even though freestyle jobs are highly flexible, they support a limited number of general build and post-build actions. Any specialized or non-typical action a user wants to add to a freestyle project requires additional plugins.</p>
<h2 id="how-to-set-up-a-build-job-in-jenkins">How to Set up a Build Job in Jenkins</h2>
<p>Follow the steps outlined below to set up and run a new Jenkins freestyle project.</p>
<h3 id="prerequisites">Prerequisites:</h3>
<ul>
<li>Download <code>Deploy war to container</code> plugin. in Dashboard click on manage Jenkins</li>
<li>Go to manage plugins</li>
</ul>
<h2 id="section"><img src="https://i.imgur.com/QPFVlYP.png" alt="Imgur"></h2>
<ul>
<li>click on available and and search for Deploy war to container</li>
</ul>
<p><img src="https://i.imgur.com/KCLJaQ6.png" alt="Imgur"></p>
<h4 id="save-tomcat-credentials">Save tomcat credentials</h4>
<ul>
<li>To deploy war file to tomcat we need to store credentials. click on manage Jenkins and click on credentials.</li>
</ul>
<p><img src="https://i.imgur.com/iSqT7sK.png" alt="Imgur"></p>
<ul>
<li>click on global<br>
<img src="https://i.imgur.com/ijXJEwf.png" alt="Imgur"></li>
<li>click on add credentials<br>
<img src="https://i.imgur.com/4lZbd9Z.png" alt="Imgur"></li>
<li>Enter your tomcat username and password. click on create:</li>
</ul>
<p><img src="https://i.imgur.com/vBjmgNl.png" alt="Imgur"></p>
<h3 id="step-1-create-a-new-freestyle-project">Step 1: Create a New Freestyle Project</h3>
<ol>
<li>Click the  <strong>New Item</strong>  link on the left-hand side of the Jenkins dashboard.</li>
</ol>
<p><img src="https://i.imgur.com/gVwB2WW.png" alt="Imgur"></p>
<ol start="2">
<li>select freestyle project and click OK</li>
</ol>
<p><img src="https://i.imgur.com/08DNLL6.png" alt="Imgur"></p>
<ol start="3">
<li>Add description to project</li>
</ol>
<p><img src="https://i.imgur.com/nEihLlj.png" alt="Imgur"></p>
<ol start="4">
<li>Enter git repository link and branch</li>
</ol>
<p><img src="https://i.imgur.com/2xYQG8Q.png" alt="Imgur"></p>
<p><img src="https://i.imgur.com/JKRj8d6.png" alt="Imgur"></p>
<ol start="5">
<li>Next, In Build stage select maven</li>
</ol>
<p><img src="https://i.imgur.com/j5e1IxX.png" alt="Imgur"></p>
<p><img src="https://i.imgur.com/QTITGxK.png" alt="Imgur"></p>
<ol start="6">
<li>In post-build actions select Deploy war to a container</li>
</ol>
<p><img src="https://i.imgur.com/NQqkWDb.png" alt="Imgur"></p>
<ol start="7">
<li>Enter war file name (eg: **/*war) Add context path and click add container.</li>
</ol>
<p><img src="https://i.imgur.com/P4IBanc.png" alt="Imgur"></p>
<ol start="8">
<li>In container section click on tomcat</li>
</ol>
<p><img src="https://i.imgur.com/mynKUUx.png" alt="Imgur"></p>
<ol start="9">
<li>Add tom cat credential and URL by default tomcat runs on <a href="http://localhost:8080/">http://localhost:8080/</a></li>
</ol>
<p><img src="https://i.imgur.com/AmFPFbO.png" alt="Imgur"></p>
<ol start="10">
<li>NOW, click on save button to save changes to the project.Click the <strong>Build Now</strong> link on the left-hand side of the new project page.</li>
</ol>
<p><img src="https://i.imgur.com/ShBWlJq.png" alt="Imgur"></p>
<ol start="11">
<li>
<p>Click the link to the latest project build in the <em>Build History</em> section.<br>
<img src="https://phoenixnap.com/kb/wp-content/uploads/2022/07/build-history-freestyle-project-jenkins-ui-update.png" alt=""></p>
</li>
<li>
<p>Click the <strong>Console Output</strong> link on the left-hand side to display the output for the commands you entered.</p>
</li>
</ol>
<p><img src="https://phoenixnap.com/kb/wp-content/uploads/2022/07/console-output-item-menu-location-freestyle-project-jenkins-ui-update.png" alt=""></p>
<ol start="13">
<li>The console output indicates that Jenkins is successfully completed the project.</li>
</ol>
<p><img src="https://i.imgur.com/L55AX64.png" alt="Imgur"></p>
<ol start="14">
<li>navigate to the URL <a href="http://localhost:8080/train/">http://localhost:8080/train/</a></li>
</ol>
<p><img src="https://i.imgur.com/bc3BTcW.png" alt="Imgur"></p>

