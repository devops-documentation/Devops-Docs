<!DOCTYPE html>
<html>

<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>maven commands</title>
  <link rel="stylesheet" href="https://stackedit.io/style.css" />
</head>

<body class="stackedit">
  <div class="stackedit__html"><h2 id="maven-commands">Maven commands</h2>
<p>Maven is a software project management and comprehension tool. It is used to build, package, deploy, and manage software projects. Maven is a popular tool for Java projects, but it can also be used for projects written in other languages.</p>
<p>Maven commands are used to perform tasks related to Maven projects. There are many different Maven commands, but some of the most common ones include:</p>
<p><img src="https://media.geeksforgeeks.org/wp-content/uploads/20201103220710/Capture-300x288.PNG" alt="Maven Lifecycle and Basic Maven Commands - GeeksforGeeks"></p>
<h2 id="mvn-clean">mvn clean:</h2>
<ul>
<li>This command cleans the project’s build directory.<br>
The mvn clean command is used to clean the project’s build directory. The build directory is where Maven stores the output of the build process, such as the compiled code, the packaged artifacts, and the test reports.</li>
</ul>
<p>The mvn clean command has the following syntax:</p>
<pre><code>mvn clean

</code></pre>
<p>This command will delete the following files and directories from the project’s build directory:</p>
<ul>
<li><strong>target:</strong>  This directory contains the output of the build process.</li>
<li><strong>pom.xml.lastUpdated:</strong>  This file is used to track the last time the project’s pom.xml file was updated.</li>
<li><strong>maven-status</strong>:** This directory contains status information about the project’s build.</li>
</ul>
<p>The mvn clean command can be used to clean the build directory before starting a new build. This can be helpful if you are making changes to the project’s source code or if you are having problems with the build.</p>
<p>Here are some of the options that can be used with the mvn clean command:</p>
<ul>
<li><strong>-f:</strong>  This option specifies the path to the pom.xml file.</li>
<li><strong>-D:</strong>  This option specifies a property that will be passed to Maven.</li>
<li><strong>-P:</strong>  This option specifies a profile that will be activated.</li>
<li><strong>-U:</strong>  This option tells Maven to update the project’s dependencies.</li>
</ul>
<p>The mvn clean command is a very useful command that can be used to keep your project’s build directory clean and organized.</p>
<p>Here are some examples of how to use the mvn clean command:</p>
<ul>
<li>To clean the build directory for the project in the current directory, you would use the following command:</li>
</ul>
<pre><code>mvn clean

</code></pre>
<ul>
<li>To clean the build directory for the project specified by the pom.xml file at /path/to/pom.xml, you would use the following command:</li>
</ul>
<pre><code>mvn clean -f /path/to/pom.xml

</code></pre>
<ul>
<li>To clean the build directory for the project and also update the project’s dependencies, you would use the following command:</li>
</ul>
<pre><code>mvn clean -U
</code></pre>
<h2 id="mvn-compile">mvn compile:</h2>
<p>This command compiles the project’s source code.</p>
<p>The mvn compile command is used to compile the project’s source code. The compiled code is then stored in the project’s build directory.</p>
<p>The mvn compile command has the following syntax:</p>
<pre><code>mvn compile

</code></pre>
<p>This command will compile all of the Java source code in the project. If there are any errors in the source code, Maven will report them.</p>
<p>The mvn compile command can be used to compile the project’s source code before running the tests or deploying the project.</p>
<p>Here are some of the options that can be used with the mvn compile command:</p>
<ul>
<li><strong>-f:</strong>  This option specifies the path to the pom.xml file.</li>
<li><strong>-D:</strong>  This option specifies a property that will be passed to Maven.</li>
<li><strong>-P:</strong>  This option specifies a profile that will be activated.</li>
<li><strong>-U:</strong>  This option tells Maven to update the project’s dependencies.</li>
<li><strong>-Dmaven.compiler.source:</strong>  This option specifies the source language level for the compilation.</li>
<li><strong>-Dmaven.compiler.target:</strong>  This option specifies the target language level for the compilation.</li>
</ul>
<p>The mvn compile command is a very useful command that can be used to compile your project’s source code.</p>
<p>Here are some examples of how to use the mvn compile command:</p>
<ul>
<li>To compile the project in the current directory, you would use the following command:</li>
</ul>
<pre><code>mvn compile

</code></pre>
<ul>
<li>To compile the project specified by the pom.xml file at /path/to/pom.xml, you would use the following command:</li>
</ul>
<pre><code>mvn compile -f /path/to/pom.xml

</code></pre>
<ul>
<li>To compile the project and also update the project’s dependencies, you would use the following command:</li>
</ul>
<pre><code>mvn compile -U

</code></pre>
<ul>
<li>To compile the project and set the source language level to Java 11, you would use the following command:</li>
</ul>
<pre><code>mvn compile -Dmaven.compiler.source=11
</code></pre>
<h2 id="mvn-package">mvn package</h2>
<p>This command packages the project’s artifacts.<br>
The mvn package command is used to package the project’s artifacts. Artifacts are the files that are produced by the build process, such as JAR files, WAR files, and EAR files.</p>
<p>The mvn package command has the following syntax:</p>
<pre><code>mvn package

</code></pre>
<p>This command will package the project’s artifacts and store them in the project’s build directory.</p>
<p>The mvn package command can be used to package the project’s artifacts before deploying the project or distributing the project.</p>
<p>Here are some of the options that can be used with the mvn package command:</p>
<ul>
<li><strong>-f:</strong>  This option specifies the path to the pom.xml file.</li>
<li><strong>-D:</strong>  This option specifies a property that will be passed to Maven.</li>
<li><strong>-P:</strong>  This option specifies a profile that will be activated.</li>
<li><strong>-U:</strong>  This option tells Maven to update the project’s dependencies.</li>
<li><strong>-Dmaven.artifact.version:</strong>  This option specifies the version of the artifact that will be packaged.</li>
<li><strong>-Dmaven.packaging:</strong>  This option specifies the packaging type of the artifact that will be packaged.</li>
</ul>
<p>The mvn package command is a very useful command that can be used to package your project’s artifacts.</p>
<p>Here are some examples of how to use the mvn package command:</p>
<ul>
<li>To package the project in the current directory, you would use the following command:</li>
</ul>
<pre><code>mvn package

</code></pre>
<ul>
<li>To package the project specified by the pom.xml file at /path/to/pom.xml, you would use the following command:</li>
</ul>
<pre><code>mvn package -f /path/to/pom.xml

</code></pre>
<ul>
<li>To package the project and also update the project’s dependencies, you would use the following command:</li>
</ul>
<pre><code>mvn package -U

</code></pre>
<ul>
<li>To package the project and set the artifact version to 1.0.0, you would use the following command:</li>
</ul>
<pre><code>mvn package -Dmaven.artifact.version=1.0.0

</code></pre>
<ul>
<li>To package the project and set the packaging type to JAR, you would use the following command:</li>
</ul>
<pre><code>mvn package -Dmaven.packaging=jar
</code></pre>
<h2 id="mvn-install">mvn install</h2>
<p>This command installs the project’s artifacts in the local Maven repository.<br>
The mvn install command is used to install the project’s artifacts in the local Maven repository. The local Maven repository is a directory where Maven stores the artifacts that it has downloaded.</p>
<p>The mvn install command has the following syntax:</p>
<pre><code>mvn install

</code></pre>
<p>This command will compile the project’s source code, package the project’s artifacts, and install the project’s artifacts in the local Maven repository.</p>
<p>The mvn install command can be used to install the project’s artifacts so that they can be used by other projects.</p>
<p>Here are some of the options that can be used with the mvn install command:</p>
<ul>
<li><strong>-f:</strong>  This option specifies the path to the pom.xml file.</li>
<li><strong>-D:</strong>  This option specifies a property that will be passed to Maven.</li>
<li><strong>-P:</strong>  This option specifies a profile that will be activated.</li>
<li><strong>-U:</strong>  This option tells Maven to update the project’s dependencies.</li>
<li><strong>-Dmaven.artifact.version:</strong>  This option specifies the version of the artifact that will be installed.</li>
<li><strong>-Dmaven.packaging:</strong>  This option specifies the packaging type of the artifact that will be installed.</li>
</ul>
<p>The mvn install command is a very useful command that can be used to install your project’s artifacts in the local Maven repository.</p>
<p>Here are some examples of how to use the mvn install command:</p>
<ul>
<li>To install the project in the current directory, you would use the following command:</li>
</ul>
<pre><code>mvn install

</code></pre>
<ul>
<li>To install the project specified by the pom.xml file at /path/to/pom.xml, you would use the following command:</li>
</ul>
<pre><code>mvn install -f /path/to/pom.xml

</code></pre>
<ul>
<li>To install the project and also update the project’s dependencies, you would use the following command:</li>
</ul>
<pre><code>mvn install -U

</code></pre>
<ul>
<li>To install the project and set the artifact version to 1.0.0, you would use the following command:</li>
</ul>
<pre><code>mvn install -Dmaven.artifact.version=1.0.0

</code></pre>
<ul>
<li>To install the project and set the packaging type to JAR, you would use the following command:</li>
</ul>
<pre><code>mvn install -Dmaven.packaging=jar
</code></pre>
<h2 id="mvn-deploy">mvn deploy:</h2>
<ul>
<li>This command deploys the project’s artifacts to a remote Maven repository.<br>
The mvn deploy command is used to deploy the project’s artifacts to a remote Maven repository. A remote Maven repository is a server where Maven artifacts can be stored and shared.</li>
</ul>
<p>The mvn deploy command has the following syntax:</p>
<pre><code>mvn deploy

</code></pre>
<p>This command will compile the project’s source code, package the project’s artifacts, install the project’s artifacts in the local Maven repository, and deploy the project’s artifacts to the remote Maven repository.</p>
<p>The mvn deploy command can be used to deploy the project’s artifacts so that they can be used by other projects.</p>
<p>Here are some of the options that can be used with the mvn deploy command:</p>
<ul>
<li><strong>-f:</strong>  This option specifies the path to the pom.xml file.</li>
<li><strong>-D:</strong>  This option specifies a property that will be passed to Maven.</li>
<li><strong>-P:</strong>  This option specifies a profile that will be activated.</li>
<li><strong>-U:</strong>  This option tells Maven to update the project’s dependencies.</li>
<li><strong>-Dmaven.artifact.version:</strong>  This option specifies the version of the artifact that will be deployed.</li>
<li><strong>-Dmaven.packaging:</strong>  This option specifies the packaging type of the artifact that will be deployed.</li>
<li><strong>-DremoteRepositoryUrl:</strong>  This option specifies the URL of the remote Maven repository.</li>
<li><strong>-DremoteRepositoryId:</strong>  This option specifies the ID of the remote Maven repository.</li>
</ul>
<p>The mvn deploy command is a very useful command that can be used to deploy your project’s artifacts to a remote Maven repository.</p>
<p>Here are some examples of how to use the mvn deploy command:</p>
<ul>
<li>To deploy the project in the current directory to the remote Maven repository at <a href="https://repo.maven.apache.org/maven2">https://repo.maven.apache.org/maven2</a>, you would use the following command:</li>
</ul>
<pre><code>mvn deploy -DremoteRepositoryUrl=https://repo.maven.apache.org/maven2

</code></pre>
<ul>
<li>To deploy the project specified by the pom.xml file at /path/to/pom.xml to the remote Maven repository at <a href="https://repo.maven.apache.org/maven2">https://repo.maven.apache.org/maven2</a>, you would use the following command:</li>
</ul>
<pre><code>mvn deploy -f /path/to/pom.xml -DremoteRepositoryUrl=https://repo.maven.apache.org/maven2

</code></pre>
<ul>
<li>To deploy the project and also update the project’s dependencies, you would use the following command:</li>
</ul>
<pre><code>mvn deploy -U

</code></pre>
<ul>
<li>To deploy the project and set the artifact version to 1.0.0, you would use the following command:</li>
</ul>
<pre><code>mvn deploy -Dmaven.artifact.version=1.0.0

</code></pre>
<ul>
<li>To deploy the project and set the packaging type to JAR, you would use the following command:</li>
</ul>
<pre><code>mvn deploy -Dmaven.packaging=jar
</code></pre>
<h2 id="mvn-test">mvn test:</h2>
<p>This command runs the project’s unit tests.<br>
The mvn test command is used to run the project’s unit tests. Unit tests are tests that test individual units of code, such as classes or methods.</p>
<p>The mvn test command has the following syntax:</p>
<pre><code>mvn test

</code></pre>
<p>This command will run all of the unit tests in the project. If there are any failures in the unit tests, Maven will report them.</p>
<p>The mvn test command can be used to run the project’s unit tests before deploying the project or releasing the project.</p>
<p>Here are some of the options that can be used with the mvn test command:</p>
<ul>
<li><strong>-f:</strong>  This option specifies the path to the pom.xml file.</li>
<li><strong>-D:</strong>  This option specifies a property that will be passed to Maven.</li>
<li><strong>-P:</strong>  This option specifies a profile that will be activated.</li>
<li><strong>-Dtest:</strong>  This option specifies a specific test class or method to run.</li>
<li><strong>-Dtest.exclude:</strong>  This option specifies a specific test class or method to exclude from running.</li>
<li><strong>-Dtest.filter:</strong>  This option specifies a regular expression that can be used to filter the tests that are run.</li>
</ul>
<p>The mvn test command is a very useful command that can be used to run your project’s unit tests.</p>
<p>Here are some examples of how to use the mvn test command:</p>
<ul>
<li>To run all of the unit tests in the project in the current directory, you would use the following command:</li>
</ul>
<pre><code>mvn test

</code></pre>
<ul>
<li>To run all of the unit tests in the project specified by the pom.xml file at /path/to/pom.xml, you would use the following command:</li>
</ul>
<pre><code>mvn test -f /path/to/pom.xml

</code></pre>
<ul>
<li>To run a specific test class, you would use the following command:</li>
</ul>
<pre><code>mvn test -Dtest=MyTestClass

</code></pre>
<ul>
<li>To run a specific test method, you would use the following command:</li>
</ul>
<pre><code>mvn test -Dtest=MyTestClass#myTestMethod

</code></pre>
<ul>
<li>To exclude a specific test class from running, you would use the following command:</li>
</ul>
<pre><code>mvn test -Dtest.exclude=MyTestClass

</code></pre>
<ul>
<li>To exclude a specific test method from running, you would use the following command:</li>
</ul>
<pre><code>mvn test -Dtest.exclude=MyTestClass#myTestMethod

</code></pre>
<ul>
<li>To filter the tests that are run by a regular expression, you would use the following command:</li>
</ul>
<pre><code>mvn test -Dtest.filter=.*MyTestClass.*
</code></pre>
<h2 id="mvn-site">mvn site:</h2>
<p>This command generates the project’s site documentation.<br>
The mvn site command is used to generate a documentation site for the project. The site will contain information about the project’s dependencies, plugins, reports, and other artifacts.</p>
<p>The mvn site command has the following syntax:</p>
<pre><code>mvn site

</code></pre>
<p>This command will generate the site in the project’s target directory.</p>
<p>The mvn site command can be used to generate a documentation site for your project. The site can be used to help users understand the project and its dependencies.</p>
<p>Here are some of the options that can be used with the mvn site command:</p>
<ul>
<li><strong>-f:</strong>  This option specifies the path to the pom.xml file.</li>
<li><strong>-D:</strong>  This option specifies a property that will be passed to Maven.</li>
<li><strong>-P:</strong>  This option specifies a profile that will be activated.</li>
<li><strong>-Dmaven.site.skip:</strong>  This option tells Maven to skip the site generation.</li>
<li><strong>-Dmaven.site.deploy:</strong>  This option tells Maven to deploy the site to a remote server.</li>
</ul>
<p>The mvn site command is a very useful command that can be used to generate documentation for your project.</p>
<p>Here are some examples of how to use the mvn site command:</p>
<ul>
<li>To generate the site for the project in the current directory, you would use the following command:</li>
</ul>
<pre><code>mvn site

</code></pre>
<ul>
<li>To generate the site for the project specified by the pom.xml file at /path/to/pom.xml, you would use the following command:</li>
</ul>
<pre><code>mvn site -f /path/to/pom.xml

</code></pre>
<ul>
<li>To skip the site generation, you would use the following command:</li>
</ul>
<pre><code>mvn site -Dmaven.site.skip=true

</code></pre>
<ul>
<li>To deploy the site to a remote server, you would use the following command:</li>
</ul>
<pre><code>mvn site -Dmaven.site.deploy=true
</code></pre>
<hr>
<p>The Maven command line is a powerful tool that can be used to automate many of the tasks involved in software development. It is a good idea to learn the basics of the Maven command line if you are planning to use Maven.</p>
<p>Here are some other common Maven commands:</p>
<ul>
<li><strong>mvn help:</strong>  This command displays help information for a specific Maven command.</li>
<li><strong>mvn help:all:</strong>  This command displays help information for all Maven commands.</li>
<li><strong>mvn -version:</strong>  This command displays the version of Maven that is installed.</li>
<li><strong>mvn -v:</strong>  This command is a shortcut for the mvn -version command.</li>
</ul>
</div>
</body>

</html>
