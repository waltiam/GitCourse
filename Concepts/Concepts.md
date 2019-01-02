# Concepts

**Git** is a distributed source control system.  That means that each user has a complete version of the source on their local machine.  Additionally, there is usually a gold or master version on a remote server, it is from this repository that the installable version of the software is made.  Be aware, the genealogy of **Git** has introduced identical concepts with different names and different concepts with identical names, context is very important in understanding the differences or similarities.

## Initial Setup

There is some setup to perform before the exercises can be completed.

* [Initial Setup](./InitialStart.md)

## Repositories

A **Git** _Repository_ or _repo_ is a self contained complete source control system.

Within the **Git** structure there are four basic areas:

1. Workspace
2. Stash, not available from **Visual Studio**
3. Index, AKA 'cache', 'staging area' or 'staged files'
4. Local Repository

> A _Bare Repo_ is a **Git** _repo_ that has no workspace, stash or index.  It is intended for use on servers where no actual changes are performed on the files and therefore these areas are not needed.  

### Exercise - Create a Local Repository

* [Create a Local Repository](./Repository.md)

Creating a local repository sets up the **Git** structures needed.

### Exercise - Staging Files

* [Adding Files to a Repo](./AddingFilesToRepo.md)

### Exercise - Committing Staged Files

### Exercise - Creating a Project With Visual Studio

### Exercise - Cloning a Repository

## Repositories - Advanced

### Exercise - Stashing Files
