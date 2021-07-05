# Introduction to Git

Sign-up for [GitHub.com](https://github.com/join?source=header-home)

## Create a repository (repo)
[GitHub create a repo](https://help.github.com/articles/create-a-repo/)

## Basic Git commands

```git
> git
> git help tutorial
```

git command | Definition
--- | ---
`clone` | Clone a repository into a new directory
`init` | Create an empty Git repository or reinitialize an existing one
`add` | Add file contents to the index
`status` | Show the working tree status
`commit` | Record changes to the repository
`fetch` | Download objects and refs from another repository
`pull` | Fetch from and integrate with another repository or a local branch
`push` | Update remote refs along with associated objects

### Command Prompt/Terminal

#### Configure Git

> [Windows, Linux & Mac]
>```git
>> git config --global user.name "Your Name Comes Here"
>> git config --global user.email you@yourdomain.example.com
>```

#### Saving your GitHub password with Git

##### wincred (GUI)
>[Windows]
>```git
>> git config --global credential.helper wincred
>```

##### Cache 
> [Windows, Linux & Mac]
>Turn on the credential helper so that Git will save your password in memory for some time. 
>By default, Git will cache your password for 15 minutes.
># Set git to use the credential memory cache
>
>```git
>> git config --global credential.helper cache
>```

> To change the default password cache timeout
># Set the cache to timeout after 1 hour (setting is in seconds):
>```git
>> git config --global credential.helper 'cache --timeout=3600'
>```

#### Make a directory to host your repository

> #### `[Windows]`
>``` cmd
>> mkdir Repository\CosFNL\GitIntro
>```
>

> #### `[Linux & Mac]`
>
>```cmd
>> mkdir -p ~/Repository/CosFNL/GitIntro
>```

> #### `[Windows]`

```cmd
> cd Repository\CosFNL\GitIntro
```

> #### `[Linux & Mac]`

```cmd
> cd Repository/CosFNL/GitIntro/
```

> #### `[Windows, Linux & Mac]`

```git
> git init

Initialized empty Git repository...
```

```git
> git add Readme.md
```

```git
> git commit -m "First commit"

[main (root-commit) 873e7b8] First commit
 1 file changed, 117 insertions(+)
 create mode 100644 Readme.md
```

```git
> git remote add origin https://github.com/CosFNL/GitIntro.git
> git push -u origin main


Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Delta compression using up to 8 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 1.21 KiB | 1.21 MiB/s, done.
Total 3 (delta 0), reused 0 (delta 0)
remote:
remote: Create a pull request for 'main' on GitHub by visiting:
remote:      https://github.com/CosFNL/GitIntro/pull/new/main
remote:
To https://github.com/CosFNL/GitIntro.git
 * [new branch]      main -> main
Branch 'main' set up to track remote branch 'main' from 'origin'.

```

## Using Git for collaboration

## Git Download

## Resources
[Pro Git Book](https://git-scm.com/book/en/v2)

[Git Notes For Professionals](https://books.goalkicker.com/GitBook/GitNotesForProfessionals.pdf)

### Connect to **COS FNL** repository

https://github.com/CosFNL/GitIntro.git

## .ssh key

[SSH Key](https://docs.github.com/en/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)

[Add SSH Key to GitHub](https://docs.github.com/en/github/authenticating-to-github/adding-a-new-ssh-key-to-your-github-account)

### Generating a new SSH key

Paste the text below, substituting in your email address.
  ```shell
  $ ssh-keygen -t ed25519 -C "<em>your_email@example.com</em>"
  ```  
  
  **Note:** If you are using a legacy system that doesn't support the Ed25519 algorithm, use:
  ```shell
   $ ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
  ```
  
### Make sure you're running PowerShell as an Administrator
```powershell 
Set-Service ssh-agent -StartupType Automatic
Start-Service ssh-agent
Get-Service ssh-agent
```

## Advanced Git commands
### [Branching & Merging](https://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging)

> #### `[Windows, Linux & Mac]`
> This workflow is primary branching and merging to prevent code loss and help with development vs. production workflows.

iss53 is the new branch we want to work with.
```git 
> git checkout -b iss53
``` 
##### Shorthand for
```git
> git branch iss53
> git checkout iss53
```

Make your changes to the file and commit them.

```git
> git commit -a -m 'Finish making x change'
```

Merge the changes back to main branch

```git
> git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.

> git merge iss53
Updating e46f478..20c8f8b
Fast-forward
 Readme.md | 16 +++++++++++++++-
 1 file changed, 15 insertions(+), 1 deletion(-)
 ```

 ```git
 git branch -d iss53
 ```

### [Reset/Revert](https://git-scm.com/book/en/v2/Git-Tools-Reset-Demystified)
If you made a mistake and need to revert to the previous commit.
Avoid doing HARD reset and always create a new branch when working on a project to prevent major issues.

git command | Definition
--- | ---
[`log`](https://www.git-scm.com/docs/git-log) | Show commit logs
[`reflog`](https://git-scm.com/docs/git-reflog) | Manage reflog (reference logs) information
[`reset`](https://git-scm.com/docs/git-reset) | Reset current HEAD to the specified state

### Command Prompt/Terminal

#### reflog - referance logs
The reflog will list the reference commit headers, which will use to revert or reset the project.


> #### `[Windows, Linux & Mac]`
> Show the HEAD logs with one line with basic graph pointers. Play around with the various options to see what suits your workflow.

```git
git log --oneline --graph
```

Git reset options

 git reset options | Definition
--- | ---
`--soft` | Does not touch the index file or the working tree at all (but resets the head to \<commit>, just like all modes do). This leaves all your changed files "Changes to be committed", as git status would put it.
`--mix` | Resets the index but not the working tree (i.e., the changed files are preserved but not marked for commit) and reports what has not been updated. This is the default action.
`--hard` | Resets the index and working tree. Any changes to tracked files in the working tree since \<commit> are discarded.

Git HEAD - ref that points to the tip (latest commit) of a branch.

 Git hard Reset HEAD
```git
git reset --hard HEAD       (going back to HEAD)
git reset --hard HEAD^      (going back to the commit before HEAD)
git reset --hard HEAD~1     (equivalent to "^")
git reset --hard HEAD~2     (going back two commits before HEAD)
```

#### Example
Let's revert to a particular HEAD ref of f6e5064 from our current head 3303307.

```git
git reset --hard f6e5064
```

### NOTE: Git only garbage collects after a month (by default). So you can recover your files if a --hard reset was done on the same machine.

#### Example
We lost files from f6e5064 due to hard reset. Going back to 3303307

```git
git reset --hard 3303307
```

TODO: Finish this repo...
