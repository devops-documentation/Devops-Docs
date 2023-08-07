<h2 id="git-commands">Git Commands</h2>
<h1 id="git-init">Git init</h1>
<pre><code>git init
</code></pre>
<p><code>git init</code>  turns any directory into a Git repository.</p>
<h2 id="what-does--git-init--do"><a href="https://github.com/git-guides/git-init#what-does-git-init-do"></a>What Does  <code>git init</code>  Do?</h2>
<p><code>git init</code>  is one way to start a new project with Git. To start a repository, use either  <code>git init</code>  or  <code>git clone</code>  - not both.</p>
<p>To initialize a repository, Git creates a hidden directory called  <code>.git</code>. That directory stores all of the objects and refs that Git uses and creates as a part of your project’s history. This hidden  <code>.git</code>  directory is what separates a regular directory from a Git repository.</p>
<h2 id="how-to-use--git-init"><a href="https://github.com/git-guides/git-init#how-to-use-git-init"></a>How to Use  <code>git init</code></h2>
<h3 id="common-usages-and-options-for--git-init"><a href="https://github.com/git-guides/git-init#common-usages-and-options-for-git-init"></a>Common usages and options for  <code>git init</code></h3>
<ul>
<li><code>git init</code>: Transform the current directory into a Git repository</li>
<li><code>git init &lt;directory&gt;</code>: Transform a directory in the current path into a Git repository</li>
<li><code>git init --bare</code>: Create a new bare repository (a repository to be used as a remote repository only, that won’t contain active development)</li>
</ul>
<p>You can see all of the options with  <code>git init</code>  in  <a href="https://git-scm.com/docs/git-init">git-scm’s documentation</a>.</p>
<p><img src="https://i.imgur.com/azYTlzf.png" alt="Imgur"></p>
<h1 id="git-add">Git Add</h1>
<pre><code>git add .
</code></pre>
<p>The  <code>git add</code>  command adds new or changed files in your working directory to the Git staging area.</p>
<p><code>git add</code>  is an important command - without it, no  <code>git commit</code>  would ever do anything. Sometimes,  <code>git add</code>  can have a reputation for being an unnecessary step in development. But in reality,  <code>git add</code>  is an important and powerful tool.  <code>git add</code>  allows you to shape history without changing how you work.</p>
<h2 id="how-to-use--git-add"><a href="https://github.com/git-guides/git-add#how-to-use-git-add"></a>How to Use  <code>git add</code></h2>
<h3 id="common-usages-and-options-for--git-add"><a href="https://github.com/git-guides/git-add#common-usages-and-options-for-git-add"></a>Common usages and options for  <code>git add</code></h3>
<ul>
<li><code>git add &lt;path&gt;</code>: Stage a specific directory or file</li>
<li><code>git add .</code>: Stage all files (that are not listed in the  <code>.gitignore</code>) in the entire repository</li>
<li><code>git add -p</code>: Interactively stage hunks of changes</li>
</ul>
<p>You can see all of the many options with  <code>git add</code>  in  <a href="https://git-scm.com/docs/git-add">git-scm’s documentation</a>.<br>
<img src="https://i.imgur.com/HH8fad7.png" alt="Imgur"></p>
<h1 id="git-commit">Git Commit</h1>
<p><code>git commit</code>  creates a commit, which is like a snapshot of your repository. These commits are snapshots of your entire repository at specific times. You should make new commits often, based around logical units of change. Over time, commits should tell a story of the history of your repository and how it came to be the way that it currently is. Commits include lots of metadata in addition to the contents and message, like the author, timestamp, and more.</p>
<h2 id="how-git-commit-works"><a href="https://github.com/git-guides/git-commit#how-git-commit-works"></a>How Git Commit Works</h2>
<p>Commits are the building blocks of “save points” within Git’s version control.</p>
<pre><code>git commit -m "first commit"
</code></pre>
<h3 id="commits-shape-history"><a href="https://github.com/git-guides/git-commit#commits-shape-history"></a>Commits shape history</h3>
<p>By using commits, you’re able to craft history intentionally and safely. You can make commits to different branches, and specify exactly what changes you want to include. Commits are created on the branch that you’re currently checked out to (wherever HEAD is pointing) so it’s always a good idea to run  <code>git status</code>  before making a commit, to check that you’re checked-out to the branch that you intend to be. Before you commit, you will need to stage any new changes that you’d like to include in the commit using  <code>git add [file]</code>.</p>
<p>Commits are lightweight SHA hashes, objects within Git. As long as you’re working with text files, you won’t need to worry about how many files you have, how big they are, or how many commits you make. Git can handle it!</p>
<h3 id="committing-in-two-phases"><a href="https://github.com/git-guides/git-commit#committing-in-two-phases"></a>Committing in two phases</h3>
<p>Commits have two phases to help you craft commits properly. Commits should be logical, atomic units of change that represent a specific idea. But, not all humans work that way. You may get carried away and end up solving two or three problems before you remember to commit! That’s OK - Git can handle that. Once you’re ready to craft your commits, you’ll use  <code>git add &lt;FILENAME&gt;</code>  to specify the files that you’d like to “stage” for commit. Without adding any files, the command  <code>git commit</code>  won’t work. Git only looks to the staging area to find out what to commit. Staging, or adding, files, is possible through the command line, and also possible with most Git interfaces like GitHub Desktop by selecting the lines or files that you’d like to stage.</p>
<p>You can also use a handy command,  <code>git add -p</code>, to walk through the changes and separate them out, even if they’re in the same file.</p>
<h2 id="how-to-use-git-commit"><a href="https://github.com/git-guides/git-commit#how-to-use-git-commit"></a>How to Use Git Commit</h2>
<h3 id="common-usages-and-options-for-git-commit"><a href="https://github.com/git-guides/git-commit#common-usages-and-options-for-git-commit"></a>Common usages and options for Git Commit</h3>
<ul>
<li><code>git commit</code>: This starts the commit process, but since it doesn’t include a  <code>-m</code>  flag for the message, your default text editor will be opened for you to create the commit message. If you haven’t configured anything, there’s a good chance this will be VI or Vim. (To get out, press esc, then  <code>:w</code>, and then Enter. 😉)</li>
<li><code>git commit -m "descriptive commit message"</code>: This starts the commit process, and allows you to include the commit message at the same time.</li>
<li><code>git commit -am "descriptive commit message"</code>: In addition to including the commit message, this option allows you to skip the staging phase. The addition of  <code>-a</code>  will automatically stage any files that are already being tracked by Git (changes to files that you’ve committed before).</li>
<li><code>git commit --amend</code>: Replaces the most recent commit with a new commit. (More on this later!)</li>
</ul>
<p>To see all of the possible options you have with  <code>git commit</code>, check out  <a href="https://git-scm.com/docs/git-commit">Git’s documentation</a>.</p>
<p><img src="https://i.imgur.com/OgYnZMf.png" alt="Imgur"></p>
<h3 id="how-to-undo-commits-in-git"><a href="https://github.com/git-guides/git-commit#how-to-undo-commits-in-git"></a>How to Undo Commits in Git</h3>
<p>Sometimes, you may need to change history. You may need to undo a commit. If you find yourself in this situation, there are a few very important things to remember:</p>
<ul>
<li>If you are “undoing” a commit that exists on the remote, you could create big problems for your collaborators</li>
<li>Undoing a commit on work that you only have locally is much safer</li>
</ul>
<h1 id="git-remote">Git Remote</h1>
<p>There are some operations with  <code>git remote</code>, like  <code>git remote -v</code>, that you may use occasionally.</p>
<p>But, the concept of a remote within Git is important and powers many of the other operations.</p>
<h2 id="what-does-git-remote-do"><a href="https://github.com/git-guides/git-remote#what-does-git-remote-do"></a>What does Git remote do?</h2>
<pre><code>git remote add origin "&lt; URL to Repository &gt;"
</code></pre>
<p><code>git remote</code>  manages the set of remotes that you are tracking with your local repository.</p>
<h3 id="common--git-remote--commands"><a href="https://github.com/git-guides/git-remote#common-git-remote-commands"></a>Common  <code>git remote</code>  commands</h3>
<ul>
<li><code>git remote -v</code>: List the current remotes associated with the local repository</li>
<li><code>git remote add [name] [URL]</code>: Add a remote</li>
<li><code>git remote remove [name]</code>: Remove a remote</li>
</ul>
<h3 id="what-is--origin"><a href="https://github.com/git-guides/git-remote#what-is-origin"></a>What is  <code>origin</code>?</h3>
<p>If you try running  <code>git remote -v</code>  in your repositories, you’ll probably see something called  <code>origin</code>. You may notice  <code>origin</code>  in many messages from Git.  <code>origin</code>  is the human-friendly name for the URL that the remote repository is stored at. It’s like a key value pair, and  <code>origin</code>  is the default.<br>
<img src="https://i.imgur.com/8j29QwD.png" alt="Imgur"></p>
<h1 id="git-status">Git Status</h1>
<pre><code>git status
</code></pre>
<p><code>git status</code>  shows the current state of your Git working directory and staging area.</p>
<h2 id="what-does--git-status--do"><a href="https://github.com/git-guides/git-status#what-does-git-status-do"></a>What Does  <code>git status</code>  Do?</h2>
<p>When in doubt, run  <code>git status</code>. This is  <em>always</em>  a good idea. The  <code>git status</code>  command only outputs information, it won’t modify commits or changes in your local repository.</p>
<p>A useful feature of  <code>git status</code>  is that it will provide helpful information depending on your current situation. In general, you can count on it to tell you:</p>
<ul>
<li>Where  <code>HEAD</code>  is pointing, whether that is a branch or a commit (this is where you are “checked out” to)</li>
<li>If you have any changed files in your current directory that have not yet been committed</li>
<li>If changed files are staged or not</li>
<li>If your current local branch is linked to a remote branch, then  <code>git status</code>  will tell you if your local branch is behind or ahead by any commits</li>
</ul>
<p>During merge conflicts,  <code>git status</code>  will also tell you exactly which files are the source of the conflict.</p>
<h2 id="how-to-use--git-status"><a href="https://github.com/git-guides/git-status#how-to-use-git-status"></a>How to Use  <code>git status</code></h2>
<h3 id="common-usages-and-options-for--git-status"><a href="https://github.com/git-guides/git-status#common-usages-and-options-for-git-status"></a>Common usages and options for  <code>git status</code></h3>
<ul>
<li><code>git status</code>: Most often used in its default form, this shows a good base of information</li>
<li><code>git status -s</code>: Give output in short format</li>
<li><code>git status -v</code>: Shows more “verbose” detail including the textual changes of any uncommitted files</li>
</ul>
<p>You can see all of the options with  <code>git status</code>  in  <a href="https://git-scm.com/docs/git-status">git-scm’s documentation</a>.<br>
<img src="https://i.imgur.com/JjdIPzZ.png" alt="Imgur"></p>
<h1 id="git-push">Git Push</h1>
<pre><code>git push origin [your branch]
</code></pre>
<p><code>git push</code>  uploads all local branch commits to the corresponding remote branch.</p>
<h2 id="what-does--git-push--do"><a href="https://github.com/git-guides/git-push#what-does-git-push-do"></a>What Does  <code>git push</code>  Do?</h2>
<p><code>git push</code>  updates the remote branch with local commits. It is one of the four commands in Git that prompts interaction with the remote repository. You can also think of  <code>git push</code>  as  <em>update</em>  or  <em>publish</em>.</p>
<p>By default,  <code>git push</code>  only updates the corresponding branch on the remote. So, if you are checked out to the  <code>main</code>  branch when you execute  <code>git push</code>, then only the  <code>main</code>  branch will be updated. It’s always a good idea to use  <code>git status</code>  to see what branch you are on before pushing to the remote.</p>
<h2 id="how-to-use--git-push"><a href="https://github.com/git-guides/git-push#how-to-use-git-push"></a>How to Use  <code>git push</code></h2>
<p>After you make and commit changes locally, you can share them with the remote repository using  <code>git push</code>. Pushing changes to the remote makes your commits accessible to others who you may be collaborating with. This will also update any open pull requests with the branch that you’re working on.</p>
<p>As best practice, it’s important to run the  <code>git pull</code>  command before you push any new changes to the remote branch. This will update your local branch with any new changes that may have been pushed to the remote from other contributors. Pulling before you push can reduce the amount of merge conflicts you create on GitHub - allowing you to resolve them locally before pushing your changes to the remote branch.</p>
<h3 id="common-usages-and-options-for--git-push"><a href="https://github.com/git-guides/git-push#common-usages-and-options-for-git-push"></a>Common usages and options for  <code>git push</code></h3>
<ul>
<li><code>git push -f</code>: Force a push that would otherwise be blocked, usually because it will delete or overwrite existing commits  <em>(Use with caution!)</em></li>
<li><code>git push -u origin [branch]</code>: Useful when pushing a new branch, this creates an upstream tracking branch with a lasting relationship to your local branch</li>
<li><code>git push --all</code>: Push all branches</li>
<li><code>git push --tags</code>: Publish tags that aren’t yet in the remote repository</li>
</ul>
<p>You can see all of the options with  <code>git push</code>  in  <a href="https://git-scm.com/docs/git-push">git-scm’s documentation</a>.<br>
<img src="https://i.imgur.com/Oe3yxv6.png" alt="Imgur"></p>
<h1 id="git-clone">Git Clone</h1>
<p>The  <code>git clone</code>  command is used to create a copy of a specific repository or branch within a repository.</p>
<pre><code>git clone [your repository URL ]
</code></pre>
<p>Git is a distributed version control system. Maximize the advantages of a full repository on your own machine by cloning.</p>
<h3 id="what-does--git-clone--do"><a href="https://github.com/git-guides/git-clone#what-does-git-clone-do"></a>What Does  <code>git clone</code>  Do?</h3>
<p>When you clone a repository, you don’t get one file, like you may in other centralized version control systems. By cloning with Git, you get the entire repository - all files, all branches, and all commits.</p>
<p>Cloning a repository is typically only done once, at the beginning of your interaction with a project. Once a repository already exists on a remote, like on GitHub, then you would clone that repository so you could interact with it locally. Once you have cloned a repository, you won’t need to clone it again to do regular development.</p>
<p>The ability to work with the entire repository means that all developers can work more freely. Without being limited by which files you can work on, you can work on a feature branch to make changes safely. Then, you can:</p>
<ul>
<li>later use  <code>git push</code>  to share your branch with the remote repository</li>
<li>open a pull request to compare the changes with your collaborators</li>
<li>test and deploy as needed from the branch</li>
<li>merge into the  <code>main</code>  branch.</li>
</ul>
<h2 id="how-to-use--git-clone"><a href="https://github.com/git-guides/git-clone#how-to-use-git-clone"></a>How to Use  <code>git clone</code></h2>
<h3 id="common-usages-and-options-for--git-clone"><a href="https://github.com/git-guides/git-clone#common-usages-and-options-for-git-clone"></a>Common usages and options for  <code>git clone</code></h3>
<ul>
<li><code>git clone [url]</code>: Clone (download) a repository that already exists on GitHub, including all of the files, branches, and commits.</li>
<li><code>git clone --mirror</code>: Clone a repository but without the ability to edit any of the files. This includes the refs, or branches. You may want to use this if you are trying to create a secondary copy of a repository on a separate remote and you want to match all of the branches. This may occur during configuration using a new remote for your Git hosting, or when using Git during automated testing.</li>
<li><code>git clone --single-branch</code>: Clone only a single branch</li>
<li><code>git clone --sparse</code>: Instead of populating the working directory with all of the files in the current commit recursively, only populate the files present in the root directory. This could help with performance when cloning large repositories with many directories and sub-directories.</li>
<li>`git clone --recurse-submodules[=&lt;pathspec]: After the clone is created, initialize and clone submodules within based on the provided pathspec. This may be a good option if you are cloning a repository that you know to have submodules, and you will be working with those submodules as dependencies in your local development.</li>
</ul>
<p>You can see all of the many options with  <code>git clone</code>  in  <a href="https://git-scm.com/docs/git-clone">git-scm’s documentation</a>.<br>
<img src="https://i.imgur.com/XHoGOub.png" alt="Imgur"></p>
<h1 id="git-pull">Git Pull</h1>
<p><code>git pull</code>  updates your current local working branch, and all of the remote tracking branches. It’s a good idea to run  <code>git pull</code>  regularly on the branches you are working on locally.</p>
<pre><code>git pull [your repository URL ]
</code></pre>
<p>Without  <code>git pull</code>, (or the effect of it,) your local branch wouldn’t have any of the updates that are present on the remote.</p>
<h3 id="what-does--git-pull--do"><a href="https://github.com/git-guides/git-pull#what-does-git-pull-do"></a>What Does  <code>git pull</code>  Do?</h3>
<p><code>git pull</code>  is one of the 4 remote operations within Git. Without running  <code>git pull</code>, your local repository will never be updated with changes from the remote.  <code>git pull</code>  should be used every day you interact with a repository with a remote, at the minimum. That’s why  <code>git pull</code>  is one of the most used Git commands.</p>
<h3 id="git-pull--and--git-fetch"><a href="https://github.com/git-guides/git-pull#git-pull-and-git-fetch"></a><code>git pull</code>  and  <code>git fetch</code></h3>
<p><code>git pull</code>, a combination of  <code>git fetch</code>  +  <code>git merge</code>, updates some parts of your local repository with changes from the remote repository. To understand what is and isn’t affected by  <code>git pull</code>, you need to first understand the concept of remote tracking branches. When you clone a repository, you clone one working branch,  <code>main</code>, and all of the remote tracking branches.  <code>git fetch</code>  updates the remote tracking branches.  <code>git merge</code>  will update your current branch with any new commits on the remote tracking branch.</p>
<p><code>git pull</code>  is the most common way to update your repository.</p>
<p>However, you may want to use  <code>git fetch</code>  instead. One reason to do this may be that you expect conflicts. Conflicts can occur in this way if you have new local commits, and new commits on the remote. Just like a merge conflict that would happen between two different branches, these two different lines of history could contain changes to the same parts of the same file. If you first operate  <code>git fetch</code>, the merge won’t be initiated, and you won’t be prompted to solve the conflict. This gives you the flexibility to resolve the conflict later without the need of network connectivity.</p>
<p>Another reason you may want to run  <code>git fetch</code>  is to update to all remote tracking branches before losing network connectivity. If you run  <code>git fetch</code>, and then later try to run  <code>git pull</code>  without any network connectivity, the  <code>git fetch</code>  portion of the  <code>git pull</code>  operation will fail.</p>
<p>If you do use  <code>git fetch</code>  instead of  <code>git pull</code>, make sure you remember to  <code>git merge</code>. Merging the remote tracking branch into your own branch ensures you will be working with any updates or changes.</p>
<h2 id="how-to-use--git-pull"><a href="https://github.com/git-guides/git-pull#how-to-use-git-pull"></a>How to Use  <code>git pull</code></h2>
<h3 id="common-usages-and-options-for--git-pull"><a href="https://github.com/git-guides/git-pull#common-usages-and-options-for-git-pull"></a>Common usages and options for  <code>git pull</code></h3>
<ul>
<li><code>git pull</code>: Update your local working branch with commits from the remote,  <em>and</em>  update all remote tracking branches.</li>
<li><code>git pull --rebase</code>: Update your local working branch with commits from the remote, but rewrite history so any local commits occur after all new commits coming from the remote, avoiding a merge commit.</li>
<li><code>git pull --force</code>: This option allows you to force a fetch of a specific remote tracking branch when using the  <code>&lt;refspec&gt;</code>  option that would otherwise not be fetched due to conflicts. To force Git to overwrite your current branch to match the remote tracking branch, read below about using  <code>git reset</code>.</li>
<li><code>git pull --all</code>: Fetch  <em>all</em>  remotes - this is handy if you are working on a fork or in another use case with multiple remotes.</li>
</ul>
<p>You can see all of the many options with  <code>git pull</code>  in  <a href="https://git-scm.com/docs/git-pull">git-scm’s documentation</a>.<br>
<img src="https://i.imgur.com/IbqgOBf.png" alt="Imgur"></p>
<h1 id="git-branch">Git branch</h1>
<p>Until now, we saw how you can work on git. But now imagine, multiple developers working on the same project or repository. To handle the workspace of multiple developers, we use branches. To create a branch from an existing branch, we type</p>
<pre><code>git branch &lt;name of your branch&gt;
</code></pre>
<p>Similarly, to delete a branch use the command</p>
<pre><code>git branch -D &lt;branch name&gt;
</code></pre>
<p><img src="https://i.imgur.com/p30tknJ.png" alt="Imgur"></p>
<h1 id="git-ckeckout">Git ckeckout</h1>
<p>To switch to the new branch, we type the command</p>
<pre><code>git checkout &lt;branch name&gt;
</code></pre>
<p><img src="https://i.imgur.com/P4ljsDw.png" alt="Imgur"></p>
<h1 id="git-log">Git log</h1>
<p>Want to check the log for every commit detail in your repository? You can accomplish that using the command git log</p>
<pre><code>git log
</code></pre>
<p><img src="https://i.imgur.com/9sl3ITF.png" alt="Imgur"></p>
<h1 id="git-revert">Git revert</h1>
<p>This command helps you in reverting a commit, To pervious version</p>
<pre><code>git revert &lt;commit-id&gt;
</code></pre>
<p><img src="https://i.imgur.com/cIyLz1n.png" alt="Imgur"></p>
<h1 id="merge-branches">Merge branches</h1>
<p>Once the developer has finished his code/feature on his branch, the code will have to be combined with the master branch. This can be done using two ways:</p>
<ol>
<li>git merge</li>
<li>git rebase</li>
</ol>
<h2 id="git-merge">Git merge</h2>
<pre><code>git merge &lt;source-branch-name&gt;
</code></pre>
<ul>
<li>If you want to apply changes from one branch to another branch, one can use merge command</li>
<li>Should be used on remote branches, since history does not change</li>
<li>Creates a new commit, which is a merger of the two branches</li>
</ul>
<p><img src="https://i.imgur.com/vPDUj4C.png" alt="Imgur"></p>
<h2 id="git-rebase">Git rebase</h2>
<pre><code>git rebase &lt;surce-branch-name&gt;
</code></pre>
<ul>
<li>
<p>This is an alternative to git merge command</p>
</li>
<li>
<p>Should be used on local branches, since history does change and will be confusing for other team members</p>
</li>
<li>
<p>Does not create any new commit, and results in a cleaner history</p>
</li>
<li>
<p>The history is based on common commit of the two branches (base)</p>
</li>
<li>
<p>The destination’s branch commit is pulled from it’s “base” and “rebased” on to the latest commit on the source branch</p>
</li>
<li>
<p>Imagine, you have a Master branch and a test branch(local branch)</p>
</li>
<li>
<p>The developer has finished his/her work in the test branch</p>
</li>
<li>
<p>But the master moved forward, while the code was being developed</p>
</li>
<li>
<p>Code being developed is related to the new commit added in master</p>
</li>
<li>
<p>Therefore you want all the changes from master in feature.</p>
</li>
<li>
<p>Since, it is a local branch, you would want a cleaner or linear history, you decide to use git rebase</p>
<p><img src="https://i.imgur.com/W0xPQRm.png" alt="Imgur"></p>
</li>
</ul>
<p>jhjhfkdhgk</p>
<pre><code>jfhjdhfkdhk
</code></pre>

