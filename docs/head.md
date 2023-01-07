# What is detached HEAD?  
## What is `HEAD`?
In Git, the `HEAD` refers to the current branch reference, which is the `current branch`. When you switch branches with `git checkout`, the `HEAD` reference is updated to point to the current branch. You can think of it as the `current branch pointer`.
The `HEAD` reference is not a `branch` itself, but rather it points to the `branch` that you are currently on. When you create a new `commit`, the `commit` is added to the current `branch` and the `HEAD` reference is **updated to point to the new `commit`**.