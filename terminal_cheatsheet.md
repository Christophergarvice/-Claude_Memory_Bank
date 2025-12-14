# Terminal Cheat Sheet for Chris
*Real programmer commands - the ones you'll actually use*

## NAVIGATION (Like CD in DOS)

```bash
# Go to home directory
cd ~

# Go to a specific folder
cd ~/PycharmProjects/SimpleBook_Core

# Go up one level
cd ..

# See where you are
pwd

# List files (like DIR in DOS)
ls

# List with details (size, date, permissions)
ls -l

# List including hidden files
ls -la

# List everything in subfolders too
ls -R
```

## FILE OPERATIONS

```bash
# Copy a file
cp oldfile.py newfile.py

# Move/rename a file (like MOVE in DOS)
mv oldname.py newname.py

# Delete a file (careful - no undo!)
rm filename.py

# View a file (like TYPE in DOS)
cat filename.py

# View first 20 lines
head -20 filename.py

# View last 20 lines  
tail -20 filename.py

# Create empty file
touch newfile.txt
```

## CREATING FILES FROM TERMINAL

```bash
# Create a new file with content (paste until you type EOF)
cat > myfile.txt << 'EOF'
Type your content here
Multiple lines work
When done, type EOF on its own line
EOF

# Append to existing file
cat >> myfile.txt << 'EOF'
This adds to the end of the file
EOF
```

## SEARCHING

```bash
# Find a file by name
find . -name "*.py"

# Find a directory
find . -name "SimpleBook*" -type d

# Search inside files for text
grep "def extract_deposits" *.py

# Search recursively in all subdirectories
grep -r "import" .
```

## GIT COMMANDS (You'll use these daily)

```bash
# Clone a repo from GitHub
git clone https://github.com/username/repo-name.git

# See what changed
git status

# Add all changes
git add .

# Add specific file
git add filename.py

# Commit with message
git commit -m "Fixed parser bug"

# Push to GitHub
git push origin main

# Pull latest from GitHub
git pull origin main

# See commit history
git log
```

## DIRECTORY OPERATIONS

```bash
# Create directory
mkdir foldername

# Create nested directories
mkdir -p path/to/nested/folder

# Remove empty directory
rmdir foldername

# Remove directory and everything in it (DANGEROUS!)
rm -rf foldername

# Copy entire directory
cp -r sourcefolder destfolder
```

## RASPBERRY PI SETUP (Coming Monday)

```bash
# SSH into Pi (after initial setup)
ssh pi@raspberrypi.local

# Update Pi software
sudo apt update
sudo apt upgrade -y

# Install Python packages on Pi
pip install package-name --break-system-packages

# Edit crontab for scheduled tasks
crontab -e

# View running processes
top

# Reboot Pi
sudo reboot

# Shutdown Pi
sudo shutdown -h now
```

## FILE PERMISSIONS (When you get "Permission denied")

```bash
# Make file executable
chmod +x script.sh

# Make file readable/writable by you
chmod 644 filename.txt

# View permissions
ls -l
```

## HELPFUL SHORTCUTS

```bash
# Clear screen (like CLS in DOS)
clear

# Cancel current command
Ctrl + C

# Exit heredoc or stuck prompt
Type: EOF and hit Enter

# Previous command
Up Arrow

# Search command history
Ctrl + R, then type to search

# Tab completion (type part of filename, hit Tab)
cd ~/Pyc[TAB] → completes to ~/PycharmProjects/

# Copy from Terminal
Cmd + C (select text first)

# Paste into Terminal  
Cmd + V
```

## YOUR COMMON WORKFLOWS

### Replace a SimpleBook file:
```bash
cd ~/PycharmProjects/SimpleBook_Core/parsers
mv oldfile.py oldfile_BACKUP.py
cat > newfile.py << 'EOF'
[paste code here]
EOF
ls -l newfile.py  # verify
```

### Update GitHub memory:
```bash
cd ~/-Claude_Memory_Bank
cat >> roadmaps/simplebook-roadmap.md << 'EOF'
- [x] New module completed
EOF
git add .
git commit -m "Updated roadmap"
git push origin main
```

### Quick file backup:
```bash
cp important.py important_backup_2025-12-14.py
```

## TIPS FOR LEARNING

1. **Use Tab completion** - Type first few letters, hit Tab
2. **Up arrow recalls commands** - Don't retype, just arrow up
3. **Cmd+K clears screen** - Fresh start when messy
4. **Copy/paste works** - Cmd+C and Cmd+V like normal
5. **Commands are case-sensitive** - "File.py" ≠ "file.py"
6. **Spaces matter** - "cd~" won't work, need "cd ~"

## DOS TO TERMINAL TRANSLATION

| DOS Command | Terminal Equivalent | What it does |
|-------------|-------------------|--------------|
| `dir` | `ls` | List files |
| `dir /w` | `ls` | List wide |
| `dir /s` | `ls -R` | List subdirectories |
| `cd` | `cd` | Change directory |
| `cd..` | `cd ..` | Go up one level |
| `md` | `mkdir` | Make directory |
| `rd` | `rmdir` | Remove directory |
| `copy` | `cp` | Copy file |
| `move` | `mv` | Move/rename |
| `del` | `rm` | Delete file |
| `type` | `cat` | Display file |
| `cls` | `clear` | Clear screen |
| `edit` | `nano` | Text editor |

## WHEN THINGS GO WRONG

```bash
# Stuck in heredoc (shows >, heredoc>, or quote>)
Type: EOF
Then hit Enter

# Wrong directory
pwd  # see where you are
cd ~  # go home and start over

# Permission denied
# Either: run with sudo (be careful!)
sudo command
# Or: check file ownership
ls -l filename

# Command not found
# Usually a typo - check spelling
# Or package not installed
```

## PRACTICE EXERCISES

Try these to build muscle memory:

```bash
# 1. Navigate to your projects
cd ~
cd PycharmProjects
cd SimpleBook_Core
pwd

# 2. List your parsers
cd parsers
ls -l

# 3. Create a test file
cat > test.txt << 'EOF'
This is a test
EOF

# 4. View it
cat test.txt

# 5. Delete it
rm test.txt

# 6. Confirm it's gone
ls test.txt
```

---

**Remember:** Real programmers Google commands constantly. Having this cheat sheet doesn't mean you're not a "real" developer - it means you're working smart.
