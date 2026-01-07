\# Your First GIT Repository: An Interactive Guide



\## 🎯 What You'll Build

By the end of this guide, you'll have:

\- Created your first local repository

\- Made several commits

\- Created and merged a branch

\- Connected to GitHub and pushed your code



---



\*\*\*Open Git Bash or Codespaces to code this project\*\*\*



\## Part 1: Setup Your First Repo (10 minutes)



\### Step 1: Create a Practice Project

Open your terminal and run:



```bash

mkdir my-first-git-project

cd my-first-git-project

```



\### Step 2: Initialize GIT

```bash

git init

```



\*\*What just happened?\*\* GIT created a hidden `.git` folder that will track all your changes.



Verify it worked:

```bash

ls -a

```



You should see `.git` in the list.



\### Step 3: Create Your First File

```bash

echo "# My First GIT Project" > README.md

```



Check what GIT sees:

```bash

git status

```



\*\*You should see:\*\* `README.md` listed as an "untracked file" in red.



---



\## Part 2: Your First Commit (5 minutes)



\### Step 4: Stage Your File

```bash

git add README.md

```



Check status again:

```bash

git status

```



\*\*You should see:\*\* `README.md` is now green and "ready to be committed."



\### Step 5: Make Your First Commit

```bash

git commit -m "Initial commit: added README"

```



\*\*What just happened?\*\* You saved a snapshot of your project. This is commit #1.



View your commit history:

```bash

git log

```



You'll see your commit with a long hash (like `df73f34fac...`), your name, date, and message.



---



\## Part 3: Make More Changes (10 minutes)



\### Step 6: Edit and Commit Again

```bash

echo "This project teaches me GIT basics." >> README.md

```



Check what changed:

```bash

git diff

```



\*\*You should see:\*\* The new line highlighted in green with a `+` sign.



Now commit this change:

```bash

git add README.md

git commit -m "Added project description"

```



\### Step 7: Add Another File

```bash

echo "print('Hello from Python!')" > app.py

```



This time, use a shortcut to add ALL changes:

```bash

git add .

git commit -m "Added Python application file"

```



Check your history:

```bash

git log

```



\*\*You should see:\*\* Three commits now!



---



\## Part 4: Branching (15 minutes)



\### Step 8: Create a New Branch

Let's say you want to add a new feature without messing up your main code.



```bash

git branch feature-greeting

```



View all branches:

```bash

git branch

```



\*\*You should see:\*\* 

\- `\* main` (or `\* master`) ← The asterisk shows you're currently here

\- `feature-greeting`



\### Step 9: Switch to Your New Branch

```bash

git checkout feature-greeting

```



Verify:

```bash

git branch

```



\*\*You should see:\*\* The asterisk is now next to `feature-greeting`.



\### Step 10: Make Changes on the Branch

```bash

echo "def greet(name):" >> app.py

echo "    return f'Hello, {name}!'" >> app.py

```



Commit these changes:

```bash

git add app.py

git commit -m "Added greeting function"

```



\*\*Important:\*\* This commit only exists on the `feature-greeting` branch!



---



\## Part 5: Merging (10 minutes)



\### Step 11: Switch Back to Main

```bash

git checkout main

```



Open `app.py`:

```bash

cat app.py

```



\*\*Notice:\*\* Your greeting function is GONE! It only exists on the other branch.



\### Step 12: Merge Your Feature

```bash

git merge feature-greeting

```



\*\*What just happened?\*\* GIT combined the changes from `feature-greeting` into `main`.



Check `app.py` again:

```bash

cat app.py

```



\*\*You should see:\*\* The greeting function is now here!



\### Step 13: Delete the Old Branch

```bash

git branch -d feature-greeting

```



The branch is no longer needed since we merged it.



---



\## Part 6: Connect to GitHub (15 minutes)



\### Step 14: Create a GitHub Repository

1\. Go to \[github.com](https://github.com) and log in

2\. Click the `+` in the top right → "New repository"

3\. Name it: `my-first-git-project`

4\. \*\*Don't\*\* initialize with README (you already have one!)

5\. Click "Create repository"



\### Step 15: Copy Your Remote URL

GitHub will show you a URL that looks like:

```

https://github.com/YOUR-USERNAME/my-first-git-project.git

```



Copy this URL.



\### Step 16: Add the Remote

```bash

git remote add origin https://github.com/YOUR-USERNAME/my-first-git-project.git

```



Verify it worked:

```bash

git remote get-url origin

```



\### Step 17: Push Your Code

```bash

git push -u origin main

```



\*\*What just happened?\*\* You uploaded all your commits to GitHub!



Refresh your GitHub repository page - you should see your files!



---



\## Part 7: Practice the Workflow (Ongoing)



\### The Daily GIT Workflow

From now on, when you code:



```bash

\# 1. See what changed

git status



\# 2. See the actual differences

git diff



\# 3. Add your changes

git add .



\# 4. Commit with a clear message

git commit -m "Describe what you did"



\# 5. Upload to GitHub

git push origin main

```



\### When Working with Others

Download their changes before you start working:

```bash

git pull origin main

```



---



\## 🎉 Congratulations!



You now understand:

\- ✅ How to create a repository

\- ✅ How to commit changes

\- ✅ How to create and merge branches

\- ✅ How to connect to GitHub

\- ✅ The daily GIT workflow



\## Quick Reference Card



```bash

\# Status \& Info

git status              # What changed?

git log                 # Commit history

git diff               # See changes



\# Making Changes

git add .              # Stage everything

git commit -m "msg"    # Save snapshot



\# Branching

git branch <name>      # Create branch

git checkout <name>    # Switch branch

git merge <name>       # Merge branch



\# Remote (GitHub)

git remote add origin <url>  # Connect to GitHub

git push origin main         # Upload

git pull origin main         # Download

```



Need to practice more? Create another project and go through this guide again - it'll be faster the second time!

