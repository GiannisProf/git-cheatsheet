# Necessary commands to execute only once before starting using Git and Github

##  1. Set your username & email (global)
```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```
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

---