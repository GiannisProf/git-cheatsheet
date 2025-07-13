##  Undoing Mistakes

### Undo unstaged changes (reset file)
```bash
git checkout -- path/to/file.txt
```

### Unstage a staged file
```bash
git reset path/to/file.txt
```

### Reset entire repo to last commit
```bash
git reset --hard HEAD
```


##  Stashing Changes

### Save uncommitted changes
```bash
git stash
```

### List stashes
```bash
git stash list
```

### Apply last stash
```bash
git stash apply
```

### Apply and drop stash
```bash
git stash pop
```


##  Working with Remotes

### Add new remote
```bash
git remote add upstream git@github.com:<user>/<repo>.git
```

### Fetch changes from upstream
```bash
git fetch upstream
```

### Merge upstream changes into local main
```bash
git checkout main
git merge upstream/main
```


##  Viewing History & Logs

### View commit log
```bash
git log --oneline --graph --all
```

### Show changes in last commit
```bash
git show
```

### See changes in working directory
```bash
git status
git diff
```

---

## Common Shortcuts

| Command                        | What It Does                     |
|--------------------------------|------------------------------------|
| `git checkout -b <branch>`    | Create and switch to new branch   |
| `git pull --rebase`           | Pull changes & rebase local work  |
| `git push origin --delete <branch>` | Delete remote branch          |
| `git clean -fd`               | Remove untracked files & folders  |