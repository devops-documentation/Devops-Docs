<!DOCTYPE html>
<html>

<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>maven installation</title>
  <link rel="stylesheet" href="https://stackedit.io/style.css" />
</head>

<body class="stackedit">
  <div class="stackedit__html"><h1 id="maven">Maven</h1>
<h2 id="what-is-maven">What is Maven</h2>
<p>Maven is a powerful  <em>project management tool</em>  that is based on POM (project object model). It is used for projects build, dependency and documentation.</p>
<p>It simplifies the build process like ANT. But it is too much advanced than ANT.</p>
<p>Current version of Maven is 3.</p>
<h2 id="what-it-does">What it does?</h2>
<p>Maven simplifies the above mentioned problems. It does mainly following tasks.</p>
<ol>
<li>It makes a project easy to build</li>
<li>It provides uniform build process (maven project can be shared by all the maven projects)</li>
<li>It provides project information (log document, cross referenced sources, mailing list, dependency list, unit test reports etc.)</li>
<li>It is easy to migrate for new features of Maven</li>
</ol>
<p>Apache Maven helps to manage</p>
<ul>
<li>Builds</li>
<li>Documentation</li>
<li>Reporing</li>
<li>SCMs</li>
<li>Releases</li>
<li>Distribution</li>
</ul>
<hr>
<h2 id="what-is-build-tool">What is Build Tool</h2>
<p>A build tool takes care of everything for building a process. It does following:</p>
<ul>
<li>Generates source code (if auto-generated code is used)</li>
<li>Generates documentation from source code</li>
<li>Compiles source code</li>
<li>Packages compiled code into JAR of ZIP file</li>
<li>Installs the packaged code in local repository, server repository, or central repository</li>
</ul>
<h2 id="difference-between-ant-and-maven">Difference between Ant and Maven</h2>
<p><strong>Ant</strong>  and  <strong>Maven</strong>  both are build tools provided by Apache. The main purpose of these technologies is to ease the build process of a project.</p>
<p>There are many differences between ant and maven that are given in the <a href="https://www.javatpoint.com/difference-between-ant-and-maven">link</a></p>
<h2 id="how-to-install-maven-on-windows">How to install Maven on windows</h2>
<p>You can download and install maven on windows, linux and MAC OS platforms. Here, we are going to learn how to install maven on windows OS.</p>
<p>To install maven on windows, you need to perform following steps:</p>
<ol>
<li>Download maven and extract it</li>
<li>Add JAVA_HOME and MAVEN_HOME in environment variable</li>
<li>Add maven path in environment variable</li>
<li>Verify Maven</li>
</ol>
<h2 id="download-maven">1) Download Maven</h2>
<p>To install maven on windows, you need to download apache maven first.</p>
<p>Download Maven latest Maven software from  <a href="https://dlcdn.apache.org/maven/maven-3/3.9.4/binaries/apache-maven-3.9.4-bin.zip">Download latest version of Maven</a></p>
<p>For example:  <strong>apache-maven-3.9.4-bin.zip</strong></p>
<p>Extract it. Now it will look like this:</p>
<p><img src="https://i.imgur.com/PHghd6b.png" alt="Imgur"></p>
<p><img src="https://i.imgur.com/BFYpqvO.png" alt="Imgur"></p>
<p><img src="https://i.imgur.com/ZVoNDsQ.png" alt="Imgur"></p>
<h2 id="add-maven_home-in-environment-variable">2. Add MAVEN_HOME in environment variable</h2>
<p>-Go to the <strong>bin</strong><br>
<img src="https://i.imgur.com/VngECEJ.png" alt="Imgur"></p>
<p>-Copy the <strong>path</strong><br>
<img src="https://i.imgur.com/gsvCU1W.png" alt="Imgur"></p>
<p>-Type <strong>Environment variable</strong> in the Toolbar<br>
<img src="https://i.imgur.com/iRCxv1Q.png" alt="Imgur"></p>
<p>-Click <strong>Environment variable</strong><br>
<img src="https://i.imgur.com/lwJAwUJ.png" alt="Imgur"></p>
<p>-Select <strong>path</strong><br>
<img src="https://i.imgur.com/M6vBxDO.png" alt="Imgur"></p>
<p>-And click <strong>Edit</strong> in the System Variable<br>
<img src="https://i.imgur.com/2Js8MJC.png" alt="Imgur"></p>
<p>-And select <strong>New</strong><br>
<img src="https://i.imgur.com/bBmF4Pj.png" alt="Imgur"></p>
<p>-paste it the copied bin path<br>
<img src="https://i.imgur.com/CLlc1JO.png" alt="Imgur"></p>
<p>-open <strong>cmd</strong> and verify the <strong>maven</strong></p>
<blockquote>
<p><code>mvn --version</code></p>
</blockquote>
<p><img src="https://i.imgur.com/xf5BXuh.png" alt="Imgur"></p>
<h2 id="install-maven-on-mac"><a href="https://www.digitalocean.com/community/tutorials/install-maven-mac-os#install-maven-on-mac">Install Maven on Mac</a><a href="https://www.digitalocean.com/community/tutorials/install-maven-mac-os#install-maven-on-mac"></a></h2>
<p>Maven is the most widely used build and project dependency management tool for Java-based applications. We can install Maven on Mac OS using a package manager such as HomeBrew or through XCode Command Line Tools. But, in this tutorial, we will learn how to install Maven on Mac OS without using any other software. Maven requires Java to execute. So we will have to first install Java and then maven into our Mac OS.</p>
<h3 id="installing-java-on-mac"><a href="https://www.digitalocean.com/community/tutorials/install-maven-mac-os#1-installing-java-on-mac">1. Installing Java on Mac</a><a href="https://www.digitalocean.com/community/tutorials/install-maven-mac-os#1-installing-java-on-mac"></a></h3>
<p>We will install OpenJDK in our Mac OS. It’s free and you don’t have to worry about licensing that comes with Oracle JDK build.</p>
<h4 id="downloading-java-for-mac-os">1.1) Downloading Java for Mac OS</h4>
<p>Go to the latest JDK GA release page and download the tar file for Mac OS. Java 13 GA Release URL:  <a href="https://jdk.java.net/13/">https://jdk.java.net/13/</a>  Then extract it to the directory of your choice. I prefer to keep my JDK setup at “/Library/Java/JavaVirtualMachines/” directory.</p>
<pre><code>$ tar -xvf openjdk-13.0.1_osx-x64_bin.tar.gz
$ sudo mv jdk-13.0.1.jdk /Library/Java/JavaVirtualMachines/

</code></pre>
<p><strong>Recommended Reading</strong>:  <a href="https://www.digitalocean.com/community/tutorials/linux-tar-command">Linux tar command to compress and extract files</a></p>
<h4 id="setting-environment-variables---java_home-and-path">1.2) Setting Environment Variables - JAVA_HOME and Path</h4>
<p>Open .bash_profile and add the following entries at the end of it.</p>
<pre><code>JAVA_HOME="/Library/Java/JavaVirtualMachines/jdk-13.0.1.jdk/Contents/Home"
PATH="${JAVA_HOME}/bin:${PATH}"
export PATH

</code></pre>
<p>You can relaunch the Terminal to apply these profile changes. Or you can also run  <code>source .bash_profile</code>  command to apply these environment variable changes.  <strong>Recommended Reading</strong>:  <a href="https://www.digitalocean.com/community/tutorials/linux-environment-variables">Linux Environment Variables</a></p>
<h4 id="verifying-the-jdk-installation">1.3) Verifying the JDK installation</h4>
<p>Open the Terminal and run  <code>java -version</code>  command. It should show the following output.</p>
<pre><code>$ java -version
openjdk version "13.0.1" 2019-10-15
OpenJDK Runtime Environment (build 13.0.1+9)
OpenJDK 64-Bit Server VM (build 13.0.1+9, mixed mode, sharing)
$

</code></pre>
<p>However, you might get an alert message with the following warning.</p>
<pre><code>“jdk-13.0.1.jdk” cannot be opened because the developer cannot be verified.
macOS cannot verify that this app is free from malware.

</code></pre>
<p><img src="https://journaldev.nyc3.digitaloceanspaces.com/2013/11/jdk13-macos-verify-error.png" alt="Jdk13 Macos Verify Error"></p>
<p>Jdk13 Macos Verify Error</p>
<p>You will have to allow the app to execute from the “Security and Privacy” settings.<img src="https://journaldev.nyc3.digitaloceanspaces.com/2013/11/allow-apps-mac-security-and-privacy.png" alt="Allow Apps Mac Security And Privacy">After that, the java command will work fine and the alert message will not be shown.</p>
<h3 id="install-maven-on-mac-os"><a href="https://www.digitalocean.com/community/tutorials/install-maven-mac-os#2-install-maven-on-mac-os">2. Install Maven on Mac OS</a><a href="https://www.digitalocean.com/community/tutorials/install-maven-mac-os#2-install-maven-on-mac-os"></a></h3>
<p>Now that we have successfully installed JDK, we are ready to download and install Maven in Mac OS.</p>
<h4 id="download-maven-for-mac-os">2.1) Download Maven for Mac OS</h4>
<p>Go to the Maven Download site:  <a href="https://maven.apache.org/download.cgi">https://maven.apache.org/download.cgi</a>  Download the “Binary tar.gz archive” file as shown in the below image.</p>
<p><img src="https://journaldev.nyc3.digitaloceanspaces.com/2013/11/maven-binary-tar-archive.png" alt="Maven Binary Tar Archive"></p>
<p>Maven Binary Tar Archive</p>
<p>After downloading, extract it using the below command.</p>
<pre><code>$ tar -xvf apache-maven-3.6.3-bin.tar.gz

</code></pre>
<p>The binaries will be extracted in the “apache-maven-3.6.3” directory. You can keep them anywhere, I have kept it in the Downloads directory for the sake of easy access.</p>
<h4 id="setting-maven-environment-variables---m2_home-and-path">2.2) Setting Maven Environment Variables - M2_HOME and Path</h4>
<p>The next step is to set up the environment variables - M2_HOME and Path. We have to add the Maven bin directory to the Path variable. Open .bash_profile in your favorite text editor and add below lines to the end of it.</p>
<pre><code>export M2_HOME="/Users/pankaj/Downloads/apache-maven-3.6.3"
PATH="${M2_HOME}/bin:${PATH}"
export PATH

</code></pre>
<p>You can relaunch Terminal to load these profile settings or use  <code>source .bash_profile</code>  command to apply it.</p>
<h4 id="verifying-the-maven-installation">2.3) Verifying the Maven Installation</h4>
<p>Finally, run the  <code>mvn -version</code>  command to check if Maven is installed successfully.</p>
<pre><code>$ mvn -version     
OpenJDK 64-Bit Server VM warning: Ignoring option MaxPermSize; support was removed in 8.0
Apache Maven 3.6.3 (cecedd343002696d0abb50b32b541b8a6ba2883f)
Maven home: /Users/pankaj/Downloads/apache-maven-3.6.3
Java version: 13.0.1, vendor: Oracle Corporation, runtime: /Library/Java/JavaVirtualMachines/jdk-13.0.1.jdk/Contents/Home
Default locale: en_IN, platform encoding: UTF-8
OS name: "mac os x", version: "10.15.1", arch: "x86_64", family: "mac"
$

</code></pre>
<p>The output shows maven home location, the JDK it’s using and also the Mac OS version details. Maven is successfully installed in your Mac OS. You are ready to create a maven based Java projects.</p>
<h3 id="installation-maven-on-ubuntu-">Installation Maven on Ubuntu :</h3>
<p>The installation process of Maven is short composite on three basic steps. Before starting these three steps, we can avail every benefiting aspect of Maven for managing the Java projects on our Ubuntu system.</p>
<p><strong>Step 1: Package up-gradation</strong></p>
<p><strong>Step 2: Apache Maven installation</strong></p>
<p><strong>Step 3: Verification</strong></p>
<h3 id="prerequisites">Prerequisites</h3>
<p>It’s mandatory to have Java installed in our server with the Java encompassing JRE and JDK development kit to execute the Maven commands. If we do not have Java installed in our system, then we can run the following command in the terminal window:</p>
<ol>
<li>$ sudo apt install default-jdk</li>
</ol>
<p><img src="https://static.javatpoint.com/linux/images/install-maven-in-ubuntu2.png" alt="Install Maven in Ubuntu"></p>
<p>Also, we can verify the Java system installation and its kit with the help of the following command:</p>
<ol>
<li>$ java -version</li>
</ol>
<p><img src="https://static.javatpoint.com/linux/images/install-maven-in-ubuntu3.png" alt="Install Maven in Ubuntu"></p>
<h3 id="step-1-package-up-gradation">Step 1: Package up-gradation</h3>
<p>First of all, we need to update our existing packages with the help of the sudo apt command. It’s fundamental for updating our existing packages before going to install any server or tool on the Ubuntu system. The command is mentioned below:</p>
<ol>
<li>$ sudo apt update</li>
</ol>
<p><img src="https://static.javatpoint.com/linux/images/install-maven-in-ubuntu4.png" alt="Install Maven in Ubuntu"></p>
<p>Also, we can execute this command before going to install the Java kit. The system packages would be updated with the  <strong><em>Java kit</em></strong>  installation using this way.</p>
<h3 id="step-2-apache-maven-installation">Step 2: Apache Maven installation</h3>
<p>Primarily, there are two methods to get Maven in our system. Either, we can download it using the apt command or using its web source directly from the  <strong><em>wget</em></strong>  command.</p>
<p>We need to run the following command in the terminal window to install Maven:</p>
<ol>
<li>$ sudo apt install maven</li>
</ol>
<p><img src="https://static.javatpoint.com/linux/images/install-maven-in-ubuntu5.png" alt="Install Maven in Ubuntu"></p>
<h3 id="step-3-verification">Step 3: Verification</h3>
<p>Also, we can verify Maven installation with the help of the following command in the terminal window:</p>
<ol>
<li>$ mvn --version</li>
</ol>
<p><img src="https://static.javatpoint.com/linux/images/install-maven-in-ubuntu6.png" alt="Install Maven in Ubuntu"></p>
<h3 id="installation-maven-on-centos">Installation Maven on CentOS</h3>
<p>Maven 3.3+ requires JDK 1.7 or above to be installed. We’ll  <a href="https://linuxize.com/post/install-java-on-centos-7/">install OpenJDK</a>  , which is the default Java development and runtime in CentOS 7.</p>
<p>Install the OpenJDK package by typing:</p>
<pre><code>sudo yum install java-1.8.0-openjdk
</code></pre>
<p>Verify that Java was successfully installed by running the following command:</p>
<pre><code>java -version
</code></pre>
<p>The output should look something like this:</p>
<pre class=" language-output"><code class="prism  language-output">openjdk version "1.8.0_191"
OpenJDK Runtime Environment (build 1.8.0_191-b12)
OpenJDK 64-Bit Server VM (build 25.191-b12, mixed mode)

</code></pre>
<p><a href="https://humix.com/redirect?url=https%3A%2F%2Fbestxpot.com%2Fhumix%2Fvideo%2FquVZJHPAA7f">How to Install Apache Maven on CentOS 8</a></p>
<h3 id="download-apache-maven">2. Download Apache Maven</h3>
<p>At the time of writing this article, the latest version of Apache Maven is  <code>3.6.0</code>. Before continuing with the next step, you should check the  <a href="https://maven.apache.org/download.cgi">Maven download page</a>  to see if a newer version is available.</p>
<p>Start by downloading the Apache Maven in the  <code>/tmp</code>  directory using the following  <a href="https://linuxize.com/post/wget-command-examples/"><code>wget</code></a>  command:</p>
<pre><code>wget https://www-us.apache.org/dist/maven/maven-3/3.6.0/binaries/apache-maven-3.6.0-bin.tar.gz -P /tmp
</code></pre>
<p>When the download is completed,  <a href="https://linuxize.com/post/how-to-create-and-extract-archives-using-the-tar-command-in-linux/">extract the archive</a>  in the  <code>/opt</code>  directory:</p>
<pre><code>sudo tar xf /tmp/apache-maven-3.6.0-bin.tar.gz -C /opt
</code></pre>
<p>To have more control over Maven versions and updates, we will  <a href="https://linuxize.com/post/how-to-create-symbolic-links-in-linux-using-the-ln-command/">create a symbolic link</a>  <code>maven</code>  that will point to the Maven installation directory:</p>
<pre><code>sudo ln -s /opt/apache-maven-3.6.0 /opt/maven
</code></pre>
<p>To upgrade your Maven installation, simply unpack the newer version and change the symlink to point to it.</p>
<h3 id="setup-environment-variables">3. Setup environment variables</h3>
<p>Next, we’ll need to set up the environment variables. Open your text editor and create a new file named  <code>maven.sh</code>  inside of the  <code>/etc/profile.d/</code>  directory.</p>
<pre><code>sudo nano /etc/profile.d/maven.sh
</code></pre>
<p>Paste the following lines:</p>
<pre class=" language-sh"><code class="prism  language-sh">export JAVA_HOME=/usr/lib/jvm/jre-openjdk
export M2_HOME=/opt/maven
export MAVEN_HOME=/opt/maven
export PATH=${M2_HOME}/bin:${PATH}

</code></pre>
<p>Copy</p>
<p>Save and close the file. This script will be sourced at shell startup.</p>
<p>Make the script executable by running the following  <a href="https://linuxize.com/post/chmod-command-in-linux/"><code>chmod</code></a>  command:</p>
<pre><code>sudo chmod +x /etc/profile.d/maven.sh
</code></pre>
<p>Load the environment variables using the  <a href="https://linuxize.com/post/bash-source-command/"><code>source</code></a>  command:</p>
<pre><code>source /etc/profile.d/maven.sh
</code></pre>
<h3 id="verify-the-installation">4. Verify the installation</h3>
<p>To verify that Maven is installed, use the  <code>mvn -version</code>  command which will print the Maven version:</p>
<pre><code>mvn -version
</code></pre>
<p>You should see something like the following:</p>
<pre class=" language-output"><code class="prism  language-output">Apache Maven 3.6.0 (97c98ec64a1fdfee7767ce5ffb20918da4f719f3; 2018-10-24T18:41:47Z)
Maven home: /opt/maven
Java version: 1.8.0_191, vendor: Oracle Corporation, runtime: /usr/lib/jvm/java-1.8.0-openjdk-1.8.0.191.b12-0.el7_5.x86_64/jre
Default locale: en_US, platform encoding: UTF-8
OS name: "linux", version: "3.10.0-862.3.2.el7.x86_64", arch: "amd64", family: "unix"

</code></pre>
<p>That’s it. The latest version of Maven is now installed on your CentOS system.</p>
</div>
</body>

</html>
