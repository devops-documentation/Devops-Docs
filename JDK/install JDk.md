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

