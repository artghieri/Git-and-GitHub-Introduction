
## Git Cheat Sheet
#### This cheat sheet features the most important and commonly used Git commands for easy reference.

![a](https://user-images.githubusercontent.com/102708433/196017262-cc8d8ba0-210e-4161-9607-5bf34893b4d5.png)

![asda](https://user-images.githubusercontent.com/102708433/196017260-752c6ad0-6a0b-46da-9b7b-a92b2fa130c1.png)

---

### SETUP
**Configuring user information used across all local repositories**

> **Set the name that will be attached to your commits and tags**
```
git config --global user.name your_name
```

> **Set the e-mail address that will be attached to your commits and tags**
```
git config --global user.email you@example.com
```

> **Enable some colorization of Git output.**
```
git config --global color.ui auto
```

---

### SETUP & INIT
**Configuring user information, initializing and cloning repositories**

> **Create a new local repository.**

```
git init project_name
```

> **Downloads a project with the entire history from the remote repository.**
```
git clone url
```

---

### STAGE & SNAPSHOT
**Working with snapshots and the Git staging area**

> **Displays the status of your working directory. Options include new, staged, and modified files**
```
git status
```

> **Add a file to the staging area**
```
git add file
```

>  **Revert your repository to a previous known working state**
```
git reset file
```

> **Show changes between working directory and staging area**
```
git diff
```

> **Shows any changes between the staging area and the repository**
```
git diff --staged
```

> **Create a new commit from changes added to the staging area**
```
git commit -m "descriptive message"
```

---

### BRANCH & MERGE
**Isolating work in branches, changing context, and integrating changes**

> **List all local branches in repository. With -a: show all branches (with remote).**
```
git branch -a
```

> **Create new branch, referencing the current HEAD**
```
git branch name
```

> **Remove selected branch, if it is already merged into any other. *-D* instead of *-d* forces deletion**
```
git branch -d name
```

> **Switch working directory to the specified branch. With -b: Git will create the specified branch if it does not exist** 
```
git checkout -b name
```

> **Discard changes in working directory. This operation is unrecoverable**
```
git checkout -- file
```

> **Join specified [from name] branch into your current branch (the one you are on currently)**
```
git merge branch
```

---

### INSPECT & COMPARE
**Examining logs, diffs and object information**

> **Show the commit history for the currently active branch**
```
git log
```

> **List commit history of current branch. -n count limits list to last n commits**
```
git log -n count
```

> **An overview with reference labels and history graph. One commit per line**
```
git log --oneline --graph --decorate
```

> **Show the commits on branchA that are not on branchB**
```
git log branchB..branchA
```

> **Show the commits that changed file, even across renames**
```
git log --follow file
```

> **Show the diff of what is in branchA that is not in branchB**
```
git diff branchB...branchA
```

> **Show any object in Git in human-readable format**
```
git show SHA
```

> **List commits that are present on the current branch and not merged into ref. A ref can be a branch name or a tag name**
```
$ git log ref..
```

> **List commit that are present on ref and not merged into current branch**
```
git log ..ref
```

> **List operations (e.g. checkouts or commits) made on local repository**
```
git reflog
```

---

### TRACKING PATH CHANGES
**Versioning file removes and path changes**

> **Delete the file from project and stage the removal for commit**
```
git rm file
```

> **Change an existing file path and stage the move**
```
git mv existing-path new-path
```

> **Show all commit logs with indication of any paths that moved**
```
git log --stat -M
```

---

### TAGGING KNOW COMMITS
**Git has the ability to tag specific points in a repository’s history as being important**

> **List all tags**
```
git tag
```

> **Create a tag reference named name for current commit. Add commit sha to tag a specific commit instead of current one**
```
git tag name commit sha
```

> **Create a tag object named name for current commit**
```
git tag -a name commit sha
```

> **Remove a tag from local repository**
```
git tag -d name
```

---

### SHARE & UPDATE
**Retrieving updates from another repository and updating local repository**

> **Add a git URL as an alias**
```
git remote add alias url
```

> **Fetch down all the branches from that Git remote**
```
git fetch alias
```

> **Merge a remote branch into your current branch to bring it up to date**
```
git merge alias/branch
```

> **Transmit local branch commits to the remote repository branch**
```
git push alias branch
```

> **fetch and merge any commits from the tracking remote branch**
```
git pull
```

> **Fetch changes from the remote, but not update tracking branches**
```
git fetch remote
```

> **Delete remote Refs that were removed from the remote repository**
```
git fetch --prune remote
```

> **Fetch changes from the remote and merge current branch with its upstream**
```
git pull remote
```

> **Push local changes to the remote. Use --tags to push tags**
```
git push --tags remote
```

> **Push local branch to remote repository. Set its copy as an upstream**
```
git push -u remote branch
```

---

### REWRITE HISTORY
**Rewriting branches, updating commits and clearing history**

> **Apply any commits of current branch ahead of specified one**
```
git rebase branch
```

> **Clear staging area, rewrite working tree from specified commit**
```
git reset --hard commit
```

> **Switches the current branch to the target reference, leaving a difference as an uncommitted change**   
> **When --hard is used, all changes are discarded.**
```
git reset --hard target reference
```

> **Create a new commit, reverting changes from the specified commit. It generates an inversion of changes**
```
git revert commit sha
```

---

### TEMPORARY COMMITS
**Temporarily store modified, tracked files in order to change branches**

> **Save modified and staged changes**
```
git stash
```

> **List stack-order of stashed file changes**
```
git stash list
```

> **Write working from top of stash stack**
```
git stash pop
```

> **Discard the changes from top of stash stack**
```
git stash drop
```

---

### IGNORING PATTERNS
**Preventing unintentional staging or commiting of files**

> **Save a file with desired paterns as .gitignore with either direct string matches or wildcard globs**
```
logs/
*.notes
pattern*/
```

> **System wide ignore patern for all local repositories**
```
git config --global core.excludesfile file
```
