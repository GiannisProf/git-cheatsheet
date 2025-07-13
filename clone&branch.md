##  Clone GitHub Repo to Local Machine (via SSH)

```bash
git clone git@github.com:<username>/<repo>.git
```

---

##  Branching Workflow

### List branches
```bash
git branch
```

### Create a new branch
```bash
git checkout -b feature/my-feature
```

### Switch branches
```bash
git checkout main
```

### Delete a branch
```bash
git branch -d feature/my-feature
```

### Push branch to GitHub
```bash
git push -u origin feature/my-feature
```

##  Merging & Rebasing

### Merge branch into current branch
```bash
git merge feature/my-feature
```

### Rebase current branch onto main
```bash
git rebase main
```

---

##  Syncing with Remote

### Pull latest changes
```bash
git pull origin main
```

### Fetch all branches (but don’t merge)
```bash
git fetch
```

### See differences between local & remote
```bash
git status
git diff
```

---

##  Staging & Committing

### Stage all changes
```bash
git add .
```

### Stage specific file
```bash
git add path/to/file.txt
```

### Commit staged changes
```bash
git commit -m "Your commit message"
```

---
