# Git Commands — Branching & Merging

A reference for every command used in this section.

---

## Working with Branches

| Command                           | What it does                       |
| --------------------------------- | ---------------------------------- |
| `git branch`                      | List all local branches            |
| `git branch -a`                   | List all branches including remote |
| `git branch feature-login`        | Create a new branch                |
| `git switch feature-login`        | Switch to an existing branch       |
| `git switch -c feature-login`     | Create and switch in one command   |
| `git checkout -b feature-login`   | Old way — create and switch        |
| `git branch -d feature-login`     | Delete a merged branch safely      |
| `git branch -D feature-login`     | Force delete a branch              |
| `git branch -m old-name new-name` | Rename a branch                    |

---

## Merging

| Command                            | What it does                                          |
| ---------------------------------- | ----------------------------------------------------- |
| `git merge feature-login`          | Merge a branch into current branch                    |
| `git merge --no-ff feature-login`  | Force a merge commit even if fast-forward is possible |
| `git merge --abort`                | Abort a merge in progress                             |
| `git merge --squash feature-login` | Combine all branch commits into one before merging    |

---

## Resolving Conflicts

| Command             | What it does                                 |
| ------------------- | -------------------------------------------- |
| `git status`        | Show which files have conflicts              |
| `git add filename`  | Mark a conflict as resolved                  |
| `git commit`        | Complete the merge after resolving conflicts |
| `git merge --abort` | Cancel the merge and go back to before       |

---

## Rebasing

| Command                 | What it does                                 |
| ----------------------- | -------------------------------------------- |
| `git rebase main`       | Replay current branch commits on top of main |
| `git rebase --abort`    | Cancel a rebase in progress                  |
| `git rebase --continue` | Continue after resolving a rebase conflict   |
| `git rebase --skip`     | Skip a conflicting commit during rebase      |

---

## Viewing Branches

| Command                           | What it does                              |
| --------------------------------- | ----------------------------------------- |
| `git log --oneline --graph --all` | Visual history of all branches            |
| `git branch --merged`             | List branches already merged into current |
| `git branch --no-merged`          | List branches not yet merged              |

---

## Quick Reference — Full Branch Workflow

```bash
# 1. Create and switch to new branch
git switch -c feature-login

# 2. Work on your feature
git add .
git commit -m "add login form"

# 3. Go back to main
git switch main

# 4. Merge the feature
git merge feature-login

# 5. Delete the branch (cleanup)
git branch -d feature-login

# 6. View result
git log --oneline --graph
```

---

## Conflict Markers Reference

```
<<<<<<< HEAD
your version (current branch)
=======
incoming version (branch being merged)
>>>>>>> feature-login
```

**Steps to resolve:**

1. Open the file
2. Remove ALL markers (`<<<<<<<`, `=======`, `>>>>>>>`)
3. Keep the correct final code
4. `git add filename`
5. `git commit`

---

> 💡 Always create a branch before starting any feature.
> Never work directly on main.
> Never rebase shared branches.

---

[Back to Branching & Merging](./README.md)

---

**From Learner to Leader**
Made with ❤️ by [Karim Ech-Chatty](https://www.linkedin.com/in/karim-chatty)
