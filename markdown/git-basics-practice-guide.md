# Git Basics Practice Guide

This guide is designed for practising Git from the terminal. You can use this file itself as your practice file: edit it, save it, stage it, commit it, and push it to GitHub.

---

## The basic Git idea

Git tracks changes to files over time.

A normal Git workflow looks like this:

```bash
git status
git add .
git commit -m "Describe what changed"
git push origin main
```

Think of it like this:

| Step | Meaning |
|---|---|
| Edit files | Make changes on your computer |
| `git add` | Choose which changes to include in the next save point |
| `git commit` | Create the save point |
| `git push` | Upload your commits to GitHub |
| `git pull` | Download the latest commits from GitHub |

---

## `git init`

```bash
git init
```

This creates a new Git repository in the current folder.

In simple terms, it tells Git:

> Start tracking this folder as a project.

It creates a hidden folder called `.git`. That hidden folder stores Git's history and settings.

### Example

```bash
mkdir my-git-practice
cd my-git-practice
git init
```

After this, your folder is now a Git repo.

---

## `git status`

```bash
git status
```

This shows what is happening in your repo.

It tells you things like:

- Which files have changed
- Which files are staged
- Which files are untracked
- Which branch you are on

You will use this command constantly.

### Example

```bash
git status
```

You might see something like:

```text
Untracked files:
  git-basics-practice-guide.md
```

That means Git can see the file, but it is not tracking it yet.

---

## `git add`

```bash
git add filename.md
```

This stages a file.

In simple terms, it means:

> Include this file in my next commit.

### Add one file

```bash
git add git-basics-practice-guide.md
```

### Add everything

```bash
git add .
```

The `.` means:

> Add all changed files in this folder and below.

Important: `git add` does **not** create a commit. It only prepares changes for a commit.

---

## `git commit`

```bash
git commit -m "Add Git basics guide"
```

This creates a saved checkpoint in your Git history.

In simple terms, it means:

> Save the staged changes with this message.

The `-m` means message.

### Example

```bash
git add .
git commit -m "Add Git basics practice guide"
```

A good commit message should briefly describe what changed.

Good examples:

```bash
git commit -m "Add homepage layout"
git commit -m "Fix login button styling"
git commit -m "Update README instructions"
```

Less useful examples:

```bash
git commit -m "stuff"
git commit -m "changes"
git commit -m "asdf"
```

---

## `git log`

```bash
git log
```

This shows your commit history.

You will see things like:

- Commit hash
- Author
- Date
- Commit message

### Shorter version

```bash
git log --oneline
```

This is often easier to read.

Example output:

```text
a1b2c3d Add Git basics practice guide
f4e5d6c Add README
```

Each commit has a unique ID called a commit hash.

---

## `git branch`

```bash
git branch
```

This shows your local branches.

The branch with `*` next to it is the branch you are currently on.

Example:

```text
* main
  test-branch
```

This means you are currently on `main`.

---

## `git checkout`

```bash
git checkout branch-name
```

This switches from one branch to another.

In simple terms:

> Move me to this branch.

### Example

```bash
git checkout main
```

This switches you to the `main` branch.

Another example:

```bash
git checkout test-branch
```

This switches you to `test-branch`.

---

## `git checkout -b`

```bash
git checkout -b new-branch-name
```

This creates a new branch and switches to it immediately.

In simple terms:

> Create a new working version of the project and move me onto it.

### Example

```bash
git checkout -b update-guide
```

This creates a new branch called `update-guide` and switches to it.

You can then make changes safely without changing `main` directly.

---

## `git switch`

Newer Git versions also support `git switch`, which is a clearer way to change branches.

### Switch to an existing branch

```bash
git switch main
```

### Create and switch to a new branch

```bash
git switch -c update-guide
```

You will still see lots of tutorials using `git checkout`, so it is worth understanding both.

---

## `git remote -v`

```bash
git remote -v
```

This shows the remote repositories connected to your local repo.

Usually, your GitHub repo is called `origin`.

Example output:

```text
origin  https://github.com/your-username/your-repo.git (fetch)
origin  https://github.com/your-username/your-repo.git (push)
```

In simple terms:

> `origin` is the GitHub version of your repo.

---

## `git remote add origin`

```bash
git remote add origin https://github.com/your-username/your-repo.git
```

This connects your local repo to a GitHub repo.

You usually do this once, after creating a new empty repo on GitHub.

### Example

```bash
git remote add origin https://github.com/james/example-repo.git
```

Then check it worked:

```bash
git remote -v
```

---

## `git push origin main`

```bash
git push origin main
```

This uploads your local commits to the `main` branch on GitHub.

Breaking it down:

| Part | Meaning |
|---|---|
| `git push` | Upload commits |
| `origin` | The remote repo, usually GitHub |
| `main` | The branch you are pushing |

### Example

```bash
git push origin main
```

If your repo uses `master` instead of `main`, you would use:

```bash
git push origin master
```

---

## `git push -u origin main`

```bash
git push -u origin main
```

This pushes your branch and sets the default upstream branch.

In simple terms:

> Push this branch to GitHub, and remember where it should push to next time.

After doing this once, you can usually just run:

```bash
git push
```

instead of:

```bash
git push origin main
```

---

## `git pull origin main`

```bash
git pull origin main
```

This downloads the latest changes from the `main` branch on GitHub and brings them into your current local branch.

Breaking it down:

| Part | Meaning |
|---|---|
| `git pull` | Download and merge changes |
| `origin` | The remote repo, usually GitHub |
| `main` | The branch you are pulling from |

### Example

```bash
git pull origin main
```

If the repo uses `master`, you would use:

```bash
git pull origin master
```

Once your branch is tracking a remote branch, you can often just run:

```bash
git pull
```

---

## `main` vs `master`

`main` and `master` are branch names.

Older repos often used `master` as the default branch.

Newer repos usually use `main`.

To check which one your repo uses, run:

```bash
git branch
```

And:

```bash
git branch -r
```

If you see `origin/main`, use `main`.

If you see `origin/master`, use `master`.

---

## Practice exercise 1: Create a repo and commit a file

```bash
mkdir git-practice
cd git-practice
git init
```

Create a file:

```bash
touch notes.md
```

Open `notes.md` and add some text.

Then run:

```bash
git status
git add notes.md
git status
git commit -m "Add notes file"
git log --oneline
```

You have now made your first commit.

---

## Practice exercise 2: Make another change

Edit `notes.md` again and add another sentence.

Then run:

```bash
git status
git add .
git commit -m "Update notes"
git log --oneline
```

You should now see two commits.

---

## Practice exercise 3: Create a branch

```bash
git checkout -b experiment
```

Edit `notes.md` again.

Then run:

```bash
git add .
git commit -m "Add experimental note"
git log --oneline
```

Now switch back to `main`:

```bash
git checkout main
```

Your experimental change may disappear from the file. That is normal, because it exists on the `experiment` branch, not on `main`.

Switch back:

```bash
git checkout experiment
```

The change should come back.

---

## Practice exercise 4: Push to GitHub

1. Create a new empty repo on GitHub.
2. Copy the repo URL.
3. In your local project, run:

```bash
git remote add origin https://github.com/your-username/your-repo.git
git branch -M main
git push -u origin main
```

After that, refresh GitHub. Your files should be there.

---

## Common beginner commands

| Command | What it does |
|---|---|
| `git init` | Start tracking a folder with Git |
| `git status` | Show what has changed |
| `git add .` | Stage all changes |
| `git add filename` | Stage one file |
| `git commit -m "message"` | Save staged changes with a message |
| `git log` | Show commit history |
| `git log --oneline` | Show shorter commit history |
| `git branch` | Show local branches |
| `git checkout branch-name` | Switch branch |
| `git checkout -b branch-name` | Create and switch to a new branch |
| `git remote -v` | Show connected remote repos |
| `git push origin main` | Push local commits to GitHub |
| `git pull origin main` | Pull latest changes from GitHub |

---

## A simple daily workflow

When starting work:

```bash
git pull
```

After making changes:

```bash
git status
git add .
git commit -m "Describe what changed"
git push
```

That is the basic loop.

---

## Useful safety habit

Before running Git commands, use:

```bash
git status
```

It tells you where you are and what Git thinks is happening.

When in doubt, check status first.
