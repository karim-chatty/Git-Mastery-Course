# Git Commands — Browsing Project History

A reference for every command used in this section.

---

## Viewing History

| Command                     | What it does                            |
| --------------------------- | --------------------------------------- |
| `git log`                   | Show full commit history                |
| `git log --oneline`         | One line per commit — clean and compact |
| `git log --oneline --graph` | Visual branch tree in terminal          |
| `git log --oneline --all`   | Show history of all branches            |
| `git log -5`                | Show only last 5 commits                |
| `git log -p`                | Show commits with full diff             |
| `git log --stat`            | Show which files changed per commit     |

---

## Filtering Logs

| Command                               | What it does                              |
| ------------------------------------- | ----------------------------------------- |
| `git log --author="name"`             | Filter commits by author                  |
| `git log --since="2 weeks ago"`       | Commits from last 2 weeks                 |
| `git log --after="2026-01-01"`        | Commits after a specific date             |
| `git log --before="2026-03-01"`       | Commits before a specific date            |
| `git log --grep="keyword"`            | Search commit messages by keyword         |
| `git log -- filename`                 | Show commits that touched a specific file |
| `git log --pretty=format:"%h %an %s"` | Custom formatted output                   |

---

## Viewing a Specific Commit

| Command                    | What it does                              |
| -------------------------- | ----------------------------------------- |
| `git show <hash>`          | Show full details of a specific commit    |
| `git show HEAD`            | Show the latest commit                    |
| `git show HEAD~1`          | Show one commit before the latest         |
| `git show HEAD~2:filename` | Show a specific file at a specific commit |

---

## Comparing Commits

| Command                        | What it does                          |
| ------------------------------ | ------------------------------------- |
| `git diff HEAD~1 HEAD`         | Compare last two commits              |
| `git diff a1b2c3 d4e5f6`       | Compare any two commits               |
| `git diff HEAD~3 HEAD`         | Compare last 3 commits combined       |
| `git diff HEAD~1 HEAD -- file` | Compare specific file between commits |
| `git diff main feature`        | Compare two branches                  |

---

## Finding Bugs — git bisect

| Command                  | What it does                             |
| ------------------------ | ---------------------------------------- |
| `git bisect start`       | Start the bisect session                 |
| `git bisect bad`         | Mark current commit as bad (has the bug) |
| `git bisect good <hash>` | Mark a commit as good (no bug)           |
| `git bisect reset`       | End bisect and go back to HEAD           |

---

## Tracing Changes — git blame

| Command                             | What it does                          |
| ----------------------------------- | ------------------------------------- |
| `git blame filename`                | Show who changed every line of a file |
| `git blame -L 10,20 filename`       | Show only lines 10 to 20              |
| `git blame -e filename`             | Show email instead of name            |
| `git blame filename \| grep "name"` | Find lines changed by specific author |

---

## Commit References

| Reference | What it means           |
| --------- | ----------------------- |
| `HEAD`    | Latest commit           |
| `HEAD~1`  | One commit before HEAD  |
| `HEAD~2`  | Two commits before HEAD |
| `a1b2c3`  | Specific commit by hash |

---

## Quick Reference — Full Workflow

```bash
# View history
git log --oneline

# Find a specific commit
git log --grep="login" --oneline

# Inspect a commit
git show HEAD~1

# Compare two commits
git diff HEAD~1 HEAD

# Find a bug
git bisect start
git bisect bad
git bisect good a1b2c3
git bisect reset

# Trace a line
git blame index.html -L 1,10
```

---

> 💡 `git log --oneline` is your daily driver.
> `git bisect` is your debugging superpower.
> `git blame` is your detective tool.

---

[Back to Browsing Project History](./README.md)

---

**From Learner to Leader**
Made with ❤️ by [Karim Ech-Chatty](https://www.linkedin.com/in/karim-chatty)
