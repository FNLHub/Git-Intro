# Introduction to Git

Sign-up for [GitHub.com](https://github.com/join?source=header-home)

## Create a repository (repo)
[GitHub create a repo](https://help.github.com/articles/create-a-repo/)

## Basic Git commands

```git
git
git help tutorial
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
>git config --global user.name "Your Name Comes Here"
>git config --global user.email you@yourdomain.example.com
>```

#### Saving your GitHub password with Git

##### wincred (GUI)
>[Windows]
>```git
>git config --global credential.helper wincred
>```

##### Cache 
> [Windows, Linux & Mac]
>Turn on the credential helper so that Git will save your password in memory for some time. 
>By default, Git will cache your password for 15 minutes.
># Set git to use the credential memory cache
>
>```git
>git config --global credential.helper cache
>```

> To change the default password cache timeout
># Set the cache to timeout after 1 hour (setting is in seconds):
>```git
>git config --global credential.helper 'cache --timeout=3600'
>```

#### Make a directory to host your repository

> #### `[Windows]`
>``` cmd
> mkdir Repository\CosFNL\GitIntro
>```
>

> #### `[Linux & Mac]`
>
>```cmd
>mkdir -p ~/Repository/CosFNL/GitIntro
>```

> #### `[Windows]`

```cmd
cd Repository\CosFNL\GitIntro
```

> #### `[Linux & Mac]`

```cmd
cd Repository/CosFNL/GitIntro/
```

> #### `[Windows, Linux & Mac]`

```git
git init

Initialized empty Git repository...
```

```git
git add Readme.md
```

```git
git commit -m "First commit"

[main (root-commit) 873e7b8] First commit
 1 file changed, 117 insertions(+)
 create mode 100644 Readme.md
```

```git
git remote add origin https://github.com/CosFNL/GitIntro.git
git push -u origin main


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

TODO: Finish this repo...
