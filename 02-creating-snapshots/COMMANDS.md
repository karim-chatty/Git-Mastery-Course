# Git Commands — Creating Snapshots

A reference for every command used in this section.

---

## Initializing a Repository

| Command      | What it does                                                         |
| ------------ | -------------------------------------------------------------------- |
| `git init`   | Initialize a new empty Git repository in current folder              |
| `ls -a`      | List all files including hidden — confirms `.git` folder was created |
| `git status` | Check the state of your repo after initializing                      |

---

## Tracking & Staging Files

| Command                         | What it does                                        |
| ------------------------------- | --------------------------------------------------- |
| `git add filename`              | Stage one specific file                             |
| `git add .`                     | Stage all changed and new files at once             |
| `git add *.js`                  | Stage all files with a specific extension           |
| `git add -p`                    | Stage changes interactively chunk by chunk          |
| `git restore --staged filename` | Unstage a file — keeps changes in working directory |

---

## Making a Commit

| Command                    | What it does                                        |
| -------------------------- | --------------------------------------------------- |
| `git commit -m "message"`  | Save staged snapshot with a descriptive message     |
| `git commit --amend`       | Edit the last commit message or add forgotten files |
| `git commit -am "message"` | Stage all tracked files and commit in one step      |

---

## Ignoring Files

| Command                      | What it does                                                 |
| ---------------------------- | ------------------------------------------------------------ |
| `touch .gitignore`           | Create a new `.gitignore` file                               |
| `echo ".env" >> .gitignore`  | Add `.env` to `.gitignore` from the terminal                 |
| `git rm --cached filename`   | Untrack a file that was already committed — keeps it locally |
| `git rm --cached -r folder/` | Untrack an entire folder that was already committed          |

---

## Viewing Status

| Command         | What it does                                    |
| --------------- | ----------------------------------------------- |
| `git status`    | Show state of all files across the three stages |
| `git status -s` | Short version — compact one line per file       |

---

## Viewing Differences

| Command                  | What it does                               |
| ------------------------ | ------------------------------------------ |
| `git diff`               | Show unstaged changes in working directory |
| `git diff --staged`      | Show staged changes ready to commit        |
| `git diff HEAD`          | Show all changes since last commit         |
| `git diff HEAD~1 HEAD`   | Compare last two commits                   |
| `git diff a1b2c3 d4e5f6` | Compare any two specific commits           |
| `git diff filename`      | Show changes in a specific file only       |

---

## Quick Reference — Full Workflow

```bash
# 1. Initialize repo
git init

# 2. Create or edit files
touch index.html

# 3. Check state
git status

# 4. Stage files
git add index.html
git add .

# 5. Review staged changes
git diff --staged

# 6. Commit
git commit -m "add homepage"

# 7. Check history
git log --oneline

# 8. See what changed
git diff HEAD~1 HEAD
```

---

## .gitignore Patterns

| Pattern          | What it ignores                     |
| ---------------- | ----------------------------------- |
| `*.log`          | All files ending in `.log`          |
| `folder/`        | Entire folder and its contents      |
| `.env`           | Specific file named `.env`          |
| `!important.log` | Exception — do NOT ignore this file |
| `/config.js`     | Only in root folder, not subfolders |
| `**/*.log`       | All `.log` files in all subfolders  |

---

> 💡 When in doubt, run `git status` — it always tells you where your files are and what to do next.

---

[Back to Creating Snapshots](./README.md)

---

**From Learner to Leader**
Made with ❤️ by [Karim Ech-Chatty](https://www.linkedin.com/in/karim-chatty)
