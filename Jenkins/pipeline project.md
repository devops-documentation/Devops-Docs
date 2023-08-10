<h2 id="what-is-jenkins-pipeline">What is Jenkins Pipeline?<a href="https://www.jenkins.io/doc/book/pipeline/#overview"></a></h2>
<p>Jenkins Pipeline (or simply “Pipeline” with a capital “P”) is a suite of plugins which supports implementing and integrating  <em>continuous delivery pipelines</em>  into Jenkins.</p>
<p>A  <em>continuous delivery (CD) pipeline</em>  is an automated expression of your process for getting software from version control right through to your users and customers. Every change to your software (committed in source control) goes through a complex process on its way to being released. This process involves building the software in a reliable and repeatable manner, as well as progressing the built software (called a “build”) through multiple stages of testing and deployment.</p>
<p>Pipeline provides an extensible set of tools for modeling simple-to-complex delivery pipelines “as code” via the  <a href="https://www.jenkins.io/doc/book/pipeline/syntax">Pipeline domain-specific language (DSL) syntax</a>.</p>
<h2 id="jenkins-pipeline-tutorial-concepts">Jenkins Pipeline Tutorial Concepts</h2>
<p>We hope that Jenkins is up and running in your Windows system, following the steps mentioned above in this Jenkins pipeline tutorial. Before moving ahead with Jenkins test automation with Selenium, it is time to get accustomed to some of this Jenkins pipeline tutorial’s crucial concepts.</p>
<p>Here they are-</p>
<p><strong>Pipeline</strong></p>
<p>It is a user-defined framework that includes all the processes like create, check, deploy, etc. In a Jenkinsfile, it’s a list of all the levels. All of the stages and steps within this block are described. This is the fundamental block to the syntax of a declarative pipeline.</p>
<pre><code>pipeline  {
}
</code></pre>
<p><strong>Node</strong></p>
<p>A node is a system running a complete workflow. It’s an integral part of the syntax of the scripted pipeline.</p>
<pre><code>node  {
}
</code></pre>
<p><strong>Agent</strong></p>
<p>An agent is described as a directive that can run multiple builds using just one Jenkins instance. This feature helps spread the workload to various agents and execute multiple projects within Jenkins’s single instance. It instructs Jenkins to assign the builds to an executor.</p>
<p>A single agent may be defined for a whole Jenkins pipeline, or different agents may be assigned to execute each stage within a pipeline. Some of the most commonly used Agent parameters are:</p>
<ol>
<li>Any</li>
</ol>
<p>Runs the stage pipeline on any available agent.</p>
<ol start="3">
<li>None</li>
</ol>
<p>This parameter is added to the root of the pipeline. It means that there is no global agent for the entire pipeline, and each stage must define its own agent.</p>
<p><strong>Stages</strong></p>
<p>This section includes all of the work that needs to be completed. The work is defined in the form of stages. Within this Directive, there may be more than one level. Each stage executes a particular task.</p>
<pre><code>agent any 
stages { 
    stage ('Build') { 
    }
    stage ('Test') { 
    }
    stage ('Deploy') {     
    }
  }          
}
</code></pre>
<p><strong>Steps</strong></p>
<p>Within a stage block, the pipeline can be described as a series of steps. Such steps are performed in sequence for the execution of a level. Within a Steps guideline, there must be at least one step.</p>
<pre><code>pipeline { 
agent any 
    stages { 
        stage ('Build') { 
            steps { 
                echo 
                'Running build phase. ' 
            }
        }
    }
}
</code></pre>
<h2 id="creating-a-jenkins-pipeline--running-our-first-test">Creating A Jenkins Pipeline &amp; Running Our First Test</h2>
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
<p>Below is the sample Jenkins File for the Pipeline, which has the required configuration details.</p>
<pre><code>pipeline {
agent any
stages {
    stage('Code Checkout') {
        steps {
            git branch: 'vp-rem', url: 'https://github.com/devopshydclub/vprofile-project.git'
        }
    }
    stage('Build') {
        steps {
          sh "mvn package" 
        }
    }
    stage('Deploy') {
        steps {
                  deploy adapters: [tomcat8(credentialsId: '0b99d1fe-1a07-4e3d-813e-75a13fa00b29', path: '', url: 'http://localhost:8080/')], contextPath: 'bookig', war: '**/*.war'
         }
      }
    }
  }
</code></pre>
<p><strong>Step 1:</strong>  We create a  <strong>New Project</strong>  for the Pipeline by navigating to Jenkins and then click on New Item.</p>
<p><img src="https://i.imgur.com/gVwB2WW.png" alt="Imgur"></p>
<p><strong>Step 2:</strong> Next, we select <strong>Pipeline</strong> from the given list of options.</p>
<p><img src="https://i.imgur.com/iba2igH.png" alt="Imgur"></p>
<p><strong>Step 3:</strong>  Then, we will scroll down to  <strong>pipeline</strong>  and paste the pipeline script code that we saw above into the code pane and hit the  <strong>Save</strong>  button.</p>
<p><img src="https://i.imgur.com/IThOq3f.png" alt="Imgur"></p>
<h2 id="pipeline-syntax">pipeline Syntax</h2>
<p>Use pipeline syntax to generate deploy stage. click in it</p>
<p><img src="https://i.imgur.com/eSQit9x.png" alt="Imgur"></p>
<ul>
<li>Now, select Deploy war to a container</li>
</ul>
<p><img src="https://i.imgur.com/PKlwHDT.png" alt="Imgur"></p>
<ul>
<li>Enter war file name (eg: **/*war) Add context path and click add container.</li>
</ul>
<p><img src="https://i.imgur.com/P4IBanc.png" alt="Imgur"></p>
<ul>
<li>In container section click on tomcat</li>
</ul>
<p><img src="https://i.imgur.com/mynKUUx.png" alt="Imgur"></p>
<ul>
<li>Add tom cat credential and URL by default tomcat runs on <a href="http://localhost:8080/">http://localhost:8080/</a></li>
</ul>
<p><img src="https://i.imgur.com/AmFPFbO.png" alt="Imgur"></p>
<ul>
<li>next click on generate pipeline script and copy the script.</li>
</ul>
<p><img src="https://i.imgur.com/qeQqnO8.png" alt="Imgur"></p>
<p><strong>Step 4:</strong>  We would need to set up a test build, which can be quickly done via the Jenkins UI by clicking  <strong>Build Now</strong>.</p>
<p><img src="https://i.imgur.com/ShBWlJq.png" alt="Imgur"></p>
<p><strong>Step 5:</strong>  We can see a new build generating under the build history as we click on  <strong>Build Now</strong>. The console logs output can be viewed by clicking on the Build.</p>
<p><img src="https://i.imgur.com/L55AX64.png" alt="Imgur"></p>
<p>navigate to the URL <a href="http://localhost:8080/train/">http://localhost:8080/train/</a></p>
<p><img src="https://i.imgur.com/bc3BTcW.png" alt="Imgur"></p>

