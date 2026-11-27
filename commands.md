
# =====================================
# 1. CLONE AND ENTER REPOSITORY
# =====================================

git clone https://github.com/tanvipriya900/se-lab-all.git
cd se-lab-all


# =====================================
# 2. BASIC GIT COMMANDS
# =====================================

git status

# MANUALLY EDIT README.md, ADD A NEW LINE, AND SAVE.

git diff
git add .
git commit -m "Basic commit"
git log --oneline


# =====================================
# 3. PUSH, FETCH AND PULL
# =====================================

git push

# TO DEMONSTRATE FETCH AND PULL:
# OPEN README.md ON GITHUB, EDIT IT, ADD A LINE,
# AND CLICK COMMIT CHANGES.

git fetch origin
git branch -r
git pull origin main


# =====================================
# 4. BRANCH CREATION AND SWITCHING
# =====================================

git branch
git branch feature
git switch feature

# MANUALLY EDIT README.md, ADD A LINE, AND SAVE.

git add .
git commit -m "Feature update"

git switch main


# =====================================
# 5. MERGE
# =====================================

git merge feature


# =====================================
# 6. REVERT
# =====================================

# CREATE A NEW CHANGE IN README.md AND SAVE.

git add .
git commit -m "Test revert"

git revert HEAD --no-edit


# =====================================
# 7. RESET
# =====================================

# CREATE ANOTHER CHANGE IN README.md AND SAVE.

git add .
git commit -m "Test reset"

# UNDO LAST COMMIT, KEEP CHANGES UNSTAGED.
git reset HEAD~1

# ALTERNATIVES:
# KEEP CHANGES STAGED:
git reset --soft HEAD~1

# DISCARD CHANGES COMPLETELY (USE ONLY FOR PRACTICE):
git reset --hard HEAD~1


# =====================================
# 8. MERGE CONFLICT AND RESOLUTION
# =====================================

git switch -c conflict

# EDIT README.md. ADD A LINE.
git add .
git commit -m "Feature change"

git switch main

# EDIT THE SAME LINE IN README.md DIFFERENTLY.
git add .
git commit -m "Main change"

# MERGE AND TRIGGER CONFLICT.
git merge conflict

# OPEN README.md.
# REMOVE CONFLICT MARKERS.
# KEEP THE REQUIRED CONTENT AND SAVE.

git add .
git commit -m "Resolve conflict"


# =====================================
# 9. REBASE
# =====================================

git switch -c rebase-feature

# EDIT README.md, ADD A NEW LINE, AND SAVE.
git add .
git commit -m "Feature update"

git switch main

# EDIT README.md AGAIN, ADD ANOTHER LINE, AND SAVE.
git add .
git commit -m "Main update"

git switch rebase-feature
git rebase main

# IF A CONFLICT OCCURS:
# RESOLVE README.md, SAVE, THEN RUN:

git add .
git rebase --continue

# TO CANCEL REBASE:
git rebase --abort


# =====================================
# 10. USEFUL COMMANDS
# =====================================

git remote -v
git branch -a
git branch -d feature
git log --oneline --graph --all
git status





**NAGIOS**
# Download image
docker pull jasonrivers/nagios:latest

# Run Nagios
docker run --name nagiosdemo -p 8888:80 jasonrivers/nagios:latest

# Run in background (alternative)
docker run -d --name nagiosdemo -p 8888:80 jasonrivers/nagios:latest

# Check running containers
docker ps

# View logs
docker logs nagiosdemo

# Stop container
docker stop nagiosdemo

# Start stopped container
docker start nagiosdemo

# Remove container
docker rm nagiosdemo

# List images
docker images

# Remove image
docker rmi jasonrivers/nagios:latest
