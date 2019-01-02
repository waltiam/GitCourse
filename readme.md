# GIT Quick Start

## Local Installation

The common tooling to use in the _GIT_ world is found [here](https://git-scm.com/download/win) for _Windows_.  Download and install this application accepting the default settings.  Downstream, you can re-install the tool with settings which you feel are more in line with your personal development style.  There is also a commonly used UI tool, [_Tortoise GIT_](https://tortoisegit.org/), the commands provided here are also available from within that tool; you're on your own to find and use them.

Once installed the _GIT_ for _Windows_ tools gives you a console or command window to work through.  Stop whining about the lack of UI and _intellisense_ and start using your brain.  In any case the following is all from the _GIT Bash_ command window, if you are uncomfortable with the command window I suggest a quick refresher.  I would suggest a tool like [cmder](http://cmder.net/) to assist with dealing with console windows.

## Initial Configuration

> The code samples that follow are all paste-able in the console window.

_GIT_ requires to 'know' who you are to operate against repositories, the following two lines will set up your environment:

```bash
git config --global user.name "walt.speelman"
git config --global user.email "walt.speelman@caseware.com"
```

> You should probably use your own user name and email at this step.

You can view your settings using the following command:

```bash
git config --list
```

## Workflow 1 - Creating a New Repository


_It is unlikely that you will need to create a repository initially, however, to get a place to work in this is a *safe* place.  If you'd rather start with existing code use the `clone` command._

_GIT_ is a distributed version control system.  This means that every repository is a completely autonomous system.  The code in repositories can merged with other repositories by pulling the code into them.  So let's start with creating a local repository:

```bash
# change to the user home directory
cd ~
# make a new dirctory called `sample`
mkdir sample
# change the current working directory to `sample`
cd sample
# initialize an empty git repository
git init
```

The first three commands are common shell commands and the forth is a _GIT_ command, all _GIT_ commands start with `git`, in _GIT Bash_ case is important. The only visible thing this command does in add a hidden `.git` folder to the local repository. 

### Files for a New Repository

Since this is a new repository you should add a couple of user files:

```bash
# the readme.md (mark down) file is displayed by most remote repository tools
touch readme.md
# this is the list of files that the source control ignore
touch .gitignore
```
> We can ignore dependency caches such as contents  of /node_modules or /packages ; compiled code such as .o , .pyc and .class files ; build output directories such as /bin , /out  or /target

A [mark down syntax](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) cheat sheet is useful.

## Workflow 2 - Using an Existing Repository

To get remote code locally:

```bash
# change to the local working root
cd /c/src/
# get the remote files
git clone https://therearellama.visualstudio.com/_git/GIT_PRIMER
# To get the remote files in a directory named something other than GIT PRIMER
# This command does the same thing as the previoud one, but the directory is called MyGit
git clone https://therearellama.visualstudio.com/_git/GIT_PRIMER MyGit
```

## Workflow 3 - Adding Files

_GIT_ is a distributed version control system, this means that there is no centralized repository, the repository that you have local is up to date if you have pulled changes from all your colleagues repository. Often times there is a *master* repository, this could also be called *main* or *gold*, this is the the repository that the distribution build comes from.  More on remote repositories later, for now let's just think about our local repository.  

> After this point the code blocks are no longer cut and paste-able because I am showing both user input, prefixed with a `$` and system output.  Each line, after the `$` can still be copied.

Let's create a file:

```bash
$ echo Hey there, How are doing today? >> Hello.txt
$ ls -al
total 29
drwxr-xr-x 1 walt.speelman 1049089    0 Dec 19 10:09 ./
drwxr-xr-x 1 walt.speelman 1049089    0 Dec 18 10:52 ../
drwxr-xr-x 1 walt.speelman 1049089    0 Dec 19 09:23 .git/
-rw-r--r-- 1 walt.speelman 1049089 3036 Dec 19 09:53 Git_Quick_Start.md
-rw-r--r-- 1 walt.speelman 1049089   30 Dec 19 10:09 Hello.txt
```

Our new file `Hello.txt` has been added to our workspace, the local repository has no knowledge of this file:

```bash
$ git status
On branch master
Your branch is up to date with 'origin/master'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   Git_Quick_Start.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)

        Hello.txt

no changes added to commit (use "git add" and/or "git commit -a")
```

This tells us that our new file `Hello.txt` exists but is currently untracked.  It even suggests two commands we could use.  

```bash
# Staging files to be commited: Adding the newly created `Hello.txt` to the local repository
$ git  add Hello.txt

# To unstage a file, use reset HEAD with filename
$ git reset HEAD <file>

# Commiting the files to local repository. This will commit all the staged files if the file is not specified.
$ git commit <file> -m "Commit message"
```

## Workflow 4 - Commiting local repository to remote repository
> Copy the link of your remote repository. Add the copied link where your local repository will be pushed
```bash
# Add the url for the remote repository
$ git remote add origin <remote repository url>

# Check the remote repository url. It shows you the URLs that Git has stored when reading and writing to the remote
$ git remote -v

# Pushing all staged changes to remote repository. This will work once the remote repository url has been setup
$ git push -u origin --all
```



