# Git Commands — Collaboration Using GitHub

A reference for every command used in this section.

---

## Connecting to GitHub

| Command                               | What it does               |
| ------------------------------------- | -------------------------- |
| `git remote -v`                       | List all remotes with URLs |
| `git remote add origin <url>`         | Add a new remote           |
| `git remote remove origin`            | Remove a remote            |
| `git remote rename origin upstream`   | Rename a remote            |
| `git remote set-url origin <new-url>` | Change remote URL          |

---

## Pushing & Pulling

| Command                                  | What it does                         |
| ---------------------------------------- | ------------------------------------ |
| `git push -u origin main`                | Push and set upstream (first time)   |
| `git push`                               | Push to tracked remote branch        |
| `git push origin feature-login`          | Push a specific branch               |
| `git push --delete origin feature-login` | Delete a remote branch               |
| `git pull`                               | Fetch and merge in one step          |
| `git pull origin main`                   | Pull from specific remote and branch |
| `git pull --rebase`                      | Fetch and rebase instead of merge    |

---

## Fetching

| Command                         | What it does                         |
| ------------------------------- | ------------------------------------ |
| `git fetch`                     | Download all changes without merging |
| `git fetch origin main`         | Fetch a specific branch              |
| `git log origin/main --oneline` | See fetched commits                  |
| `git diff main origin/main`     | Compare local vs remote              |
| `git merge origin/main`         | Merge fetched changes                |

---

## Cloning

| Command                     | What it does                 |
| --------------------------- | ---------------------------- |
| `git clone <url>`           | Clone a repo to your machine |
| `git clone <url> my-folder` | Clone into a specific folder |
| `git clone -b main <url>`   | Clone a specific branch      |

---

## Working with Forks

| Command                         | What it does                          |
| ------------------------------- | ------------------------------------- |
| `git remote add upstream <url>` | Add original repo as upstream         |
| `git fetch upstream`            | Get latest from original repo         |
| `git merge upstream/main`       | Merge original changes into your fork |

---

## Pull Request Workflow

| Command                           | What it does                    |
| --------------------------------- | ------------------------------- |
| `git switch -c feature-name`      | Create feature branch           |
| `git push -u origin feature-name` | Push branch to GitHub           |
| `git switch main`                 | Go back to main after PR merged |
| `git pull`                        | Get merged changes locally      |
| `git branch -d feature-name`      | Delete local feature branch     |

---

## Handling Remote Conflicts

| Command                         | What it does                           |
| ------------------------------- | -------------------------------------- |
| `git pull origin main --rebase` | Pull and rebase to avoid merge commits |
| `git rebase --continue`         | Continue after resolving conflict      |
| `git rebase --abort`            | Cancel the rebase                      |
| `git push`                      | Push after resolving conflict          |

---

## Quick Reference — Full Collaboration Workflow

```bash
# Start of work session — always pull first
git pull origin main

# Create a feature branch
git switch -c feature-name

# Work on your feature
git add .
git commit -m "your message"

# Push to GitHub
git push -u origin feature-name

# Open PR on GitHub, get review, merge

# After merge — clean up
git switch main
git pull
git branch -d feature-name
```

---

## Remote Conflict Fix — Quick Reference

```bash
git pull origin main --rebase
# resolve conflicts if any
git push
```

---

> 💡 Pull before you work. Push when you are done.
> Never push directly to main. Always use branches and PRs.

---

[Back to Collaboration Using GitHub](./README.md)

---

**From Learner to Leader**
Made with ❤️ by [Karim Ech-Chatty](https://www.linkedin.com/in/karim-chatty)
