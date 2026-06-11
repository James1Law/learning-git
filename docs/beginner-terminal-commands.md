# Beginner Terminal Commands for Coding on macOS

This guide is a practical cheat sheet for using the terminal while learning coding, Git, GitHub, Cursor, npm projects, and local development.

The aim is not to memorise everything. The aim is to recognise the commands, understand what they roughly do, and know which ones are safe to practise.

## 1. What the terminal is

The terminal is a text-based way to control your computer.

Instead of clicking folders and files in Finder, you type commands.

For coding, the terminal is useful because you can:

- Move around project folders
- Create files and folders
- Run Git commands
- Install packages
- Start local development servers
- Open projects in Cursor or VS Code
- Check errors and logs

## 2. The prompt

You may see something like this:

```bash
jameslaw@Jamess-Mac-mini learning-git %
```

That is your terminal prompt.

It usually tells you:

- Your username: `jameslaw`
- Your computer name: `Jamess-Mac-mini`
- Your current folder: `learning-git`
- That the terminal is ready for a command: `%`

You do not type the prompt itself. You only type the command after it.

## 3. Where am I?

### Print working directory

```bash
pwd
```

This shows the full path of the folder you are currently in.

Example output:

```bash
/Users/jameslaw/LocalProjects/learning-git
```

Think of it as asking:

> Where am I right now?

## 4. List files and folders

### Basic list

```bash
ls
```

Shows files and folders in your current folder.

### Detailed list

```bash
ls -la
```

Shows more detail, including hidden files.

Useful because Git and macOS use hidden files, such as:

```bash
.git
.gitignore
.DS_Store
```

### List a specific folder

```bash
ls markdown
```

Shows what is inside the `markdown` folder.

## 5. Move around folders

### Change directory

```bash
cd folder-name
```

Moves into a folder.

Example:

```bash
cd learning-git
```

### Go up one level

```bash
cd ..
```

Moves up one folder.

Example:

If you are here:

```bash
/Users/jameslaw/LocalProjects/learning-git
```

Then:

```bash
cd ..
```

moves you to:

```bash
/Users/jameslaw/LocalProjects
```

### Go to your home folder

```bash
cd ~
```

or just:

```bash
cd
```

This takes you back to your user home folder:

```bash
/Users/jameslaw
```

### Go to a full path

```bash
cd /Users/jameslaw/LocalProjects
```

This moves directly to that location.

### Go back to the previous folder

```bash
cd -
```

This switches back to the last folder you were in.

## 6. Create folders

### Make a directory

```bash
mkdir folder-name
```

Example:

```bash
mkdir markdown
```

Creates a folder called `markdown`.

### Create nested folders

```bash
mkdir -p notes/git
```

This creates both folders if they do not already exist:

```bash
notes/
  git/
```

The `-p` means:

> Create parent folders as needed, and do not complain if they already exist.

## 7. Create files

### Create an empty file

```bash
touch README.md
```

Creates an empty file called `README.md`.

If the file already exists, `touch` updates its modified time but does not usually change the contents.

### Create a file with one line of text

```bash
echo "# Learning Git" > README.md
```

This creates `README.md` and puts this text inside it:

```markdown
# Learning Git
```

Important: `>` overwrites the file.

### Add a line to the end of a file

```bash
echo "Another note" >> README.md
```

Important: `>>` appends to the file instead of replacing it.

## 8. Read files in the terminal

### Print a whole file

```bash
cat README.md
```

Shows the full contents of the file in the terminal.

Good for small files.

### Read a file page by page

```bash
less README.md
```

Useful for longer files.

Inside `less`:

- Press `Space` to move down
- Press `b` to move back up
- Press `q` to quit

### Show the first few lines

```bash
head README.md
```

Shows the start of a file.

### Show the last few lines

```bash
tail README.md
```

Shows the end of a file.

This is useful for logs.

## 9. Open files and folders

### Open current folder in Finder

```bash
open .
```

The `.` means:

> The current folder.

### Open a specific file

```bash
open README.md
```

Opens the file using the default app.

### Open a project in Cursor

If the `cursor` command is installed:

```bash
cursor .
```

This opens the current folder in Cursor.

### Open a project in VS Code

If the `code` command is installed:

```bash
code .
```

This opens the current folder in VS Code.

## 10. Copy, move, and rename

### Copy a file

```bash
cp README.md README-copy.md
```

Creates a copy of `README.md` called `README-copy.md`.

### Copy a folder

```bash
cp -R notes notes-copy
```

Copies a folder and everything inside it.

The `-R` means recursive, meaning:

> Include the folder contents too.

### Move a file

```bash
mv README.md notes/README.md
```

Moves `README.md` into the `notes` folder.

### Rename a file

```bash
mv old-name.md new-name.md
```

There is no separate rename command. You use `mv`.

## 11. Delete files and folders

Be careful with delete commands. The terminal does not always give you a nice undo button.

### Delete a file

```bash
rm old-file.md
```

Deletes the file.

### Delete an empty folder

```bash
rmdir old-folder
```

Only works if the folder is empty.

### Delete a folder and everything inside it

```bash
rm -r old-folder
```

This deletes the folder and its contents.

Use with care.

### Dangerous command to avoid casually

```bash
rm -rf folder-name
```

This force deletes a folder and everything inside it.

Do not use this unless you are absolutely sure what it will delete.

## 12. Useful shortcuts

### Stop a running command

```bash
Ctrl + C
```

Use this when something is running and you want to stop it.

Common example: stopping a local development server.

### Clear the terminal screen

```bash
clear
```

Or press:

```bash
Ctrl + L
```

This does not delete anything. It just clears the visible terminal screen.

### Re-run previous commands

Press the up arrow key:

```text
↑
```

This cycles through previous commands.

### Autocomplete

Press `Tab` while typing a file or folder name.

Example:

```bash
cd LocalP
```

Press `Tab` and it may autocomplete to:

```bash
cd LocalProjects
```

## 13. Paths

A path is the location of a file or folder.

### Current folder

```bash
.
```

Means:

> Here.

Example:

```bash
open .
```

### Parent folder

```bash
..
```

Means:

> One folder up.

Example:

```bash
cd ..
```

### Home folder

```bash
~
```

Means your user home folder.

Example:

```bash
cd ~/LocalProjects
```

That means:

```bash
cd /Users/jameslaw/LocalProjects
```

## 14. Find files and text

### Find files by name

```bash
find . -name "README.md"
```

Searches from the current folder downwards for files called `README.md`.

### Find text inside files

```bash
grep "Git" README.md
```

Searches for the word `Git` inside `README.md`.

### Search recursively inside a folder

```bash
grep -R "Git" .
```

Searches for `Git` in files in the current folder and subfolders.

## 15. Check command location and version

### Where is this command installed?

```bash
which git
```

Shows where the `git` command is coming from.

### Check Git version

```bash
git --version
```

### Check Node version

```bash
node -v
```

### Check npm version

```bash
npm -v
```

These are useful when setting up coding projects.

## 16. Environment variables and secrets

You may see files like:

```bash
.env
```

These often contain API keys, passwords, or project settings.

Do not commit `.env` files to GitHub.

A common `.gitignore` entry is:

```gitignore
.env
```

## 17. Package/project commands you will see often

These depend on the project, but they are common in JavaScript/React projects.

### Install project dependencies

```bash
npm install
```

or:

```bash
npm i
```

### Start a local development server

```bash
npm run dev
```

You may then see something like:

```bash
http://localhost:5173
```

or:

```bash
http://localhost:3000
```

That means the app is running locally on your Mac.

### Stop the local server

Press:

```bash
Ctrl + C
```

## 18. Commands that pair well with Git

### Check where you are before running Git commands

```bash
pwd
ls
```

### Check whether the folder is a Git repo

```bash
ls -la
```

If you see this folder:

```bash
.git
```

then you are inside a Git repository.

### Open the current repo in Finder

```bash
open .
```

### Open the current repo in Cursor

```bash
cursor .
```

## 19. Safe practice routine

Use this to practise terminal basics:

```bash
pwd
ls
mkdir terminal-practice
cd terminal-practice
touch notes.md
echo "# Terminal Practice" > notes.md
cat notes.md
mkdir examples
mv notes.md examples/notes.md
ls examples
cd ..
```

Then, if you want to clean it up:

```bash
rm -r terminal-practice
```

## 20. Beginner command summary

| Command | Meaning |
|---|---|
| `pwd` | Show where you are |
| `ls` | List files and folders |
| `ls -la` | List files, including hidden ones |
| `cd folder` | Move into a folder |
| `cd ..` | Move up one folder |
| `cd ~` | Go to your home folder |
| `mkdir folder` | Create a folder |
| `mkdir -p a/b` | Create nested folders |
| `touch file.md` | Create an empty file |
| `echo "text" > file.md` | Create/overwrite a file with text |
| `echo "text" >> file.md` | Add text to the end of a file |
| `cat file.md` | Print a file in the terminal |
| `less file.md` | Read a file page by page |
| `open .` | Open current folder in Finder |
| `cp file copy` | Copy a file |
| `mv old new` | Move or rename |
| `rm file` | Delete a file |
| `rm -r folder` | Delete a folder and its contents |
| `clear` | Clear the terminal screen |
| `Ctrl + C` | Stop a running command |
| `which command` | Show where a command is installed |
| `command --version` | Show a command version, when supported |

## 21. Important mindset

Do not blindly paste terminal commands if you do not roughly understand them.

Before pressing Enter, ask:

- What folder am I currently in?
- Is this command creating, changing, moving, or deleting something?
- Is this command safe to run?
- Does it affect only this project, or my whole computer?

The most useful beginner habit is running this often:

```bash
pwd
ls
git status
```

Those three commands tell you where you are, what is there, and what Git thinks is happening.
