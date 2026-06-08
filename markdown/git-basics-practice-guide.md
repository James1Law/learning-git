# Git Basics Practice Guide

This guide is designed for practising Git from the terminal.

You can use this file itself as your practice file: edit it, save it, stage it, commit it, push it to GitHub, and open pull requests from it.

---

## The basic Git idea

Git tracks changes to files over time.

A normal Git workflow looks like this:

bash git status git add . git commit -m "Describe what changed" git push 

If you are pushing a new branch to GitHub for the first time, you may need:

bash git push -u origin branch-name 

Think of it like this:

| Step | Meaning |
|---|---|
| Edit files | Make changes on your computer |
| git status | Check what Git can see |
| git add | Choose which changes to include in the next save point |
| git commit | Create the save point |
| git push | Upload your commits to GitHub |
| git pull | Download the latest commits from GitHub |

---

## Two ways to start with Git

There are two common ways to start working with a Git repo.

| Command | When to use it |
|---|---|
| git init | When you are starting a brand new project on your computer |
| git clone | When the project already exists on GitHub and you want a copy locally |

In simple terms:

text git init  = start a new Git repo here git clone = download an existing Git repo 

---

## git clone

bash git clone https://github.com/username/repo-name.git 

This copies an existing GitHub repository onto your computer.

In simple terms, it means:

> Download this project from GitHub and set it up as a Git repo on my machine.

When you clone a repo, Git automatically:

- Downloads the files
- Downloads the commit history
- Creates the hidden .git folder
- Connects your local repo to the GitHub repo
- Usually sets the remote name as origin

### Example

bash git clone https://github.com/james/example-repo.git 

This creates a new folder called example-repo.

Then you move into it:

bash cd example-repo 

Then check everything:

bash git status git remote -v 

You should see that your local repo is connected to GitHub.

### Clone into a specific folder name

By default, Git creates a folder with the same name as the repo.

This:

bash git clone https://github.com/username/repo-name.git 

creates:

text repo-name/ 

But you can choose a different local folder name:

bash git clone https://github.com/username/repo-name.git my-local-folder 

That creates:

text my-local-folder/ 

### Important note

Only use git clone when you want to download an existing repo.

If you already have the repo locally, do not clone it again. Instead, go into the folder and use:

bash git pull 

---

## git init

bash git init 

This creates a new Git repository in the current folder.

In simple terms, it tells Git:

> Start tracking this folder as a project.

It creates a hidden folder called .git. That hidden folder stores Git's history and settings.

### Example

bash mkdir my-git-practice cd my-git-practice git init 

After this, your folder is now a Git repo.

### Important note

git init does not upload anything to GitHub.

It only creates a Git repo on your computer.

To connect it to GitHub, you would later use:

bash git remote add origin https://github.com/username/repo-name.git 

---

## git status

bash git status 

This shows what is happening in your repo.

It tells you things like:

- Which files have changed
- Which files are staged
- Which files are untracked
- Which branch you are on

You will use this command constantly.

### Example

bash git status 

You might see something like:

text Untracked files:   git-basics-practice-guide.md 

That means Git can see the file, but it is not tracking it yet.

### Good habit

When in doubt, run:

bash git status 

It is one of the safest and most useful Git commands.

---

## git add

bash git add filename.md 

This stages a file.

In simple terms, it means:

> Include this file in my next commit.

### Add one file

bash git add git-basics-practice-guide.md 

### Add everything

bash git add . 

The . means:

> Add all changed files in this folder and below.

Important: git add does not create a commit. It only prepares changes for a commit.

---

## git commit

bash git commit -m "Add Git basics guide" 

This creates a saved checkpoint in your Git history.

In simple terms, it means:

> Save the staged changes with this message.

The -m means message.

### Example

bash git add . git commit -m "Add Git basics practice guide" 

A good commit message should briefly describe what changed.

Good examples:

bash git commit -m "Add homepage layout" git commit -m "Fix login button styling" git commit -m "Update README instructions" 

Less useful examples:

bash git commit -m "stuff" git commit -m "changes" git commit -m "asdf" 

---

## git log

bash git log 

This shows your commit history.

You will see things like:

- Commit hash
- Author
- Date
- Commit message

### Shorter version

bash git log --oneline 

This is often easier to read.

Example output:

text a1b2c3d Add Git basics practice guide f4e5d6c Add README 

Each commit has a unique ID called a commit hash.

### Getting out of git log

Sometimes git log opens in a scrollable view.

To exit, press:

text q 

---

## git branch

bash git branch 

This shows your local branches.

The branch with * next to it is the branch you are currently on.

Example:

text * main   test-branch 

This means you are currently on main.

---

## git checkout

bash git checkout branch-name 

This switches from one branch to another.

In simple terms:

> Move me to this branch.

### Example

bash git checkout main 

This switches you to the main branch.

Another example:

bash git checkout test-branch 

This switches you to test-branch.

---

## git checkout -b

bash git checkout -b new-branch-name 

This creates a new branch and switches to it immediately.

In simple terms:

> Create a new working version of the project and move me onto it.

### Example

bash git checkout -b update-guide 

This creates a new branch called update-guide and switches to it.

You can then make changes safely without changing main directly.

---

## git switch

Newer Git versions also support git switch, which is a clearer way to change branches.

### Switch to an existing branch

bash git switch main 

### Create and switch to a new branch

bash git switch -c update-guide 

You will still see lots of tutorials using git checkout, so it is worth understanding both.

---

## git branch -d

bash git branch -d branch-name 

This deletes a local branch.

You normally do this after a pull request has been merged.

### Example

bash git branch -d update-guide 

The lowercase -d is the safe version. It only deletes the branch if Git can see that it has already been merged.

There is also:

bash git branch -D branch-name 

That force deletes a branch. Avoid this as a beginner unless you are completely sure you want to throw away the branch.

---

## git remote -v

bash git remote -v 

This shows the remote repositories connected to your local repo.

Usually, your GitHub repo is called origin.

Example output:

text origin  https://github.com/your-username/your-repo.git (fetch) origin  https://github.com/your-username/your-repo.git (push) 

In simple terms:

> origin is the GitHub version of your repo.

---

## git remote add origin

bash git remote add origin https://github.com/your-username/your-repo.git 

This connects your local repo to a GitHub repo.

You usually do this once, after creating a new empty repo on GitHub.

### Example

bash git remote add origin https://github.com/james/example-repo.git 

Then check it worked:

bash git remote -v 

---

## git push origin main

bash git push origin main 

This uploads your local commits to the main branch on GitHub.

Breaking it down:

| Part | Meaning |
|---|---|
| git push | Upload commits |
| origin | The remote repo, usually GitHub |
| main | The branch you are pushing |

### Example

bash git push origin main 

If your repo uses master instead of main, you would use:

bash git push origin master 

---

## git push -u origin branch-name

bash git push -u origin branch-name 

This pushes your branch and sets the default upstream branch.

In simple terms:

> Push this branch to GitHub, and remember where it should push to next time.

The -u means:

> Set upstream.

That means your local branch is linked to the matching branch on GitHub.

After doing this once, you can usually just run:

bash git push 

instead of:

bash git push origin branch-name 

### Example

bash git push -u origin update-guide 

After that, future pushes from the same branch can usually be:

bash git push 

---

## git pull origin main

bash git pull origin main 

This downloads the latest changes from the main branch on GitHub and brings them into your current local branch.

Breaking it down:

| Part | Meaning |
|---|---|
| git pull | Download and merge changes |
| origin | The remote repo, usually GitHub |
| main | The branch you are pulling from |

### Example

bash git pull origin main 

If the repo uses master, you would use:

bash git pull origin master 

Once your branch is tracking a remote branch, you can often just run:

bash git pull 

---

## git fetch

bash git fetch 

This downloads information from GitHub, but does not merge it into your current branch.

In simple terms:

> Check what has changed on GitHub, but do not change my files yet.

This is different from git pull.

| Command | Meaning |
|---|---|
| git fetch | Download remote information only |
| git pull | Download remote information and merge it into your current branch |

As a beginner, you will use git pull more often. But git fetch is useful to know because you will see it in tutorials and tools.

---

## main vs master

main and master are branch names.

Older repos often used master as the default branch.

Newer repos usually use main.

To check which one your repo uses, run:

bash git branch 

And:

bash git branch -r 

If you see origin/main, use main.

If you see origin/master, use master.

---

## Pull requests

A pull request is a GitHub feature, not a basic Git command.

A normal pull request workflow looks like this:

bash git checkout main git pull origin main git checkout -b update-guide 

Then make your changes.

bash git status git add . git commit -m "Update guide" git push -u origin update-guide 

Then go to GitHub and create a pull request from:

text update-guide into main 

After the pull request is merged, go back to your terminal:

bash git checkout main git pull origin main git branch -d update-guide 

You can also delete the remote branch on GitHub after the pull request has been merged.

---

## Practice exercise 1: Clone an existing repo

Use this when the repo already exists on GitHub.

bash cd ~/LocalProjects git clone https://github.com/username/repo-name.git cd repo-name git status git remote -v 

This downloads the repo, moves you into the repo folder, and checks that everything is connected.

---

## Practice exercise 2: Create a repo and commit a file

Use this when you are starting from your computer.

bash mkdir git-practice cd git-practice git init 

Create a file:

bash touch notes.md 

Open notes.md and add some text.

Then run:

bash git status git add notes.md git status git commit -m "Add notes file" git log --oneline 

You have now made your first commit.

---

## Practice exercise 3: Make another change

Edit notes.md again and add another sentence.

Then run:

bash git status git add . git commit -m "Update notes" git log --oneline 

You should now see two commits.

---

## Practice exercise 4: Create a branch

bash git checkout -b experiment 

Edit notes.md again.

Then run:

bash git add . git commit -m "Add experimental note" git log --oneline 

Now switch back to main:

bash git checkout main 

Your experimental change may disappear from the file. That is normal, because it exists on the experiment branch, not on main.

Switch back:

bash git checkout experiment 

The change should come back.

---

## Practice exercise 5: Push to GitHub

1. Create a new empty repo on GitHub.
2. Copy the repo URL.
3. In your local project, run:

bash git remote add origin https://github.com/your-username/your-repo.git git branch -M main git push -u origin main 

After that, refresh GitHub. Your files should be there.

---

## Practice exercise 6: Create a pull request

Start from main:

bash git checkout main git pull origin main 

Create a new branch:

bash git checkout -b update-notes 

Make a change to a file.

Then run:

bash git status git add . git commit -m "Update notes" git push -u origin update-notes 

Go to GitHub and create a pull request from:

text update-notes into main 

After merging the pull request, return to your terminal:

bash git checkout main git pull origin main git branch -d update-notes 

---

## Common beginner commands

| Command | What it does |
|---|---|
| git clone repo-url | Copy an existing GitHub repo onto your computer |
| git init | Start tracking a folder with Git |
| git status | Show what has changed |
| git add . | Stage all changes |
| git add filename | Stage one file |
| git commit -m "message" | Save staged changes with a message |
| git log | Show commit history |
| git log --oneline | Show shorter commit history |
| git branch | Show local branches |
| git checkout branch-name | Switch branch |
| git checkout -b branch-name | Create and switch to a new branch |
| git switch branch-name | Switch branch using the newer command |
| git switch -c branch-name | Create and switch to a new branch using the newer command |
| git branch -d branch-name | Delete a local branch safely |
| git remote -v | Show connected remote repos |
| git remote add origin repo-url | Connect a local repo to GitHub |
| git push origin main | Push local commits to GitHub |
| git push -u origin branch-name | Push a new branch and set upstream |
| git pull origin main | Pull latest changes from GitHub |
| git fetch | Download remote information without merging |

---

## Common beginner mistakes

### Trying to commit an empty folder

Git does not track empty folders.

This will not create a useful commit:

bash mkdir notes git add . git commit -m "Add notes folder" 

Instead, create a file inside it:

bash mkdir notes touch notes/notes.md git add . git commit -m "Add notes folder with notes file" 

### Forgetting which branch you are on

Check with:

bash git branch 

Or:

bash git status 

The current branch will be shown.

### Forgetting to pull latest main

Before starting a new branch, it is a good habit to run:

bash git checkout main git pull origin main 

Then create your new branch.

### Accidentally committing .DS_Store

.DS_Store is a macOS system file. You normally do not want it in GitHub.

Add this to .gitignore:

gitignore .DS_Store 

If it was already committed, remove it from Git tracking:

bash git rm --cached .DS_Store git add .gitignore git commit -m "Ignore DS_Store" 

---

## A simple daily workflow

When starting work:

bash git checkout main git pull origin main git checkout -b my-new-branch 

After making changes:

bash git status git add . git commit -m "Describe what changed" git push -u origin my-new-branch 

Then create and merge a pull request on GitHub.

After merging:

bash git checkout main git pull origin main git branch -d my-new-branch 

That is the basic loop.

---

## Useful safety habit

Before running Git commands, use:

bash git status 

It tells you where you are and what Git thinks is happening.

When in doubt, check status first.