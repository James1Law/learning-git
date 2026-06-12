# What I Learned

This file is a summary of what I learned while practising Git, GitHub, branches, pull requests, and working in the terminal.

---

## 1. The basic Git flow

The main workflow I practised was:

```text
main
→ create a new branch
→ make changes
→ stage changes
→ commit changes
→ push the branch to GitHub
→ create a pull request
→ merge the pull request
→ switch back to main locally
→ pull the latest main
→ delete the old branch
```

This helped me understand that Git is not just about saving files. It is about tracking changes properly and moving those changes between my Mac and GitHub.

---

## 2. Local repo vs remote repo

There are two places I need to keep in sync:

```text
Local repo = the copy on my Mac
Remote repo = the copy on GitHub
```

When I make a commit, that only saves the change locally.

When I push, I send my local branch or commits up to GitHub.

When I pull, I bring the latest changes from GitHub down to my Mac.

---

## 3. Useful Git commands I used

### Check which branch I am on

```bash
git branch
```

The branch with the `*` next to it is the branch I am currently on.

---

### Create a new branch and switch to it

```bash
git checkout -b new-branch
```

This creates a new branch from the branch I am currently on.

---

### Switch branches

```bash
git checkout main
```

This moves me back to the `main` branch.

---

### Check what has changed

```bash
git status
```

This is one of the most useful Git commands. It shows:

- which branch I am on
- which files have changed
- which files are staged
- whether there is anything to commit

---

### Stage changes

```bash
git add .
```

This stages all changed files so they are ready to be committed.

---

### Commit changes

```bash
git commit -m "Add beginner Git notes"
```

A commit saves a snapshot of the staged changes locally.

The message should describe what changed.

---

### Push a branch to GitHub

```bash
git push origin new-branch
```

This sends the local branch to GitHub.

---

### Pull the latest main from GitHub

```bash
git pull origin main
```

This updates my local `main` branch with the latest version from GitHub.

---

### Delete a local branch after it has been merged

```bash
git branch -d new-branch
```

This removes the branch from my Mac once I no longer need it.

---

## 4. What a pull request is

A pull request is a way of saying:

> I have made changes on this branch. Please review them and merge them into main.

A pull request lets me compare my branch against `main`, review the changes, and then merge them safely.

---

## 5. What merge means

Merging means taking the changes from one branch and adding them into another branch.

In my case, I created a branch, made changes, pushed it to GitHub, opened a pull request, and merged that branch into `main`.

After that, my local `main` was behind GitHub, so I needed to run:

```bash
git pull origin main
```

---

## 6. What detached HEAD means

At one point I saw something like:

```text
HEAD detached
```

This means I was not properly sitting on a normal branch.

I fixed it by switching back to `main`:

```bash
git checkout main
```

Then I pulled the latest changes:

```bash
git pull origin main
```

---

## 7. Folder rename learning

I renamed a folder from something like:

```text
markdown
```

to:

```text
docs
```

Git tracked this as a rename.

This showed me that Git understands file moves and folder changes, not just text changes inside files.

---

## 8. Terminal mistake I made

I accidentally pasted Markdown text directly into the terminal without wrapping it properly.

The terminal tried to run parts of the text as commands, which caused errors like:

```text
zsh: command not found
```

The lesson:

If I want to write a lot of text into a file from the terminal, I should use a proper method such as:

```bash
cat > filename.md <<'EOF'
My text goes here
EOF
```

Or just open the file in Cursor and paste the content there.

---

## 9. The most important commands so far

The commands I should remember first are:

```bash
pwd
ls
cd
mkdir
touch
git status
git branch
git checkout -b branch-name
git checkout main
git add .
git commit -m "message"
git push origin branch-name
git pull origin main
git branch -d branch-name
```

---

## 10. Final takeaway

The biggest thing I learned is that Git has a logical flow.

I do my work on a branch, save the work with a commit, push it to GitHub, merge it through a pull request, then bring my local `main` back up to date.

The main loop is:

```text
branch
→ change
→ add
→ commit
→ push
→ pull request
→ merge
→ pull main locally
```

That is the foundation I need before moving on to more advanced Git.
