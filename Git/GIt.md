<h2 id="welcome-to-git">Welcome to Git</h2>
<p>Git is a version-control system for tracking changes in computer files and coordinating work on those files among multiple people. It is primarily used for source-code management in software development, but it can be used to keep track of changes in any set of files</p>
<h1 id="install-git-on-windows">Install Git on Windows</h1>
<ol>
<li>Navigate to the latest  <a href="https://gitforwindows.org/">Git for Windows installer</a>  and download the latest version.</li>
<li>Once the installer has started, follow the instructions as provided in the  <strong>Git Setup</strong>  wizard screen until the installation is complete.</li>
<li>Open the windows command prompt (or  <strong>Git Bash</strong>  if you selected not to use the standard Git Windows Command Prompt during the Git installation).</li>
<li>Type  <code>git version</code>  to verify Git was installed.</li>
</ol>
<p>Note:  <a href="https://git-scm.com/download/win"><code>git-scm</code></a>  is a popular and recommended resource for downloading Git for Windows. The advantage of downloading Git from  <code>git-scm</code>  is that your download automatically starts with the latest version of Git included with the recommended command prompt,  <code>Git Bash</code>  . The download source is the same  <a href="https://gitforwindows.org/">Git for Windows installer</a>  as referenced in the steps above.</p>
<pre><code>git version
</code></pre>
<h2 id="install-git-on-mac">Install Git on mac</h2>
<p>Most versions of MacOS will already have  <code>Git</code>  installed, and you can activate it through the terminal with  <code>git version</code>. However, if you don’t have Git installed for whatever reason, you can install the latest version of Git using one of several popular methods as listed below:</p>
<h4 id="install-git-from-an-installer"><a href="https://github.com/git-guides/install-git#install-git-from-an-installer"></a>Install Git From an Installer</h4>
<ol>
<li>Navigate to the latest  <a href="https://sourceforge.net/projects/git-osx-installer/files/git-2.23.0-intel-universal-mavericks.dmg/download?use_mirror=autoselect">macOS Git Installer</a>  and download the latest version.</li>
<li>Once the installer has started, follow the instructions as provided until the installation is complete.</li>
<li>Open the command prompt “terminal” and type  <code>git version</code>  to verify Git was installed.</li>
</ol>
<p>Note:  <a href="https://git-scm.com/download/mac"><code>git-scm</code></a>  is a popular and recommended resource for downloading Git on a Mac. The advantage of downloading Git from  <code>git-scm</code>  is that your download automatically starts with the latest version of Git. The download source is the same  <a href="https://sourceforge.net/projects/git-osx-installer/files/git-2.23.0-intel-universal-mavericks.dmg/download?use_mirror=autoselect">macOS Git Installer</a>  as referenced in the steps above.</p>
<h4 id="install-git-from-homebrew"><a href="https://github.com/git-guides/install-git#install-git-from-homebrew"></a>Install Git from Homebrew</h4>
<p><a href="https://brew.sh/">Homebrew</a>  is a popular package manager for macOS. If you already have Homwbrew installed, you can follow the below steps to install Git:</p>
<p>Open up a terminal window and install Git using the following command:</p>
<pre><code>brew install git
</code></pre>
<p>Once the command output has completed, you can verify the installation by typing:  <code>git version</code>.</p>
<pre><code>git version
</code></pre>
<h2 id="install-git-on-linux">Install Git on Linux</h2>
<p>You can install  <code>Git</code>  on Linux through the package management tool that comes with your distribution.</p>
<h4 id="debianubuntu"><a href="https://github.com/git-guides/install-git#debianubuntu"></a>Debian/Ubuntu</h4>
<p>Git packages are available using <code>apt</code>. It’s a good idea to make sure you’re running the latest version. To do so, Navigate to your command prompt shell and run the following command to make sure everything is up-to-date:</p>
<pre><code>sudo apt-get update
</code></pre>
<p>To install Git, run the following command:</p>
<pre><code>sudo apt-get install git-all
</code></pre>
<p>Once the command output has completed, you can verify the installation by typing:</p>
<pre><code>enter code here
</code></pre>
<h4 id="fedora"><a href="https://github.com/git-guides/install-git#fedora"></a>Fedora</h4>
<p>Git packages are available using  <code>dnf</code>.To install Git, navigate to your command prompt shell and run the following command:</p>
<pre><code>sudo dnf install git-all`
</code></pre>
<p>Once the command output has completed, you can verify the installation by typing:</p>
<pre><code>git version
</code></pre>
<p>Note: You can download the proper Git versions and read more about how to install on specific Linux systems, like installing Git on Ubuntu or Fedora,  <a href="https://git-scm.com/download/linux">in git-scm’s documentation</a>.</p>

