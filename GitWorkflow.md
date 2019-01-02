# GIT Workflow for Larger Teams

This GIT workflow is directly related to the **VSTS** and incorporates rather tightly with _Visual Studio 2017_.  Other workflows are possible but this is the one that comes out of the box.

> Ultimately a search for [git workflows](https://www.google.ca/search?q=git+workflows) will also yield a reasonable set of results.

## Prerequisite

* The developer has been added to the VSTS team.
* [GIT for windows](https://git-scm.com/download/win) has been installed and configured.
* [TortoiseGIT](https://tortoisegit.org/download/) is a useful bit of tooling.
* If executing this from the command line it is expected that [SSH has been set up](https://www.visualstudio.com/en-us/docs/git/use-ssh-keys-to-authenticate).
* From within Visual Studio use [GIT credential manager](https://www.visualstudio.com/en-us/docs/git/set-up-credential-managers).

## VSTS and Visual Studio Workflow

The recommended workflow to use with VSTS and Visual Studio is branches.

* [GIT workflows from VSTS](https://www.visualstudio.com/en-us/docs/git/tutorial/gitworkflow)

### Feature branching

1. For each story create a branch when work begins.
1. For each task create a branch when work begins.
1. Clone the repository using Visual Studio
1. The remotes/origin > branch select Checkout on the branch to bring it local and begin work.
1. Update the code for the task
1. Commit or stage to the local repository
1. Push the commit(s) to the remote branch
1. Once the feature is completed, and it may take several commit/push cycles, a pull request can be created to move the changes from the branch into the master.  This is done through the VSTS site.

### Pull requests

1. Once a pull request has been made it is available for code review.  All team members can participate in the review.
1. Each reviewer has the option to Approve the PR.
1. Once the PR has the required number of approvals it can be Completed.

## GitHub Workflow

The GitHub workflow is applicable to both GitHub and BitBucket, it does not work as seamlessly on VSTS without a lot of command line work.  The GitHub workflow requires each developer to have a public fork of the master, changes in the developer fork are PR'ed into the master.  GitHub and BitBucket have tools that facilitate this, VSTS and Visual Studio do not.

It is mentioned here simply as an also examined workflow.

## Other GIT readings

* [There is **The Book**](https://git-scm.com/book/en/v2)
* [Naming](https://www.visualstudio.com/en-us/articles/git-branching-guidance)
* [Tutorial](https://www.visualstudio.com/en-us/docs/git/gitquickstart)
* [GIT workflows from Atlassian](https://www.atlassian.com/git/tutorials/syncing)
* [GIT workflows from GIT](https://git-scm.com/book/en/v2)
* [GitHub workflow in VSTS](http://www.woodcp.com/2014/01/how-to-fork-git-repositories-on-visual-studio-online/)

---

### set up to use SSH

`SSH` (**S**ecure **SH**ell) is a netwok protocol used to protect network traffic against trival eavesdropping.  Using `SSH` from a GIT bash command shell means that the GIT destination does not have to prompt for a username and password to authenticate.

#### pre-requisites

* GIT [downloaded](https://git-scm.com/download/win) and installed

Once GIT is installed you can visit the [Microsoft Visual Studio](https://www.visualstudio.com/en-us/docs/git/use-ssh-keys-to-authenticate) page to setup up a `SSH` key pair. The [Atlassian](https://confluence.atlassian.com/bitbucket/set-up-ssh-for-git-728138079.html) site also has some useful information about setting up for the git-bash shell This is usefull for the command shell or git-bash shell.