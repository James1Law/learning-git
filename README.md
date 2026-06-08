# Learning Git and Terminal Commands

This repository is my personal practice space for learning Git, GitHub, and useful beginner terminal commands.

The aim is not to build a production project. The aim is to practise the basic developer workflow in a safe place, make mistakes, fix them, and get comfortable using Git, GitHub, Cursor, and the command line.

## What this repo is for

I am using this repo to practise:

- Initialising a Git repository with git init
- Cloning an existing GitHub repository with git clone
- Creating and switching branches
- Making changes to files
- Staging changes with git add
- Saving changes with git commit
- Viewing history with git log
- Pushing branches to GitHub
- Creating pull requests
- Merging changes into main
- Tidying up branches after a pull request is merged
- Using .gitignore to avoid committing unwanted files
- Building confidence with everyday terminal commands

## Current focus

Right now, I am focusing on two areas:

1. Learning the basic Git and GitHub workflow
2. Learning useful terminal commands for coding and local development

## Files in this repo

| File | Purpose |
|---|---|
| README.md | Explains what this practice repo is for |
| git-basics-practice-guide.md | A beginner guide to Git commands and GitHub workflow |
| beginner-terminal-commands.md | A beginner guide to useful terminal commands for coding |

## Git commands I am practising

bash git clone git init git status git add . git commit -m "Describe the change" git log git log --oneline git checkout main git checkout -b branch-name git branch git branch -d branch-name git remote -v git remote add origin repo-url git push -u origin branch-name git pull origin main git fetch 

## Terminal commands I am practising

bash pwd ls cd mkdir touch cat echo cp mv rm clear open . code . 

## Practice workflow

A typical practice workflow in this repo is:

bash git checkout main git pull origin main git checkout -b my-new-branch 

Then make a change to a file.

bash git status git add . git commit -m "Describe what changed" git push -u origin my-new-branch 

Then open GitHub, create a pull request, review the change, and merge it into main.

After merging:

bash git checkout main git pull origin main git branch -d my-new-branch 

## Starting from an existing GitHub repo

If the repo already exists on GitHub, I can copy it onto my Mac with:

bash cd ~/LocalProjects git clone https://github.com/username/repo-name.git cd repo-name git status 

This is different from git init.

| Command | Use it when |
|---|---|
| git clone | The repo already exists on GitHub and I want a local copy |
| git init | I am starting a brand new repo from a folder on my Mac |

## Notes to self

- main should stay clean and up to date.
- New work should usually happen on a new branch.
- Commit messages should explain what changed.
- Pull requests are a GitHub feature, not a core Git command.
- Empty folders are not tracked by Git.
- .DS_Store is a macOS file and should be ignored.
- .gitignore tells Git which files not to track.
- git clone is for downloading an existing repo.
- git init is for starting a new repo locally.
- Terminal commands are powerful, so check where I am before creating, moving, or deleting files.
- pwd shows where I am.
- ls shows what is in the current folder.
- cd moves between folders.
- git status is the safest command to run when I am unsure what is going on.

## Why I am doing this

I am learning Git and terminal basics properly so I can better understand developer workflows, work more confidently with code projects, and use tools like Cursor, GitHub, and the terminal without blindly relying on copy-pasted commands.

This repo is my safe place to practise that workflow repeatedly until it becomes second nature.