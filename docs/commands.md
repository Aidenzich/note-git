# Commands
## Basic Git Commands
| Usage | Command |
|-|-|
| Initialize a new Git repository | `git init` |
| Clone a repository from a remote source | `git clone <repository>` |
| Check the status of the working directory and staging area | `git status` |
| Add a file to the staging area | `git add <file>` |
| Add all new and modified files to the staging area | `git add .` |
| Commit changes with a message | `git commit -m <message>` |
| Commit changes and automatically stage all tracked, modified files before the commit | `git commit -m <message>` |
| Push commits to a remote repository | `git push` |
| Pull changes from a remote repository | `git pull` |
| Find out who wrote the file | `git blame <filename>` |

## Branching and Merging
| Usage | Command |
|-|-|
| List all branches | `git branch` |
| Create a new branch | `git branch <branch-name>` |
| Create a new branch and then checked out | `git checkout -b <branch-name>` |
| Delete a branch | `git branch -d <branch-name>` |
| Switch to a branch | `git checkout <branch-name>` |
| List remote barnches | `git branch -r` |
| List all local & remote branches | `git branch -a` |
| Merge a branch into the current branch | `git merge <branch-name>` |
| Change a branch name | `git checkout <old-name>` then, <br> `git branch -m <new-name>` |

## Undoing Changes
| Usage | Command |
|-|-|
| Undo a specific commit | `git revert <commit>` |
| Unstage a file | `git reset <file>` |
| Revert to a specific commit id | `git reset <commit-id>` |
| Save changes temporarily and switch to a clean working directory | `git stash` |
| Restore changes from the most recent stash | `git stash pop` |

## Show log histories
| Usage | Command |
|-|-|
| Viewing the commit history | `git log` |
| Viewing the reflog |  `git reflog` or `git log -g` |

## Remote 
| Usage | Command |
|-|-|
| Manage the set of repositories ("remotes") whose branches you track. | `git remote` |
| Check remote as HTTPS or SSH | `git remote -v` <br> `git remote --verbose` |
| Download contents from a remote repository | `git fetch <repository>`  |
| Fetch all branches from all remotes  | `git fetch -all <repository>`  |

## Show changes
| Usage | Commands |
|-|-|
| View changes between the `working tree` and `Staging` | `git diff` |
| Specific on a file | `git diff <filepath>` |
| View changes between the `Staging` and commited `commit` | `git diff --cached` |
| Display only changed file name | `git diff --name-only` |

### Select only changed files that match condition
```bash
git diff --diff-filter=<condition>
```

| Conditions | Description |
|-|-|
| `A` | Added |
| `C` | Copied |
| `D` | Deleted |
| `M` | Modified |
| `R` | Renamed |
| `T` | Have their type (mode) changed |
| `U` | Unmerged |
| `X` | Unknown |
| `B` | Have had their pairing Broken |
| `*` | All-or-none |
- Any **combination** of the filter characters may be used. e.g. 
    ```bash
    git diff --diff-filter=AD
    ```
- These upper-case letters can be downcased to **exclude**. e.g.
    ```bash
    git diff --diff-filter=ad
    ```
## Options of git reset
- **Options**
    | Options | Description | Working Directory | Staging | Local Repository |
    |-|-|-|-|-|
    | `--soft`  | Only reset the head to `<commit>` | ☓ | ☓ | ✓ |
    | `--mixed` | Default. Resets the staging and the head to `<commit>`. | ☓ | ✓ | ✓ |
    | `--hard`  | Any changes to tracked files in the working tree since `<commit>` are discarded.  | ✓ | ✓ | ✓ |
- **Examples**
    - Undo a commit
        ```
        git reset HEAD~
        git reset --soft HEAD^
        git reset --soft HEAD\^   # zsh might need to escape `^`
        ```
    - Fall back to a historical commit
        ```
        git reset --hard <commit-id>
        git push -f
        ```

## Others
### git ls-tree
```
git ls-tree [-d] [-r] [-t] [-l] [-z]
	    [--name-only] [--name-status] [--full-name] [--full-tree] [--abbrev[=<n>]]
	    <tree-ish> [<path>…​]
```
- Usage
    ```
    git ls-tree -r --name-only HEAD
    ```

| Options | Description |
|-|-|
| `-d` | show only the named tree entry itself, not it's children |
| `-r` | recurse into sub-tree |
| `-t` | show tree entries even when going to recurse them |
| `--name-only` | Show only names of changed files. |

## TODO
- [x] git diff --name-only --diff-filter=U
- [ ] git checkout <branchname> && git cherry-pick <commitid>
- [ ] git whatchanged --since='2 weeks ago'
