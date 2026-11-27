

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









#docker file

# STEP 1: Create project folder
mkdir Docker-Calculator
cd Docker-Calculator

# STEP 2: Create calculator.js manually in VS Code
# Paste the JavaScript code provided below and save it.

# STEP 3: Create Dockerfile manually in VS Code
# Paste the Dockerfile content provided below and save it.

# STEP 4: Build Docker image
docker build -t calculator .

# STEP 5: Verify image
docker images

# STEP 6: Run calculator container
docker run --rm calculator 10 + 5
docker run --rm calculator 10 - 5
docker run --rm calculator 10 '*' 5
docker run --rm calculator 10 / 2

# STEP 7: Login to Docker Hub
docker login

# STEP 8: Tag image for Docker Hub
docker tag calculator YOUR_USERNAME/calculator-app:latest

# STEP 9: Push image to Docker Hub
docker push YOUR_USERNAME/calculator-app:latest

# STEP 10: Verify image
# Open https://hub.docker.com/repositories
# Open calculator-app and check the Tags section.




FROM node:20-alpine
WORKDIR /app
COPY calculator.js .
CMD ["node", "calculator.js"]






//minikube
minikube start --driver=docker

kubectl create deployment mynginx --image=nginx

kubectl get deployments
kubectl get pods

kubectl expose deployment mynginx --type=NodePort --port=80 --target-port=80

kubectl scale deployment mynginx --replicas=4

kubectl get pods
kubectl get services

minikube service mynginx







//docker-multi
mkdir compose-lab
cd compose-lab
code .

# Create and save docker-compose.yml first

docker compose up -d
docker compose ps

# Open http://localhost:8080

docker compose logs
docker compose down
docker compose up -d
docker compose ps




.yaml file:
services:
  web:
    image: nginx:latest
    ports:
      - "8080:80"

  db:
    image: postgres:15
    environment:
      POSTGRES_USER: demo
      POSTGRES_PASSWORD: demo
      POSTGRES_DB: demo_db
