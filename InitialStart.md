# Initial Setup

There are some new tools to begin using and some old tools to begin using in new ways.  Most of the top ten or twenty searches in **Stack Overflow** are for **Git** related questions, this is new for everybody.

## Essential Tooling

The following tools are required to be installed and configured.

### Visual Studio 2017

The **Visual Studio** tools required to use **GIT** are installed as part of the core install, there is nothing to add or update here.  On the other hand, if you are using **VS2015** or earlier you will need to add extensions, it is assumed you are using **VS2017** and you are on your own otherwise.

### GIT + LFS

Although **Visual Studio** installs a copy of **GIT** it does not support _Large File Storage (LFS)_.  [Download GIT](https://git-scm.com/download/win) and install it with all the default options (next, next, etc.).  When the progress bar completes and before you click _Finish_, check the _Launch Git Bash_ and clear (or not) the _View Release Notes_ check.  This will launch a command prompt where you will complete the configuration.  **Be advised, this is a \*nix like BASH window and will behave different than a Windows Command window.**  In the window type (or copy and paste) the following: replacing the `{username}` with your name as it appears in you email address and the `{email}` with your full **CaseWare** email.  Be sure to include the double quotes (`"`).  

```bash
git config --global user.name "{username}"
git config --global user.email "{email}"
git config --global core.editor "notepad"
```

#### Example GIT Configuration

```bash
git config --global user.name "walt.speelman"
git config --global user.email "walt.speelman@caseware.com"
git config --global core.editor "notepad"
```

The last line of the shell command configures **Git** to use **NotePad** as the default editor, without this line **Git** will use **VIM**.  See the optional section below for configuring other editors.  Should you end up in a **VIM** windows the following will exit: `<Esc>:q!`.

## Options

The following tools may make your life easier (or more complicated), use at your own discretion.

### Command Windows

> Console is the new UI.

There are lots of alternate command windows, my current preference is [**PowerShell 6**](https://github.com/PowerShell/Powershell) and the [Posh Git](https://github.com/dahlbyk/posh-git) module.  [Chocolatey](https://chocolatey.org/) is also useful if you use a lot of console. 

### UI Tools

There are several UI tools that can help with git.

- [Tortoise GIT](https://tortoisegit.org/) provides an **Windows File Explorer** interface with icon overlays and right click extensions. If you already have windows explorer extensions installed (Google Drive, OneDrive, etc.), there is an undocumented limit on the number of icon overlays that can be used at once.  To use the Tortoise Overlays disable the other extensions.
- [Source Tree](https://www.sourcetreeapp.com/) provides an alternate UI, initial setup requires a [BitBucket](https://bitbucket.org/) account, which can be setup for free.

### VIM (or another advanced text editor)

**Git** defaults to using **VIM**, this likely will not be an issue if you are using either **Visual Studio** or one of the above UI tools, but you can change the default text editor that **Git** launches.

Here is a list of options, I'm sure you have a favorite:

- [NotePad++](https://notepad-plus-plus.org/)
- [NotePad2](http://www.flos-freeware.ch/notepad2.html)
- [GVIM](https://www.vim.org/download.php)

Some guidelines on picking a good editor for **Git**:

- it should be light weight and launch fast
- it does not need to handle large files
- it needs to be able to run multiple instances
- you should be proficient in it's use, or be willing to become so

Once you've downloaded and installed the editor of your choice you can configure **Git** to use it as the default editor with the following:

```bash
git config --global core.editor "{full path to editor}"
```

#### Example Editor Configuration

```bash
git config --global core.editor "'/C/Program Files/Notepad++/notepad++.exe'"
```

**Important** things to note about the path string.

- The path in the `config` file is both double and single quoted (`"'blah'"`)
- The path separator is a forward slash, not the **Windows** backslash
- The root drive is prefixed with a forward slash (`/`) and the semi-colon (`:`) has been removed

### GVFS

In order to work with very large files systems **Microsoft** developed a virtual file system, it was deemed easier to develop a virtual file system then break the **Git** repository for the **Windows** OS up.  It use to be _Git Virtual File System_ but it turns out it was also _Gnome VFS_ so **Microsoft** changed it to _VFS for GIT_ (and that just rolls off the tongue).  Download it [here](https://github.com/Microsoft/VFSForGit/releases/download/v1.0.18297.1/SetupGVFS.1.0.18297.1.exe) and install.
