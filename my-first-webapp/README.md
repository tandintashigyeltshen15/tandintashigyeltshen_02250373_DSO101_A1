# My First DevOps Web App 🚀

> Assignment IV — DSO101: Continuous Integration and Continuous Deployment  
> Bachelor of Engineering in Software Engineering, RUB

## Live URL
https://my-first-webapp-zguk.onrender.com

## GitHub Repo
https://github.com/tandintashigyeltshen15/tandintashigyeltshen_02250373_DSO101

## Tools Used
- GitHub — version control
- GitHub Actions — CI/CD pipeline
- Render — cloud deployment

## Steps to Deploy

### Step 1: Install Git
Download from https://git-scm.com and verify:
git --version

### Step 2: Clone or Create Repo
Create a new repository on GitHub.

### Step 3: Push Code
git init
git add .
git commit -m "first commit"
git branch -M main
git remote add origin <repo-url>
git push -u origin main

### Step 4: GitHub Actions
The `.github/workflows/deploy.yml` file runs automatically on every push to main.

### Step 5: Deploy on Render
1. Go to https://render.com
2. Sign in with GitHub
3. Click New Static Site
4. Connect your repo
5. Set publish directory to `my-first-webapp`
6. Click Deploy

### Step 6: Verify
- Open the live URL
- Check GitHub Actions logs under the Actions tab

## CI/CD Pipeline
Push Code → GitHub Actions runs → Render deploys automatically

Save with Ctrl+S, then run:
git add .
git commit -m "improve README with deployment steps"
git push