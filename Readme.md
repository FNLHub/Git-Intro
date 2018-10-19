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

[master (root-commit) 873e7b8] First commit
 1 file changed, 117 insertions(+)
 create mode 100644 Readme.md
```

```git
git remote add origin https://github.com/CosFNL/GitIntro.git
git push -u origin master


Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Delta compression using up to 8 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 1.21 KiB | 1.21 MiB/s, done.
Total 3 (delta 0), reused 0 (delta 0)
remote:
remote: Create a pull request for 'master' on GitHub by visiting:
remote:      https://github.com/CosFNL/GitIntro/pull/new/master
remote:
To https://github.com/CosFNL/GitIntro.git
 * [new branch]      master -> master
Branch 'master' set up to track remote branch 'master' from 'origin'.

```

## Using Git for collaboration

## Git Download

### Connect to **COS FNL** repository

https://github.com/CosFNL/GitIntro.git

…or create a new repository on the command line
echo "# GitIntro" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/CosFNL/GitIntro.git
git push -u origin master

…or push an existing repository from the command line
git remote add origin https://github.com/CosFNL/GitIntro.git
git push -u origin master

…or import code from another repository
You can initialize this repository with code from a Subversion, Mercurial, or TFS project.
