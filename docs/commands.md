# Commands

## git ls-tree
```
git ls-tree [-d] [-r] [-t] [-l] [-z]
	    [--name-only] [--name-status] [--full-name] [--full-tree] [--abbrev[=<n>]]
	    <tree-ish> [<path>…​]
```
- Usage
    ```
    git ls-tree -r --name-only HEAD
    ```
- Arguments
  - `-d` show only the named tree entry itself, not it's children.
  - `-r` recurse into sub-tree.
  - `-t` show tree entries even when going to recurse them.

## git fetch
```
git fetch <options> <repository> 
```
- `--all` Fetch all remotes.
## git checkout
- Create a new branch and then checked out
```
git checkout -b <branch>
```
- Switch to a branch in local repo
```
git checkout <branch>
```

## git branch
- To see local branches
```
git branch
```
- To see remote branches
```
git branch -r
```
- To see all local and remote branches
```
git branch -a
```
- Delete a local branch
```
git branch -d <branch> 
```

## git reset
- Undo a commit
```
git reset HEAD~
git reset --soft HEAD^
git reset --soft HEAD\^   # zsh might need to escape `^`
```
- Reverting to a specific commit
```
git reset --hard <commit-id>
```
## git fall back to a historical commit
```
git reset --hard <commit-id>
git push -f
```
## git log
- Viewing the commit history
```
git log
```
- Viewing the reflog, can be seen as `git reflog` command
```
git log -g
```

## git blame
- Find out who wrote the file
```
git blame <filename>
```

## git remote
- You can check if you have added the remote as HTTPS or SSH using:
```
git remote -v
```

## Change the branch name
> With a `-m` or `-M` option, <oldbranch> will be renamed to <newbranch>. If <oldbranch> had a corresponding reflog, it is renamed to match <newbranch>, and a reflog entry is created to remember the branch renaming. If <newbranch> exists, -M must be used to force the rename to happen.
```
git checkout <old-name>
git branch -m <new-name>
```

## Git add or `-a`
- git commit -a automatically stage all tracked, modified files before the commit 
- If you think the git add stage of the workflow is too **cumbersome(繁瑣)**, Git allows you to skip that part with the -a option. 
- This basically tells Git to run git add on any file that is "tracked" 


# TODO
- [ ] git checkout <branchname> && git cherry-pick <commitid>
- [ ] git whatchanged --since='2 weeks ago'
- [ ] git diff --name-only --diff-filter=U