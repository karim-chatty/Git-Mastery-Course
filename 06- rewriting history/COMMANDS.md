# Git Commands — Rewriting History

A reference for every command used in this section.

---

## Amending the Last Commit

| Command                        | What it does                              |
| ------------------------------ | ----------------------------------------- |
| `git commit --amend -m "msg"`  | Fix the last commit message               |
| `git commit --amend --no-edit` | Add staged files without changing message |
| `git commit --amend`           | Open editor to change message             |

---

## Interactive Rebase

| Command                 | What it does                                |
| ----------------------- | ------------------------------------------- |
| `git rebase -i HEAD~3`  | Open interactive rebase for last 3 commits  |
| `git rebase -i HEAD~N`  | Open interactive rebase for last N commits  |
| `git rebase --continue` | Continue after resolving a conflict or edit |
| `git rebase --abort`    | Cancel and restore original state           |
| `git rebase --skip`     | Skip conflicting commit and continue        |

---

## Interactive Rebase Commands (inside the editor)

| Command  | What it does                                 |
| -------- | -------------------------------------------- |
| `pick`   | Keep the commit unchanged                    |
| `reword` | Keep commit — edit its message               |
| `edit`   | Pause rebase to edit the commit              |
| `squash` | Combine with previous — keep both messages   |
| `fixup`  | Combine with previous — discard this message |
| `drop`   | Delete this commit entirely                  |

---

## Pushing Rewritten History

| Command                       | What it does                                           |
| ----------------------------- | ------------------------------------------------------ |
| `git push --force`            | Force push — dangerous on shared branches              |
| `git push --force-with-lease` | Safer force push — checks for new remote commits first |

---

## Undoing Without Rewriting

| Command             | What it does                                                  |
| ------------------- | ------------------------------------------------------------- |
| `git revert <hash>` | Undo a commit by creating a new one — safe on shared branches |
| `git reflog`        | See all recent actions including lost commits                 |

---

## Quick Reference — Full Workflow

```bash
# Fix last commit message
git commit --amend -m "correct message"

# Add forgotten file to last commit
git add forgotten.js
git commit --amend --no-edit

# Clean up last 4 commits
git rebase -i HEAD~4
# inside editor:
# pick   a1b2c3d first good commit
# squash d4e5f6g wip
# fixup  g7h8i9j fix typo
# drop   k1l2m3n bad commit

# Continue after editing
git rebase --continue

# Cancel if something goes wrong
git rebase --abort

# Recover lost commits
git reflog
```

---

## When to Use Each Tool

| Situation                   | Command                                         |
| --------------------------- | ----------------------------------------------- |
| Fix last commit message     | `git commit --amend -m "msg"`                   |
| Add forgotten file          | `git add file` + `git commit --amend --no-edit` |
| Clean up N commits          | `git rebase -i HEAD~N`                          |
| Combine messy commits       | `squash` or `fixup`                             |
| Delete a bad commit         | `drop`                                          |
| Fix a specific old commit   | `edit`                                          |
| Undo a pushed commit safely | `git revert <hash>`                             |

---

## The Golden Rule

```
✅ Rewrite BEFORE you push
✅ Rewrite your own private branches
❌ Never rewrite shared branches
❌ Never rewrite commits others have pulled
```

---

> ⚠️ When in doubt — use `git revert` instead of rewriting history.
> It is always safe because it adds a new commit instead of changing old ones.

---

[Back to Rewriting History](./README.md)

---

Made with ❤️ by [Karim Ech-Chatty](https://www.linkedin.com/in/karim-chatty)
