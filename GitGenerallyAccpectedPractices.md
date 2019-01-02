# GIT Generally Accepted Practices

## Why GIT?

To quote  [Microsoft&trade;](https://docs.microsoft.com/en-us/vsts/tfvc/comparison-git-tfvc?view=vsts#which-version-control-system-should-i-use):

_You should use Git for version control in your projects unless you have a specific need for centralized version control features in TFVC._

## 3rd Party Software

**Do not** check binary third party software into GIT.

**Do** manually store in a backed-up shared drive each version of commercial 3rd party tooling that is used.

> [Walt] Should the need arise to modify the source of 3rd party code, the code portion of the project should be copied from the 3rd party storage into the source tree.  It can then be added to GIT and version controlled as code.  Do not move sample files, example code, help files, etc. into the source tree.

> [Michel] No modifying source from 3rd party packages. In my humble opinion If the source has to be modified then it’s the wrong package.

**Do** prefer using a 3rd party package manager (NuGet, Paket, etc.).

**Do** clone 3rd party repositories and push them to private repositories.  `Fork` github OS projects or if they are desired locally prefer `git subtree` to `git submodule`.

> [Walt] Unless there is a concern that the binary distribution will go away or there is a customization on the source, it is best to leave 3rd party source code in its original repository.  A policy of refreshing the 3rd party repositories should be set when engaging the source code.

>[Walt] Consider posting changes to open-source projects as PR back the original project unless there is proprietary content.
Binary Files

**Do not** store binary files directly in GIT.

**Do** use GIT-LFS to store binary files.

> [Walt] ToDo: Define a list of binary files, the content of each check in should be reviewed for new file types.

## Build Artefacts

**Do not** store the build artefacts in GIT.  Any product that can be reproduced from a pull of the code at that point does not get added to the source control.
**Do** store build definitions in source control.

## Workflow

> [Walt] ToDo: Define a set of common workflows. [Example](https://therearellama.visualstudio.com/GIT-Workflows)

### Clone a remote repository

```ps1
git clone https://therearellama.visualstudio.com/_git/GIT-Workflows
```

### Add a 3rd Party Source

```ps1
git subtree add --squash --prefix=OpenMcdf https://github.com/ironfede/openmcdf.git master
```

## Tooling

### 2nd Party

#### Visual Studio

Visual Studio 2017 and 20:qw
15 have native support for GIT, there are addons for 2013.  I have not idea what, if any, support 2010 has for GIT.

#### PowerShell

Support for GIT in powershell is provided by a 3rd party module Posh GIT (https://github.com/dahlbyk/posh-git).

### 3rd Party

#### [GIT](https://git-scm.com)

It is advisable to install git for windows in addition to any UI based tooling that may support git.  There are features that are not well supported (lfs, branching, stashing, etc.) in the individual UI tools.

#### [Tortoise GIT](https://tortoisegit.org)

This adds icons and right click functionality from within windows explorer.

#### [Source Tree](https://www.sourcetreeapp.com)

This is a stand alone application, it seems to work only with 

## References and Reading

- [Git Strategizing: Branch, Commit, Review, and Merge](https://www.red-gate.com/simple-talk/dotnet/net-framework/git-strategizing-branch-commit-review-merge/)
- [5 Git Commands I Wish I'd Known About When I Started Coding](https://www.netguru.co/codestories/5-git-commands-i-wish-i-knew-about-when-i-started-coding)
- [Git Feature Branch Workflow](https://www.atlassian.com/git/tutorials/comparing-workflows/feature-branch-workflow)
- [When to Use Git Reset, Git Revert & Git Checkout](https://dev.to/neshaz/when-to-use-git-reset-git-revert--git-checkout-18je)
- [Git Merge vs Git Rebase]https://dev.to/neshaz/git-merge-vs-git-rebase-5134()
- [Git Cheat Sheet](https://www.git-tower.com/blog/git-cheat-sheet)
- [Git Cheatsheet](https://ndpsoftware.com/git-cheatsheet.html)

## NuGet Mirroring

[Why?](https://blog.maartenballiauw.be/post/2016/03/23/someone-broke-the-internet!-or-why-you-may-want-to-mirror-your-dependencies.html)
