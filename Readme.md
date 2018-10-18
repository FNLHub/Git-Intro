# GitIntro

Signup for GitHub.com

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

### Command Prompt/Terminal

#### Configure Git

> [Windows, Linux & Mac]
>```git
>git config --global user.name "Your Name Comes Here"
>git config --global user.email you@yourdomain.example.com
>```

#### Make a directory to host your repository

> [Windows]
>``` cmd
> mkdir Repository\CosFNL\GitIntro
>```
>

> Linux & Mac
>
>```cmd
>mkdir -p ~/Repository/CosFNL/GitIntro
>```

> [Windows]

```cmd
cd Repository\CosFNL\GitIntro
```

> [Linux & Mac]

```cmd
cd Repository/CosFNL/GitIntro/
```

> [Windows, Linux & Mac]

```git
git init

Initialized empty Git repository...
*[HTML]: HyperText Markup Language

I just love **bold text**.


```

> #### The quarterly results look great!
>
> - Revenue was off the chart.
> - Profits were higher than ever.
>
> *Everything* is going according to **plan**.

> Dorothy followed her through many of the beautiful rooms in her castle.
>
>> The Witch bade her clean the pots and kettles and sweep the floor and keep the fire fed with wood.

```git
git add Readme.md
```

```csharp
<h1>test</h1>
public void ()
{
    //test
}
//comment
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