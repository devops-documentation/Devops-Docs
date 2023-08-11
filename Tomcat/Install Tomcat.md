<h1 id="introduction">Introduction</h1>
<p>Apache Tomcat is an open-source  <a href="https://phoenixnap.com/blog/web-server-vs-application-server">web server</a>  and servlet container for Java code. Tomcat executes programs written in the Java programming language, and it implements many  <a href="https://phoenixnap.com/glossary/java-ee">Java EE</a>  specifications, including Jakarta Servlet, Jakarta Server Pages, and others.</p>
<p>Java JRE installed and configured<br>
Prerequisites:</p>
<ul>
<li><a href="https://github.com/devops-pavan-2001/pavan-123/blob/master/JDK/install%20JDk.md">Java JRE installed and configured</a></li>
<li>Administrator privileges</li>
</ul>
<h2 id="how-to-install-tomcat-on-windows">How to Install Tomcat on Windows</h2>
<p>In this section, we will cover two ways of installing the Tomcat web server:</p>
<ul>
<li>Via Windows Service Installer.</li>
<li>From a zip archive.</li>
</ul>
<p>Follow the steps below to download and install Tomcat.</p>
<h3 id="step-1-download-tomcat-for-windows">Step 1: Download Tomcat for Windows</h3>
<p>To download the Tomcat installation file, follow the steps below:</p>
<ol>
<li>Browse to the  <a href="https://tomcat.apache.org/">official Apache Tomcat website</a>. Locate the  <em>Download</em>  section and click the  <strong>latest Tomcat version</strong>  available. At the time of writing this article, the latest Tomcat version was version 10.</li>
</ol>
<p><img src="https://i.imgur.com/vBexGsl.png" alt="Imgur"></p>
<ol start="2">
<li>On the  <em>Download</em>  page, scroll down and locate the  <em>Binary Distributions</em>  area.</li>
</ol>
<p>In the  <em>Core</em>  list, depending on the installation type you prefer, click the download link for the  <strong>Windows Service Installer</strong>  or the  <strong>32bit</strong>/<strong>64bit Windows zip file</strong>.</p>
<p><img src="https://i.imgur.com/V56x069.png" alt="Imgur"></p>
<h3 id="step-2-install-tomcat">Step 2: Install Tomcat</h3>
<p>Install Tomcat via the  <strong>Windows Service Installer</strong>  for an automated and wizard-guided experience. The service installer installs the Tomcat service and runs it automatically when the system boots.</p>
<p>For a portable experience, install Tomcat using the  <strong>zip file</strong>  and avoid installing the service. Easily uninstall Tomcat when it is no longer needed by deleting the Tomcat directory, or move it around when necessary.</p>
<h4 id="method-1-install-tomcat-using-the-windows-service-installer">Method 1: Install Tomcat Using the Windows Service Installer</h4>
<p>Follow the steps below to install Tomcat using the Windows Service Installer.</p>
<ol>
<li>
<p>Open the downloaded  <strong>Windows Service Installer</strong>  file to start the installation process.</p>
</li>
<li>
<p>In the Tomcat Setup welcome screen, click  <strong>Next</strong> to proceed.</p>
</li>
</ol>
<p><img src="https://i.imgur.com/Gswhmw9.png" alt="Imgur"></p>
<ol start="3">
<li>Read the License Agreement and if you agree to the terms, click <strong>I Agree</strong> to proceed to the next step.</li>
</ol>
<p><img src="https://i.imgur.com/8oEpEJM.png" alt="Imgur"></p>
<ol start="4">
<li>In the Tomcat component selection screen, choose <strong>Full</strong> in the dropdown menu to ensure the wizard installs the Tomcat Host Manager and Servlet and JSP examples web applications. Alternatively, keep the default <strong>Normal</strong> installation type and click <strong>Next</strong>.</li>
</ol>
<p><img src="https://i.imgur.com/CzhJTW3.png" alt="Imgur"></p>
<ol start="5">
<li>The next step configures the Tomcat server. For instance, enter the <strong>Administrator login credentials</strong> or choose a different <strong>connection port</strong>. When finished, click <strong>Next</strong> to proceed to the next step.</li>
</ol>
<p><img src="https://i.imgur.com/BDf1MIy.png" alt="Imgur"></p>
<ol start="6">
<li>The next step requires you to enter the full path to the JRE directory on your system. The wizard auto-completes this if you have previously <a href="https://phoenixnap.com/kb/install-java-windows#ftoc-heading-6">set up the Java environment variables</a>. Click <strong>Next</strong> to proceed to the next step.</li>
</ol>
<p><img src="https://i.imgur.com/sFRlCUw.png" alt="Imgur"></p>
<ol start="7">
<li>Choose the Tomcat server install location or keep the default one and click <strong>Install</strong>.</li>
</ol>
<p><img src="https://i.imgur.com/owuSYk5.png" alt="Imgur"></p>
<ol start="8">
<li>
<p>Check the <strong>Run Apache Tomcat</strong> box to start the service after the installation finishes. Optionally, check the <strong>Show Readme</strong> box to see the Readme file. To complete the installation, click <strong>Finish</strong>.</p>
</li>
<li>
<p>A popup window appears that starts the Tomcat service. After the process completes, the window closes automatically. The Apache Tomcat web server is now successfully installed .</p>
</li>
</ol>
<p><img src="https://phoenixnap.com/kb/wp-content/uploads/2022/02/starting-tomcat-service.png" alt="Starting the Apache Tomcat Windows service."></p>
<h4 id="method-2-install-tomcat-using-the-zip-archive">Method 2: Install Tomcat Using the zip Archive</h4>
<p>Follow the steps below to set up the Tomcat server using the  <strong>zip archive</strong>.</p>
<ol>
<li>
<p>After downloading the  <strong>32bit</strong>/<strong>64bit Windows zip file,</strong> depending on your Windows version,  <strong>unzip</strong>  the downloaded file. Right-click the file and select  <strong>Extract all…</strong></p>
</li>
<li>
<p>Choose where to extract the archive contents. For easier navigation, we recommend extracting it to the hard drive’s root. Optionally, give the directory a shorter name to facilitate server configuration later. Click  <strong>Extract</strong>  to start the process.</p>
</li>
</ol>
<p><img src="https://phoenixnap.com/kb/wp-content/uploads/2022/02/extract-tomcat-zip-archive.png" alt="Extracting the Tomcat server zip file."></p>
<ol start="3">
<li>Navigate to the  <em>conf</em>  sub-directory within the extracted directory and locate the  <strong>server.xml</strong>  file.</li>
<li>The default connection port is  <strong><code>8080</code></strong>. To choose a different port, edit the  <strong>server.xml</strong>  file with a text editor, such as Notepad++, and locate the following lines:</li>
</ol>
<pre><code>&lt;Connector port="8080" protocol="HTTP/1.1"
           connectionTimeout="20000"
           redirectPort="8443" /&gt;
</code></pre>
<p>Change the  <strong><code>connector port</code></strong>  number to any number between  <strong><code>1024</code></strong>  and  <strong><code>65535</code></strong>.</p>
<ol start="5">
<li>To  <a href="https://phoenixnap.com/kb/403-forbidden#ftoc-heading-9">enable directory browsing</a>, locate the  <strong>web.xml</strong>  file in the  <em>conf</em>  directory and edit the file with a text editor. Directory browsing helps when testing the system, and sometimes it may be the  <a href="https://phoenixnap.com/kb/403-forbidden">solution for a 403 forbidden error</a>.</li>
</ol>
<p>Locate the following lines and change the  <strong><code>listings</code></strong>  value from  <strong><code>false</code></strong>  to  <strong><code>true</code></strong>:</p>
<pre><code>&lt;servlet&gt;
  &lt;servlet-name&gt;default&lt;/servlet-name&gt;
  &lt;servlet-class&gt;org.apache.catalina.servlets.DefaultServlet&lt;/servlet-class&gt;
  &lt;init-param&gt;
    &lt;param-name&gt;debug&lt;/param-name&gt;
    &lt;param-value&gt;0&lt;/param-value&gt;
  &lt;/init-param&gt;
  &lt;init-param&gt;
    &lt;param-name&gt;listings&lt;/param-name&gt;
    &lt;param-value&gt;false&lt;/param-value&gt;
  &lt;/init-param&gt;
  &lt;load-on-startup&gt;1&lt;/load-on-startup&gt;
&lt;/servlet&gt;
</code></pre>
<ol start="6">
<li>Implement an auto-reload feature by editing the  <strong>context.xml</strong>  file. Above all, auto-reload is useful in development to prevent restarting the server manually each time a change is made.</li>
</ol>
<p>Using a text editor, open the  <strong>context.xml</strong>  file. Locate the following line and change the value from  <strong><code>false</code></strong>  to  <strong><code>true</code></strong>  in each instance:</p>
<pre><code>&lt;Context reloadable="false" crossContext="false" parallelAnnotationScanning="false"&gt;
   ......
   ......
&lt;/Context&gt;

</code></pre>
<ol start="7">
<li>
<p>After making the changes, start the server. Press the  <strong>Windows key</strong>  and type  <em>cmd</em>. Press  <strong>Enter</strong>  to open a Command Prompt window.</p>
</li>
<li>
<p>Move to the  <em>bin</em>  directory of your Tomcat server and run:</p>
</li>
</ol>
<pre><code>startup
</code></pre>
<p><img src="https://phoenixnap.com/kb/wp-content/uploads/2022/02/start-apache-tomcat-server.png" alt="Starting the Tomcat server in Windows."></p>
<ol start="8">
<li>Add an exception for Tomcat in the firewall:</li>
</ol>
<p><img src="https://phoenixnap.com/kb/wp-content/uploads/2022/02/allow-tomcat-in-firewall.png" alt="Allowing Tomcat network access in Windows Firewall."></p>
<ol start="9">
<li>A new Tomcat console window appears. This console receives error messages and  <strong><code>system.out.println()</code></strong>  messages issued by the Java servlets.</li>
</ol>
<p><img src="https://phoenixnap.com/kb/wp-content/uploads/2022/02/starting-tomcat-server.png" alt="Tomcat console windows displaying server status."></p>
<ol start="10">
<li>Access the server using a browser as an HTTP client. Browse to <a href="http://localhost:8080">http://localhost:8080</a> and access the Tomcat welcome page to ensure the server works.</li>
</ol>
<p>In addition, use the  <em>Developer Quick Start</em>  links to see more information about the server and start using and configuring the server.</p>
<p><img src="https://phoenixnap.com/kb/wp-content/uploads/2022/02/test-tomcat-server.png" alt="Apache Tomcat server welcome screen."></p>
<ol start="11">
<li>Shut down the Tomcat server by pressing  <strong>Ctrl+C</strong>  on the Tomcat console.</li>
</ol>
<h3 id="step-3-check-if-apache-tomcat-service-is-running">Step 3: Check if Apache Tomcat Service Is Running</h3>
<p>Installing Tomcat using the Windows Service Installer installs Tomcat as a Windows service that automatically runs on boot. Follow the steps below to ensure that Tomcat is started as a Windows service.</p>
<ol>
<li>
<p>Open the  <strong>Start</strong>  menu and search for  <em>Services</em>.</p>
</li>
<li>
<p>Select the  <strong>Services</strong>  result.</p>
</li>
</ol>
<p><img src="https://phoenixnap.com/kb/wp-content/uploads/2022/02/open-services.png" alt="Opening the Services app in Windows."></p>
<ol start="3">
<li>In the  <em>Services</em>  window, locate the  <em>Apache Tomcat</em>  service. The  <em>Status</em>  column indicates whether the service is running or not.  <strong>Start</strong>  or  <strong>Stop</strong>  the service using the buttons in the toolbar or by pressing  <strong>Stop</strong>  or  <strong>Restart</strong>  on the left side of the service list.</li>
</ol>
<p><img src="https://phoenixnap.com/kb/wp-content/uploads/2022/02/tomcat-service-properties.png" alt="Starting or stopping the Tomcat service in Windows."></p>
<p>Configure the service startup by right-clicking the  <strong>Tomcat service</strong>  and selecting  <strong>Properties</strong>.</p>
<ol start="4">
<li>In the  <em>Properties</em>  window, under the  <em>Startup type</em>  dropdown menu, select how to run the Tomcat service:</li>
</ol>
<ul>
<li><strong>Automatic (Delayed Start)</strong>. Starts the service shortly after boot. A delayed start improves server boot performance and has security benefits.</li>
<li><strong>Automatic</strong>. Automatically starts the service on boot.</li>
<li><strong>Manual</strong>. The service starts only when Windows or another service needs it or if invoked.</li>
<li><strong>Disabled</strong>. Disables the service startup, even if you try to start it.</li>
</ul>
<p><img src="https://phoenixnap.com/kb/wp-content/uploads/2022/02/tomcat-service-configuration.png" alt="Configuring the Tomcat service startup in Windows."></p>
<p>Click  <strong>OK</strong>  to confirm the changes.</p>
<h1 id="install-tomcat-on-linux">Install Tomcat on Linux</h1>
<p>To install Apache Tomcat on a Linux system, you can follow these general steps. Please note that specific commands might vary depending on your Linux distribution.</p>
<ol>
<li>
<p><strong>Update Package Repository:</strong>(For Ubuntu/Debian) Before installing any software, it’s a good practice to update your package repository to ensure you are installing the latest versions of packages.</p>
<p>bashCopy code</p>
<pre><code>sudo apt update 
</code></pre>
</li>
<li>
<p><strong>Install Java Development Kit (JDK):</strong> Apache Tomcat requires Java to run. Install the JDK using the package manager appropriate for your Linux distribution.</p>
<p>For Ubuntu/Debian:</p>
<p>bashCopy code</p>
<pre><code>sudo apt install default-jdk 
</code></pre>
<p>For CentOS/RHEL:</p>
<p>bashCopy code</p>
<pre><code>sudo yum install java-1.8.0-openjdk-devel
</code></pre>
</li>
<li>
<p><strong>Download Tomcat:</strong> Visit the official Apache Tomcat website and download the desired version of Tomcat. You can use <code>wget</code> or <code>curl</code> to download it directly to your server.</p>
<p>bashCopy code</p>
<pre><code>wget https://downloads.apache.org/tomcat/tomcat-X/vX.XX.XX/bin/apache-tomcat-X.XX.XX.tar.gz 
</code></pre>
</li>
<li>
<p><strong>Extract Tomcat:</strong> Extract the downloaded archive to a location on your system.</p>
<p>bashCopy code</p>
<pre><code>tar -xvf apache-tomcat-X.XX.XX.tar.gz
</code></pre>
</li>
<li>
<p><strong>Move Tomcat:</strong> Move the extracted Tomcat folder to a desired location, such as <code>/opt</code>.</p>
<p>bashCopy code</p>
<pre><code>sudo mv apache-tomcat-X.XX.XX /opt/tomcat 
</code></pre>
</li>
<li>
<p><strong>Configure Environment Variables:</strong> Set the necessary environment variables. Open the <code>.bashrc</code> or <code>.bash_profile</code> file in your home directory and add the following lines:</p>
<p>bashCopy code</p>
<pre><code>export CATALINA_HOME=/opt/tomcat
</code></pre>
<p>export PATH=<span class="katex--inline"><span class="katex"><span class="katex-mathml"><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><mi>P</mi><mi>A</mi><mi>T</mi><mi>H</mi><mo>:</mo></mrow><annotation encoding="application/x-tex">PATH:</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height: 0.68333em; vertical-align: 0em;"></span><span class="mord mathnormal" style="margin-right: 0.13889em;">P</span><span class="mord mathnormal">A</span><span class="mord mathnormal" style="margin-right: 0.13889em;">T</span><span class="mord mathnormal" style="margin-right: 0.08125em;">H</span><span class="mspace" style="margin-right: 0.277778em;"></span><span class="mrel">:</span></span></span></span></span>CATALINA_HOME/bin</p>
</li>
<li>
<p><strong>Reload Shell Configuration:</strong> Apply the changes made to the environment variables by either restarting your shell or running:</p>
<p>bashCopy code</p>
<pre><code>source ~/.bashrc 
</code></pre>
</li>
<li>
<p><strong>Start Tomcat:</strong> Start the Tomcat server using the <code>startup.sh</code> script.</p>
<p>bashCopy code</p>
<pre><code>$CATALINA_HOME/bin/startup.sh
</code></pre>
</li>
<li>
<p><strong>Access Tomcat:</strong> Open your web browser and access Tomcat at public ip address of your ubuntu eg: <code>192.168.33.10:8080</code></p>
</li>
</ol>

