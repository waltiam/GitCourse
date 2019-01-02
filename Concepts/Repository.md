# Repositories

A **Git** _Repository_ or _repo_ is a self contained complete source control system.

## Create an Empty Repository

- The folder name selected cannot exist, it is not possible to create a **Git** _repo_ from **Visual Studio** from an existing folder.
- To create a **Git** _repo_ from an existing folder with files either **Tortoise** or the command line need to be used, see below.

1. From **Visual Studio** launch the _Team Explorer_

![Launch Team Explorer](/img/LaunchingTeamExplorer.PNG)

2. Within the _Team Explorer_ pane click the _Add_ link

![Add Link](/img/NewLocalGitRepositoryLink.PNG)

3. Type or browse (use the '...') to the folder to want to create and click the _Create_ button

![Create Local Git](/img/LocalGitRepository.PNG)

1. To see the effect of this right click on the new repository and select _Open in File Explorer_

![Open Repository](/img/OpenRepositoryInExplorer.PNG)

5. This opens an _Explorer_ window
   - The `.git` is a hidden system folder and should not be modified, it is shown here only to demonstrate it's presence.  Modifying this folder or the contents of this folder may corrupt the local **Git** repository.  
   - The `.gitignore` is a text file which contains files to not include as source, by default **Git** will not include the `.git` in the source.
     - A complete discussion on the formatting of the `.gitignore` file can be found [here](https://git-scm.com/docs/gitignore).
   - The `.gitattributes` is a text file which contains instructions to **Git** as specialized file handling instructions.
   - The two text files can be edited and are both part of the source control.
   - The blue plus sign on the text files are _icon overlays_ available because **Tortise Git** is installed.

![Local Repository](/img/LocalRepository.PNG)

## Create a Repository from the Command Line

Open a command prompt (**Bash**, **Command** or **PowerShell**) navigate to the folder that you wish to create a _repo_ in:

```shell
git init
```

- This will initialize the folder with a `.git` folder and nothing else.
- `.gitignore` and `.gitattributes` files need to be created manually if required
- The folder does not need to empty.
- This will not change the state of an existing _repo_, (it will update templates)
- [Full discussion](https://git-scm.com/docs/git-init)

## Create a Repository with Tortoise

Right click in the folder that you wish to create the _repo_ in and select _Git Create repository here ..._.

![Create a Tortoise Git Repo](/img/NewLocalRepositoryTortoise.PNG)

Select _OK_ leaving the check-box unchecked.

![Ok To Create](/img/okToCreate.PNG)
