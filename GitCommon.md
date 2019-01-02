# Useful commands

## GIT

### clone

> clone a repository from another user

```bash
git remote add otherUser git://path/to/coworkers/repo.git
git fetch otherUser
git checkout --track otherUser/branch
```

### [checkout](https://git-scm.com/docs/git-checkout)

> create and checkout a local branch

```bash
git checkout -b {branch}
```

> copy a file across local branches, performed from the working branch

```bash
git checkout {branch containing files} {name of file}
```

**Example:** this will copy the _packages.config_ file from the _development_ branch to the _development-ui_ branch

```bash
git checkout development-ui
git checkout development -- packages.config
```

### [commit](https://git-scm.com/docs/git-commit)

> append a commit, this appends the currently staged files to the last commit on this branch

```bash
git commit --amend --no-edit
```

### log

> show the commits in the current branch

```bash
$ git log -3
commit 87c6328fd6a9afa4e647f8551cd86f942c05f5d5
Author: walt speelman <walt.speelman@talentmap.com>
Date:   Thu Jul 6 11:50:23 2017 -0400

    getting this running ...

commit 1fefa75c8d614737f55f9c674683925fabd8942a
Author: walt speelman <walt.speelman@talentmap.com>
Date:   Thu Jul 6 10:49:52 2017 -0400

    WIP adding multiple question types

commit a3eeae617234d3f4f6748a64e4116324305a68cb
Author: walt speelman <walt.speelman@talentmap.com>
Date:   Thu Jul 6 09:52:53 2017 -0400

    working with the color picker

$ git checkout -b poc-precomponents a3eeae61
Switched to a new branch 'poc-precomponents'
```

### remote

> update the local repository, `prune` removes branches from the local repository that do not exist on the remote repository

```bash
git remote update origin --prune
```

---

### remove

> removes a tree _{folder}_ recursively from the tracked files, add `-n` to dry run the task first

```bash
git rm -r -f {folder}
```

> the `rm` command can also be used in file matching

```bash
git rm -r {glob pattern}
```

**Example:** to remove all *.user files in the tree

```bash
git rm -r *.user
```

``

## BASH

> delete all the _bin_ and _obj_ folders from a tree starting here, these are the VS build artifact directories

```bash
find . -iname "bin" -o -iname "obj" | xargs rm -rf
```

---
> search for a {string} in the {glob} patterned files

```bash
grep -r --include={glob} {string} *
```

**EXAMPLE:** 

```bash
grep -r --include=*.cs "TalentGateWebContext" *
```
