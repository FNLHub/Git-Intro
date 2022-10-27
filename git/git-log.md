# Git Log

git-log - Show commit logs


## [-S`<string>`](https://www.git-scm.com/docs/git-log#Documentation/git-log.txt--Sltstringgt)

>Look for differences that change the number of occurrences of the specified string (i.e. addition/deletion) in a file. Intended for the scripter’s 

Example
```
git log -S'XXXXXXXXXXXXX012' -p
```

## [-G`<regex>`](https://www.git-scm.com/docs/git-log#Documentation/git-log.txt--Gltregexgt)

>Look for differences whose patch text contains added/removed lines that match <regex>.

Example
```
git log -G'XXXXXXXXXXXXX012' -p --all
```

## Differences between -S`<string>` and -G`<regex>`
>While git log -G"frotz\(nitfol" will show this commit, git log -S"frotz\(nitfol" --pickaxe-regex will not (because the number of occurrences of >that string did not change).


## ⭐ Resources
- [git-log](https://www.git-scm.com/docs/git-log)