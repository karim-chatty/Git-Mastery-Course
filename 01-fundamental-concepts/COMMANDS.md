# Git Commands — Fundamental Concepts

A reference for every command used in this section.

---

## Configuring Git

| Command                                            | What it does                          |
| -------------------------------------------------- | ------------------------------------- |
| `git config --global user.name "Your Name"`        | Set your name for all commits         |
| `git config --global user.email "you@example.com"` | Set your email for all commits        |
| `git config --global core.editor "code --wait"`    | Set VSCode as default editor          |
| `git config --list`                                | Show all your current config settings |

---

## Starting a Repository

| Command      | What it does                                              |
| ------------ | --------------------------------------------------------- |
| `git init`   | Initialize a new Git repo in current folder               |
| `git status` | Show the state of your working directory and staging area |

---

## Working Directory

| Command      | What it does                                       |
| ------------ | -------------------------------------------------- |
| `git status` | See which files are untracked, modified, or staged |
| `git diff`   | Show exactly which lines changed in unstaged files |

---

## Staging Area

| Command                         | What it does                                      |
| ------------------------------- | ------------------------------------------------- |
| `git add filename`              | Stage a specific file                             |
| `git add .`                     | Stage all changed files at once                   |
| `git add -p`                    | Stage changes interactively line by line          |
| `git diff --staged`             | Show what is staged and ready to commit           |
| `git restore --staged filename` | Unstage a file, keep changes in working directory |

---

## Repository

| Command                   | What it does                                        |
| ------------------------- | --------------------------------------------------- |
| `git commit -m "message"` | Save staged snapshot with a message                 |
| `git commit --amend`      | Edit the last commit message or add forgotten files |
| `git restore filename`    | Undo changes in working directory from last commit  |

---

## Viewing History

| Command                         | What it does                                 |
| ------------------------------- | -------------------------------------------- |
| `git log`                       | Show full commit history                     |
| `git log --oneline`             | Show one line per commit — clean and compact |
| `git log --oneline --graph`     | Visual branch tree in terminal               |
| `git log -5`                    | Show only last 5 commits                     |
| `git log --author="Karim"`      | Show commits by specific author              |
| `git log --since="2 weeks ago"` | Show commits from last 2 weeks               |
| `git show <hash>`               | Show full details of a specific commit       |
| `git diff HEAD~1 HEAD`          | Compare last two commits                     |

---

## Quick Reference — Full Workflow

```bash
# 1. Start
git init

# 2. Check state
git status

# 3. Stage files
git add filename
git add .

# 4. Review what is staged
git diff --staged

# 5. Commit
git commit -m "your message"

# 6. View history
git log --oneline
```

---

> 💡 When in doubt, run `git status` — it always tells you what to do next.

---

**From Learner to Leader**
Made with ❤️ by [Karim Ech-Chatty](https://www.linkedin.com/in/karim-chatty)
