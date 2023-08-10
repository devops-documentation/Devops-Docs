<h2 id="java-jdk-download">Java JDK Download</h2>
<p>This article describes the step-by-step process for installing and configuring the JDK on the 2 most popular Computer Operating Systems in order to begin the process of developing Android Applications.</p>
<p><strong>The JDK can be installed on the following Platforms:</strong></p>
<ol>
<li>Microsoft Windows</li>
<li>macOS</li>
</ol>
<h2 id="install-jdk-on-microsoft-windows">Install JDK on Microsoft Windows</h2>
<h3 id="step-1-download-and-install-java-development-kit-jdk"><strong>Step 1: Download and Install Java Development Kit (JDK)</strong></h3>
<p>The very first step is to download the  <strong>Oracle Java Development Kit (JDK)</strong>  from the Official Oracle Website. For that, Head over to the  <a href="https://www.oracle.com/java/technologies/downloads/#jdk18-windows">Official Website</a>.<br>
<img src="https://media.geeksforgeeks.org/wp-content/uploads/20220622114149/Step1DownloadingJDKforWindows.png" alt="jdk"></p>
<p>You need to identify your system specifications to choose the Product/file description. The website will contain the latest version for your corresponding system. For Windows, we’ll be downloading the latest <strong>x64 Installer of Java SE Development Kit 18.</strong> After the download is complete, proceed to install the JDK by following the bootstrapped steps.<br>
<img src="https://media.geeksforgeeks.org/wp-content/uploads/20220622175210/Step1InstallingJDKforWindows.png" alt=""></p>
<h3 id="step-2-configure-environment-variables"><strong>Step 2: Configure Environment Variables</strong></h3>
<p>After the installation is complete, we have to configure environment variables to notify the system about the directory in which JDK files are located. Proceed to  <strong>C:\Program Files\Java\jdk-</strong>{YOUR_JDK_VERSION}<strong>\bin</strong>  (replace {-} with your JDK version)</p>
<p><img src="https://media.geeksforgeeks.org/wp-content/uploads/20220622115447/Step2LocatingJDKFile.png" alt=""></p>
<p>To set the Environment Variables, you need to search Environment Variables in the Task Bar and click on <strong>“Edit the system environment variables”</strong>.</p>
<p><img src="https://media.geeksforgeeks.org/wp-content/uploads/20220622115655/Step2ConfiguringEnvironmentVariables.png" alt=""></p>
<p>Under the  <strong>Advanced</strong>  section, Click on  <strong>“Environment Variables”</strong>.</p>
<p><img src="https://media.geeksforgeeks.org/wp-content/uploads/20220622115847/Step2SettingEnvironmentVariable.png" alt=""></p>
<p>Under <strong>System variables</strong>, select the <strong>“Path”</strong> variable and click on <strong>“Edit”</strong>. Click on <strong>“New”</strong> then paste the Path Address i.e. <strong>C:\Program Files\Java\jdk-</strong>{YOUR_JDK_VERSION}<strong>\bin</strong>. Click on <strong>“OK”</strong>.</p>
<p><img src="https://media.geeksforgeeks.org/wp-content/uploads/20220622120027/Step2SettingPathEnvironmentVariable.png" alt=""></p>
<p>Now, in the <strong>Environment Variables</strong> dialogue, under <strong>System variables</strong>, click on <strong>“New”</strong> and then under <strong>Variable name: JAVA_HOME</strong> and <strong>Variable value:</strong> paste address i.e. <strong>C:\Program Files\Java\jdk-</strong>{YOUR_JDK_VERSION}. Click on <strong>OK =&gt; OK =&gt; OK</strong>.</p>
<p><img src="https://media.geeksforgeeks.org/wp-content/uploads/20220622120141/Step2SettingJAVAHOMEEnvironmentVariable.png" alt=""></p>
<h3 id="step-3-check-the-java-version"><strong>Step 3: Check the Java Version</strong></h3>
<p>Open  <strong>Command Prompt</strong> and enter the following commands</p>
<pre><code>java -version
</code></pre>
<p><img src="https://media.geeksforgeeks.org/wp-content/uploads/20220622120248/Step3CheckingJDKVersion.png" alt=""></p>
<h2 id="install-jdk-on-linux">Install JDK On Linux</h2>
<h3 id="debian-basedububtu">Debian-based:(ububtu)</h3>
<p>To install the Java Development Kit (JDK) on a Linux system, you can follow these steps. I’ll provide instructions for installing OpenJDK, which is the open-source implementation of the Java Platform.</p>
<ol>
<li>
<p><strong>Update Package Repositories (Optional)</strong>: It’s a good practice to update your package repositories before installing new software. Run the following command:</p>
<p>bashCopy code</p>
<pre><code>sudo apt update 
</code></pre>
</li>
</ol>
<p><img src="https://i.imgur.com/8FcLpwG.png" alt="Imgur"></p>
<p>This command is for Debian-based distributions like Ubuntu. If you’re using a different distribution, use the appropriate package manager’s update command.</p>
<ol start="2">
<li>
<p><strong>Install OpenJDK</strong>: You can install OpenJDK using your distribution’s package manager. The package name might vary depending on the version of Java you want to install. Typically, OpenJDK 8, 11, and 16 are common versions.</p>
<p>For OpenJDK 11, run the following command:</p>
<p>bashCopy code</p>
<pre><code>sudo apt install openjdk-11-jdk 
</code></pre>
</li>
</ol>
<p><img src="https://i.imgur.com/sk4iTja.png" alt="Imgur"></p>
<ul>
<li>
<p>click on <code>y</code> to continue</p>
<p>For OpenJDK 8 or 16, replace <code>11</code> with <code>8</code> or <code>16</code> in the package name.</p>
</li>
</ul>
<ol start="3">
<li>
<p><strong>Verify Installation</strong>: Once the installation is complete, you can verify it by checking the installed Java version:</p>
<p>bashCopy code</p>
<pre><code>java -version 
</code></pre>
</li>
</ol>
<p><img src="https://i.imgur.com/omssgOE.png" alt="Imgur"></p>
<p>You should see output indicating the installed Java version.</p>
<ol start="4">
<li>
<p><strong>Configure Default Java Version (Optional)</strong>: If you have multiple Java versions installed, you can set the default version using the <code>update-alternatives</code> command:</p>
<p>bashCopy code</p>
<pre><code>sudo update-alternatives --config java 
</code></pre>
<p>This command will present you with a list of installed Java versions. Choose the one you want to set as default by entering the corresponding number.</p>
</li>
</ol>
<p>That’s it! You have successfully installed the OpenJDK Java Development Kit on your Linux system. Remember that package names and installation methods might vary slightly depending on your specific Linux distribution.</p>
<h3 id="centos">CentOS</h3>
<p>CentOS has a similar process to Fedora.</p>
<ol>
<li>
<p><strong>Update Package Repositories (Optional)</strong>:</p>
<p>bashCopy code</p>
<pre><code>sudo yum update 
</code></pre>
</li>
<li>
<p><strong>Install OpenJDK</strong>:</p>
<p>For OpenJDK 11:</p>
<p>bashCopy code</p>
<pre><code>sudo yum install java-1.8.0-openjdk 
</code></pre>
<p>For OpenJDK 8 or 16, replace <code>11</code> with <code>8</code> or <code>16</code> in the package name.</p>
</li>
<li>
<p><strong>Verify Installation</strong>:</p>
<p>bashCopy code</p>
<pre><code>java -version
</code></pre>
</li>
</ol>
<h2 id="install-jdk-on-macos">Install JDK on MacOS</h2>
<h3 id="step-1-download-and-install-oracle-java-development-kit-jdk"><strong>Step 1: Download and Install Oracle Java Development Kit (JDK)</strong></h3>
<p>The very first step is to download the  <strong>Oracle Java Development Kit (JDK)</strong>  from the Official Oracle Website. For that, Head over to the  <a href="https://www.oracle.com/java/technologies/downloads/#jdk18-mac">Official Website</a>.</p>
<p><img src="https://media.geeksforgeeks.org/wp-content/uploads/20220629181918/Step1DownloadOracleJavaDevelopmentKit.png" alt=""></p>
<p>You need to identify your system specifications to choose the Product/file description. The website will contain the latest version for your corresponding system. For Mac, we’ll be downloading the latest <strong>x64 DMG Installer of Java SE Development Kit 18.</strong> After the download is complete, proceed to install the JDK by following the bootstrapped steps.<br>
<img src="https://media.geeksforgeeks.org/wp-content/uploads/20220629181941/Step1InstallingOracleJavaDevelopmentKit.png" alt=""></p>
<h3 id="step-2-configure-environment-variables-1"><strong>Step 2: Configure environment variables</strong></h3>
<p>Now to configure, we have to open the terminal and pass the following commands. To find the Location of the JAVA_HOME, run this command</p>
<pre><code>/usr/libexec/java_home -v{YOUR_VERSION}
</code></pre>
<p><img src="https://media.geeksforgeeks.org/wp-content/uploads/20220629182010/Step2ConfiguringEnvironmentVariables.png" alt=""></p>
<p>We have to set this output as our JAVA_HOME Environment Variable. You can use any command or code editor to edit the file, here we are using VS Code</p>
<pre><code> code ~/. bash_profile
</code></pre>
<p><img src="https://media.geeksforgeeks.org/wp-content/uploads/20220629182040/Step2ConfiguringJAVAHOME.png" alt=""></p>
<p>At the very bottom, we have to export the path we obtained earlier i.e.</p>
<pre><code>export JAVA_HOME=/Library/Java/JavaVirtualMachines/jdk-{YOUR_VERSION}.jdk/Contents/Home
</code></pre>
<p><img src="https://media.geeksforgeeks.org/wp-content/uploads/20220629182214/Step2ConfiguredJAVAHOMEPath.png" alt=""></p>
<p>Now we have to refresh the environment file by using this command</p>
<pre><code>source ~/.bash_profile
</code></pre>
<p>And echo the JAVA_HOME variable</p>
<pre><code>echo $JAVA_HOME
</code></pre>
<p><img src="https://media.geeksforgeeks.org/wp-content/uploads/20220629182235/Step2RefreshedJAVAHOMEEnvironmentVariable.png" alt=""></p>
<h3 id="step-3-check-the-java-version-1"><strong>Step 3: Check the Java Version</strong></h3>
<p>In the  <strong>terminal</strong>, enter the following commands</p>
<pre><code>java -version
</code></pre>
<p><img src="https://media.geeksforgeeks.org/wp-content/uploads/20220629182335/Step3CheckingJavaVersion.png" alt=""></p>

