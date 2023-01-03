# Git Settings
## Fix git command output is in editor(vim) to terminal output
```
git --no-pager branch
```
or 
```
git config --global pager.branch false
git config --global pager.tag false
```