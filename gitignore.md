# Git Ignore (.gitignore)

## Added .gitignore after the fact

> [NOTE]
> 
> This does not remove the files from history or previous commits to the repository like GitHub.

For the files already committed to a remote git repository, you’ll need to unstage them, create a new commit and push to your remote git repository.

> [Windows, Linux & Mac] 
```git
git rm -r --cached .
git add -A
git status
git commit -am 'Removing ignored files'
```

### One-liner
```git
git rm -r --cached . && git add -A && git status && git commit -am 'Removing ignored files'
```

### [git-update-index](https://www.git-scm.com/docs/git-update-index) (alternative)

 Tell git to avoid writing the file to the working directory when reasonably possible, and treat the file as unchanged when it is not present in the working directory.

>Note: that not all git commands will pay attention to this bit, and some only partially support it.

Source: [SKIP-WORKTREE BIT](https://www.git-scm.com/docs/git-update-index#_skip_worktree_bit)

> [Windows, Linux & Mac]
> To
```git
git update-index --skip-worktree <file>
```


> [Windows, Linux & Mac]
>To Cancel/stop
```git
git update-index --no-skip-worktree <file>
```

> [Linux & Mac]
>
> xargs - or get windows alternative/WSL to this.
```git
git ls-files -z --ignored --exclude-standard | xargs -0 git rm -r --cached
git commit -am "Removing ignored files"
```

## ⭐ Resources
- [git-update-index](https://www.git-scm.com/docs/git-update-index)
- [SKIP-WORKTREE BIT](https://www.git-scm.com/docs/git-update-index#_skip_worktree_bit)
- [StackOverFlow](https://stackoverflow.com/questions/1274057/how-do-i-make-git-forget-about-a-file-that-was-tracked-but-is-now-in-gitignore)
