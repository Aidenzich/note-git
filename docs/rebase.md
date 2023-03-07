# git rebase
| Command | Description |
|-|-|
| git rebase <base> | Rebase the current branch onto <base>. <base> can be a commit ID, branch name, or tag name. |
| git rebase -i <base> | Interactive rebase. Allows you to selectively edit, reorder, or delete commits from the branch being rebased. |
| git rebase --abort | Abort a rebase that is currently in progress.|
| git rebase --continue | Continue a rebase after resolving conflicts. |
| git rebase --skip | Skip a commit that has conflicts during a rebase. |
| git rebase -p | Preserve merges in the rebase. |
| git rebase --onto <newbase> <oldbase> <branch> | Rebase the commits in <branch> that come after <oldbase> and before the current branch's HEAD onto <newbase>. This is useful if you want to move a series of commits from one branch to another. |
| git rebase -s <strategy> | Use the specified merge strategy during the rebase. For example, -s recursive uses the default recursive merge strategy. Other options include resolve, octopus |

## git flow
![gitflow](/assets/rebase_gitflow.svg)

## Reference
>  There's nothing "clean" or "tidy" about a rebased history. It's generally filthy and IMHO awful because you have no idea what really went on. The "cleanest" Git history is the one that actually occurred. - [Marnen Laibow-Koser](https://stackoverflow.com/users/109011/marnen-laibow-koser)
- [gitflow source](https://www.atlassian.com/git/tutorials/merging-vs-rebasing)
- [when-do-you-use-git-rebase-instead-of-git-merge](https://stackoverflow.com/questions/804115/when-do-you-use-git-rebase-instead-of-git-merge)
