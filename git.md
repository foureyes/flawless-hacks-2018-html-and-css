---
layout: slides
title: Flawless Hacks - Git
---

<section markdown="block" class="intro-slide">
# Git, Maybe? ¯\\_(ツ)_/¯

### A quick workshop on using git for your hackathon project!


#### (And an inadvertent crash course on the commandline)
</section>
<section markdown="block">
## WAT?

This is a __beginner's workshop__ on __git__, a tool that helps _manage_ your source code. 💻

We'll see how to use git to ... &rarr;

* {:.fragment} ✅  save historical versions of your work on your own computer and on a _remote_ computer
* {:.fragment} ✅  facilitate collaboration on your project using a __simple__ workflow
* {:.fragment} ✅  (oh, and some commandline stuff too)

<small> You probably don't want to stay here if already know the material above or are expecting an in-depth talk on branching, merging, and rebasing or git internals🚫</small>
{:.fragment}

</section>

<section markdown="block">
## Introductions

### Me
{:.fragment}

* {:.fragment} Hi. I'm __Joe Versoza__. 👋
* {:.fragment} I teach some intro courses at NYU. 🎓
* {:.fragment} I only _kind of_ know git ¯\\_(ツ)_/¯
* {:.fragment} Embarrassing Fact (1 out of 1000000): I'm _afraid_ of graphical user interfaces 😱

### You
{:.fragment}

* {:.fragment} You don't know how to use git
* {:.fragment} You want to learn _some_ git
* {:.fragment} (enough to work on your hackathon project)

</section>

<section markdown="block">
## Requirements

For this workshop, you should probably:

* have a computer 💻
* be _willing_ to work with a partner 🙌
* ask a lot of questions ✋

</section>
<section markdown="block">
## References

#### (The material in this workshop was sourced from the links below)

__Guides that are _way_ better than these slides.__ &rarr;

* [git - the simple guide](http://rogerdudler.github.io/git-guide/)
* [git cheat sheet](https://education.github.com/git-cheat-sheet-education.pdf) from github education
* [gitref.org](http://gitref.org/)

__...And some in-depth articles on git:__ &rarr;
{:.fragment}

* [git from the inside out](https://maryrosecook.com/blog/post/git-from-the-inside-out) (seriously the best! 💯)
* [pro git](http://git-scm.com/book/en/Getting-Started-About-Version-Control) (also amazing)
* [visual git guide](http://marklodato.github.io/visual-git-guide/index-en.html)
* [atlassian's tutorial on version control](https://www.atlassian.com/git/tutorials/what-is-version-control)
{:.fragment}

</section>

<section markdown="block">
## Installation

Open terminal (OSX) or cmd.exe (Windows) and type in __git__ to see if you already have git installed. If you don't, __follow these instructions to install git__ &rarr;

* 🏁 [git for windows](https://git-for-windows.github.io/)
    * ✅  make sure to check off the option that installs __Git Bash__
* 🍎 [instructions for installing on OSX](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git#_installing_on_mac)
* 🐧 [for linux (assuming Debian/Ubuntu or Fedora/Red Hat](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git#_installing_on_mac)

</section>

<section markdown="block">
## Um. Why Even?

__What problems do a source code management / version control system, like git, solve?__ &rarr;

1. {:.fragment} archiving / saving / maintaining __multiple versions__ of your code
2. {:.fragment} __collaborating__ with others
3. {:.fragment} (not a _real_ problem, but... __git is pretty much a standard__ and is required in most software engineering jobs)

</section>

<section markdown="block">
## Backups / Archiving / Versioning

__What are some ways you've used to keep / save different versions of files?__ &rarr;

* {:.fragment} adding a date to a file name? 📅
* {:.fragment} adding extensions to files, like .bak? ⌨️
* {:.fragment} organizing copies by folders? 🗃
    * {:.fragment} perhaps folders with timestamps / dates
    * {:.fragment} or color organized folders
* {:.fragment}ummm... etc.

</section>

<section markdown="block">
## Drawbacks?

__What are some drawbacks methods of saving versions of using the methods in the previous slides?__ &rarr;

* it's __all__ manual 😰
* and, consequently, tedious and error prone 🙅
    * you have to remember to do it!
    * (um, what's the date again?)
    * (etc.)
{:.fragment}

</section>

<section markdown="block">
## Sharing / Collaborating

Have you ever worked on a programming project with more than one person?  __How did you share your code? ↔️__ &rarr;

* email? 📧
* usb? 
* dropbox?
{:.fragment}

</section>

<section markdown="block">
## Sharing / Collaborating Continued

What are some __issues with the methods from the previous slides__ (well, except for DropBox)? &rarr;

* hard to find a specific version 😕
* difficult to determine what the latest version is ⏱
* not clear who made what changes 🤔
* how do you deal with conflicting changes? 😡
{:.fragment}

And some things that __aren't supported by online sync tools__, like DropBox or Google Drive: &rarr;
{:.fragment}

* no way to manage multiple _branches_ of code 🔀
* how do you group changes into features? 
* how can a meaningful description be attached to a change? 📖
{:.fragment}

</section>

<section markdown="block">
## Let's Ask our Computer to Deal With Managing our Source Code 🙃

#### (by using software made for managing your source code)
</section>

<section markdown="block">
## What's Version Control?


__With version control software, you can__ &rarr;

1. {:.fragment} leave __comments__ on changes that you've made 🗣
2. {:.fragment} __revert__ files to a previous state ⏮
3. {:.fragment} __review__ changes made over time, and track __who__ made them 👀
4. {:.fragment} __easily recover from accidentally breaking or deleting code__ 🏥
5. {:.fragment} automatically __merge__ changes to the same file 
6. {:.fragment} _branch_ your code so that you can have __stable and _work-in-progress_ versions of your code__

<small>(This can be applied to any kind of file, but we're mostly concerned with text files)</small>
{:.fragment}
</section>

<section markdown="block">
##  We're Using git!

__The version control system that we'll use is [git](https://git-scm.com/)__  &rarr;

* {:.fragment} it's a __modern distributed source code management__ system
* {:.fragment} it has emerged as __the standard__ version control system to use
* {:.fragment} (some others are...)
  * {:.fragment} [mercurial](https://www.mercurial-scm.org/) (hg)
  * {:.fragment} [subversion](https://subversion.apache.org/) (svn)
  * {:.fragment} cvs - this one is _very_ old!  
</section>

<section markdown="block">
## A Bit About Git

It was developed by this super _friendly_ person, __Linus Torvalds... who?__ &rarr;

<div markdown="block" class="img-container">
![Linux](https://cdn.arstechnica.net/wp-content/uploads/2013/02/linus-eff-you-640x363.png)
</div>
{:.fragment}

<small>He's the person who made [Linux](http://en.wikipedia.org/wiki/Linux), and he created __git__ to maintain the source code to Linux (after using a _proprietary_ version control system).</small>
{:.fragment}

</section>

<section markdown="block">
## Github vs git

__GIT and GITHUB ARE DIFFERENT!__ 

1. {:.fragment} __git is just version control__
    * can be used locally
    * without having to register an account with a website
2. {:.fragment} __GitHub is a website__ 
    * ...that hosts git repositories
    * and has some other features for managing projects
3. {:.fragment} Alternatives to GitHub include:
    * [bitbucket](https://bitbucket.org/)
    * [gitlab](https://about.gitlab.com/)

<small>So... you can use git without github.</small>
{:.fragment}

</section>

<section markdown="block">
## Local Version Control

[See the diagram on pro git](http://git-scm.com/book/en/Getting-Started-About-Version-Control)

* __equivalent to what we may have done manually__ (it's kind of like):
  * {:.fragment} save files in folder with locally as a _snapshot_ of current state of code
  * {:.fragment} recover by going through folders on computer
  * {:.fragment} see versions by the timestamped folder name
* {:.fragment} but __all of this is automated through software__ ‼️
  * {:.fragment} stores changes to your files in a local database / file system
  * {:.fragment} an example of local version control is RCS

</section>

<section markdown="block">
## Centralized Version Control

[See the diagram on pro git](http://git-scm.com/book/en/Getting-Started-About-Version-Control)

* __promoted collaboration__; everyone retrieves and sends code to the same place
* single server that has all of the versioned files
* __everyone working on it had a _working copy_, but not the full repository__
* an example is subversion (SVN)

</section>

<section markdown="block">
## Distributed Version Control

[See the diagram on pro git](http://git-scm.com/book/en/Getting-Started-About-Version-Control)

* __everyone has full repository__ 🙌
* can connect to multiple __remote__ repositories 
* can push and pull to individuals, not just _shared_ or _centralized_ servers
* single server that has all of the versioned files
* __everyone working on it has a _working copy_ and the full repository history (yes, that's a lot!)__

</section>

<section markdown="block">
## Git is a Distributed Version Control System

#### (But We're Really Going to Use a Central Repository Anyway)
</section>

<section markdown="block">
## A Quote...

From a former co-worker of mine, a software engineer that builds web apps:

__"Git is the hardest thing we do here"__

<small>(it's a little complicated sometimes, but for the commands that we'll learn today, hopefully, not-so-much)</small>

</section>


<section markdown="block">
## Some Terminology

__repository__ - the place where your version control system stores the snapshots that you _save_

* think of it as the place where you store all previous/saved versions of your files
* this could be:
  * {:.fragment} __local__ - on your computer
  * {:.fragment} __remote__ - a copy of versions of your files on another computer
</section>

<section markdown="block">
## Some More Terminology

* __git__ - the distributed version control system that we're using
* __github__ - a website that:
    * can __serve as a remote _repository_ for your project__
    * has some project management / project community related features


What's a __remote repository__ again? &rarr;

<div class="fragment" markdown="block">
__A copy of versions of your files on another computer/server__
</div>
</section>

<section markdown="block">
## Where Are My Files

In your __local repository__, git _stores_ your files and versions of your files in a few different _conceptual_ places:

* {:.fragment} __the working directory / working copy__ - stores the version of the files that you're currently modifying / working on
    * that is, the actual files that you're working with
* {:.fragment} __index__ - the staging area where you put stuff that you want to _save_ (or... that you're about to _commit_)
* {:.fragment} __committed changes__ and __HEAD__ - the most recent saved version of your files (or... the last _commit_ that you made), and all versions of your files
</section>

<section markdown="block">
## Another Way to Look at It

__Whew, that was a lot 😓.__ Maybe an easier way of looking at is:

* {:.fragment} __the working directory / working copy__ - stuff you've changed but haven't saved
* {:.fragment} __index__ - stuff that you're about to save
* {:.fragment} __committed work__ and __HEAD__ - stuff that you've saved
</section>

<section markdown="block">
## Aaaaand.  More Terminology.

* to __commit__ your code is: to save a snapshot of your work
* a __diff__ is: - the line-by-line difference between two files or sets of files
</section>

<section markdown="block">
## Two Basic Workflows

__We'll discuss two ways of working with git today__ &rarr;

1. Creating and setting up local and remote repositories
2. Making, saving, and _sharing_ changes
</section>

<section markdown="block">
## Creating Repositories

1. create a local repository
2. configure it to use your name and email (for tracking purposes)
3. create a remote repository
4. _link_ the two
</section>

<section markdown="block">
## Making, Saving, and Sharing Changes

1. make changes
2. put them aside so they can staged for saving / committing
3. save / commit
4. send changes from local repository to remote repository
</section>



<section markdown="block">

## Creating and Setting Up Repositories 

</section>


<section markdown="block">
## Commands for Creation and Set Up of Repositories

We'll be using this for most of our work...

* <code>git clone REPO_URL</code>

<br>
This stuff, not so much, but you should know them too...

* <code>git init</code>
* <code>git config ...</code>
  * <code>git config user.name  "__your user name__"</code>
  * <code>git config user.email __your@email.address__</code>
* <code>git remote add REMOTE_NAME REMOTE_URL</code>
</section>

<section markdown="block">
## git clone

Again, for most of our work, you'll just be cloning an existing repository (creating a local repository from a remote one).

<pre><code data-trim contenteditable>git clone REPOSITORY_URL
</code></pre>

__REPOSITORY_URL__ is usually going to be something that you copy from github.
</section>

<section markdown="block">
## git init

__git init__ - creates a new _local_ repository (using the files in the existing directory)

* you can tell a repository is created by running ls -l ... it creates a .git directory
* again, this creates a new repository - a place to archive / save all versions of your files

<pre><code data-trim contenteditable># in the directory of your repository
git init
</code></pre>
</section>


<section markdown="block">
## git config

__git config__ - configure your user name and email for your commits 

* this has nothing to do with your computer's account or your account on github
* this information helps track changes

<pre><code data-trim contenteditable># in the directory of your repository
git config user.name  "foo bar baz"
git config user.email foo@bar.baz
</code></pre>
</section>


<section markdown="block">
## git remote add 

__git remote add__ - add a remote repository so that you can synchronize changes between it and your local repository

<pre><code data-trim contenteditable>git remote add REPOSITORY_NAME REPOSITORY_URL
</code></pre>

</section>

<section markdown="block">
## Typical Workflow for Making Changes

0. git pull (or git pull --rebase depending on what your team does)
1. make changes
2. git status (to see what changes there are)
3. git add --all (to stage your changes for committing)
4. git status (to see your staged changes)
5. git commit -m 'my message' (to save your changes)
6. git push origin master (optionally send/share your changes to a remote repository)

Check out a workflow chart here: [http://rogerdudler.github.io/git-guide/img/trees.png](http://rogerdudler.github.io/git-guide/img/trees.png)
</section>

<section markdown="block">
## git pull

__git pull__ - get the latest version of code from the remote repository (in case anyone has made any changes!)

<pre><code data-trim contenteditable>git pull

# or if you're using a rebase based workflow
git pull --rebase
</code></pre>
</section>

<section markdown="block">
## git status

__git status__ - show what changes are ready to be committed as well as changes that you are working on in your working directory that haven't been staged yet

<pre><code data-trim contenteditable>git status
</code></pre>
</section>

<section markdown="block">
## git add

__git add__ - mark a change to be staged

<pre><code data-trim contenteditable># in the directory of your repository

# add specific file
git add myfile.txt

# add all
git add --all 
</code></pre>
</section>

<section markdown="block">
## git commit

__git commit__ - take a snapshot of your work

<pre><code data-trim contenteditable># in the directory of your repository
# don't forget the commit message

git commit -m 'commit message goes here'
</code></pre>
</section>

<section markdown="block">
## git log

__git log__ - show commit history of your repository or file

<pre><code data-trim contenteditable># in the directory of your repository

git log

#you can also colorize the output:

git log --color
</code></pre>

</section>

<section markdown="block">
## git diff

__git diff__ - show the line-by-line differences between your last commit and your working directory

<pre><code data-trim contenteditable># in the directory of your repository
# use --color for syntax highlighting

git diff --color

</code></pre>
</section>

<section markdown="block">
## git reset

__git reset__ - revert last commit... or unstage changes

<pre><code data-trim contenteditable># unstage changes
git reset filename.txt

# revert last commit
git reset HEAD^

</code></pre>
</section>

<section markdown="block">
## git push

__git push__ - send your code to a remote repository

<pre><code data-trim contenteditable>git push

# or to specify... push master branch to remote 
# repository called origin
git push origin master
</code></pre>
</section>

<section markdown="block">
## Can't Push!?

If you try to push, but git says __you have to pull first__, that means that there were changes in the remote repository &rarr;

* try running `git pull`
* this will bring your local repository up-to-date


</section>

<section markdown="block">
## Problems with Pull

If you try to pull, but git says __you have changes in your working copy__, that means that your have changes that you haven't committed yet.

* commit your changes using `git add` and `git commit`

If you try to pull, but __you get a merge conflict__ &rarr;

* you'll have to look at the files that have conflicts - get a list with `git status`
* manually fix the conflicts
* `git add` and `git commit` to resolve conflicts

</section>

<section markdown="block">
## Ok, Now Your Turn
</section>

<section markdown="block">
## First, Some Commandline Exercises

__You should probably know these commands__ &rarr;

1. __pwd__ - shows you the current directory that you're in
2. __cd__ - change to another directory
3. __cat__ - show the contents of a file

These commands can be entered in __Terminal__ (apple spacebar, Terminal).

Commandline commands can be thought of as verbs/actions. You can specify the object or target of the verb by adding a space and target afterwards: `cd directory_to_change_to`
</section>

<section markdown="block">
## Some Specific Examples

<pre><code data-trim contenteditable># change to your Desktop
cd /Users/jversoza/Desktop

# go up one directory
cd ../

# go back to Desktop
cd Desktop

# show the directory that we're in
pwd

# show the contents of the file pizza.txt 
# on the Desktop
cat pizza.txt
</code></pre>




</section>

<section markdown="block">
## Notes About Commandline Commands

`cd /Users/jversoza/Desktop`

* if a directory is prefixed with /, then that will be relative to your root directory
* will go to Desktop __regardless of what directory you're int__

`cd Desktop`

* if there's no slash, then it's __relative to the directory you're in__ (the one shown by `pwd`)
* so, will go to Desktop only if you're already in /Users/jversoza

</section>


<section markdown="block">
## Some Stuff to Try

* work in pairs
* create a remote repository
* add both members of pair as collaborators
* both members will clone the repository
* one person will make changes to repository and push
* another person will pull
* try the same, but with a conflict!

</section>






