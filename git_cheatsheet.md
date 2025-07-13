
# Git Cheat Sheet – Essential Commands for All Workflows

---

##  1. Initialize a Local Repo & Connect to GitHub

### Initialize Git in a folder
```bash
git init
```

### Set your username & email (global)
```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

---

##  2. Create & Add SSH Key (GitHub Authentication) (OPTIONAL)

### Check for existing SSH keys
```bash
ls -al ~/.ssh
```
Look for `id_rsa.pub` or `id_ed25519.pub`.

### Generate a new SSH key
```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```
*For older systems:*
```bash
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```
Press Enter to accept default file location. Set a passphrase if you want.

### Start SSH agent
```bash
eval "$(ssh-agent -s)"
```

### Add your SSH private key to agent
```bash
ssh-add ~/.ssh/id_ed25519
```

### Copy SSH public key to clipboard
```bash
cat ~/.ssh/id_ed25519.pub
```
Or on macOS:
```bash
pbcopy < ~/.ssh/id_ed25519.pub
```
Or on Windows (Git Bash):
```bash
clip < ~/.ssh/id_ed25519.pub
```

### Add key to GitHub
1. Go to **GitHub → Settings → SSH and GPG keys**
2. Click **New SSH key** → Paste key → Save.

### Test SSH connection
```bash
ssh -T git@github.com
```
Expected output:
```
Hi <username>! You've successfully authenticated.
```

### Set GitHub remote using SSH
```bash
git remote add origin git@github.com:<username>/<repo>.git
```

---

##  3. Clone GitHub Repo to Local Machine (via SSH)

```bash
git clone git@github.com:<username>/<repo>.git
```

---

##  4. Branching Workflow

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

---

##  5. Merging & Rebasing

### Merge branch into current branch
```bash
git merge feature/my-feature
```

### Rebase current branch onto main
```bash
git rebase main
```

---

##  6. Syncing with Remote

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

##  7. Staging & Committing

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

##  8. Undoing Mistakes

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

---

##  9. Stashing Changes

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

---

##  10. Working with Remotes

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

---

##  11. Viewing History & Logs

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

##  Bonus: Common Shortcuts

| Command                        | What It Does                     |
|--------------------------------|------------------------------------|
| `git checkout -b <branch>`    | Create and switch to new branch   |
| `git pull --rebase`           | Pull changes & rebase local work  |
| `git push origin --delete <branch>` | Delete remote branch          |
| `git clean -fd`               | Remove untracked files & folders  |
