# Learning Git

This repository is my personal practice space for learning Git, GitHub, and eventually general terminal commands.

The aim is not to build a production project. The aim is to practise the basic developer workflow in a safe place, make mistakes, fix them, and get comfortable using Git from the command line.

## What this repo is for

I am using this repo to practise:

- Initialising a Git repository
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

Right now, I am focusing on the basics of Git:

bash git init git status git add . git commit -m "Describe the change" git log git checkout main git checkout -b branch-name git push -u origin branch-name git pull origin main 

## Future focus

Once I am more comfortable with Git, I may expand this repo to include notes and practice examples for general terminal usage, including:

- Creating files and folders
- Moving around the file system
- Reading and editing files
- Understanding paths
- Using common macOS terminal commands
- Running local development projects
- Understanding ports, local servers, and development environments

## Practice workflow

A typical practice workflow in this repo is:

bash git checkout main git pull origin main git checkout -b my-new-branch 

Then make a change to a file.

bash git status git add . git commit -m "Describe what changed" git push -u origin my-new-branch 

Then open GitHub, create a pull request, review the change, and merge it into main.

After merging:

bash git checkout main git pull origin main git branch -d my-new-branch 

## Notes to self

- main should stay clean and up to date.
- New work should usually happen on a new branch.
- Commit messages should explain what changed.
- Pull requests are a GitHub feature, not a core Git command.
- Empty folders are not tracked by Git.
- .DS_Store is a macOS file and should be ignored.
- .gitignore tells Git which files not to track.

## Why I am doing this

I am learning Git properly so I can better understand developer workflows, work more confidently with code projects, and use tools like Cursor, GitHub, and the terminal without blindly relying on copy-pasted commands.