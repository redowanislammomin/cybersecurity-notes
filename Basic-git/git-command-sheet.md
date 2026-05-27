# Git Command Cheat Sheet

A quick reference for the most commonly used Git commands.

---

## Setup & Config

```bash
git config --global user.name "Your Name"       # Set your name
git config --global user.email "you@email.com"  # Set your email
git config --global core.editor nano            # Set default editor
git config --list                               # View all config settings
```

---

## Starting a Repository

```bash
git init                    # Initialize a new local repo
git clone <url>             # Clone a remote repo locally
git clone <url> my-folder   # Clone into a specific folder name
```

---

## Staging & Committing

```bash
git status                  # Show working tree status
git add <file>              # Stage a specific file
git add .                   # Stage all changes
git add -p                  # Interactively stage chunks (patch mode)
git commit -m "message"     # Commit with a message
git commit -am "message"    # Stage tracked files + commit in one step
git commit --amend          # Edit the last commit (message or content)
```

---

## Branching

```bash
git branch                  # List local branches
git branch -a               # List all branches (local + remote)
git branch <name>           # Create a new branch
git checkout <branch>       # Switch to a branch
git checkout -b <branch>    # Create and switch to a new branch
git switch <branch>         # Modern way to switch branches
git switch -c <branch>      # Create and switch (modern syntax)
git branch -d <branch>      # Delete a branch (safe)
git branch -D <branch>      # Force delete a branch
git branch -m <old> <new>   # Rename a branch
```

---

## Merging & Rebasing

```bash
git merge <branch>          # Merge a branch into current branch
git merge --no-ff <branch>  # Merge with a merge commit (no fast-forward)
git merge --abort           # Abort an in-progress merge
git rebase <branch>         # Rebase current branch onto another
git rebase -i HEAD~3        # Interactive rebase — last 3 commits
git rebase --abort          # Abort a rebase
git rebase --continue       # Continue after resolving conflicts
```

---

## Remote Repos

```bash
git remote -v                        # List remotes with URLs
git remote add origin <url>          # Add a remote named "origin"
git remote remove <name>             # Remove a remote
git remote rename <old> <new>        # Rename a remote
git push origin <branch>             # Push branch to remote
git push -u origin <branch>          # Push and set upstream tracking
git push --force-with-lease          # Force push (safer than --force)
git pull                             # Fetch + merge from upstream
git pull --rebase                    # Fetch + rebase instead of merge
git fetch                            # Download changes, don't merge
git fetch --prune                    # Fetch and remove stale remote refs
```

---

## Viewing History & Diffs

```bash
git log                     # Full commit history
git log --oneline           # Compact one-line log
git log --oneline --graph   # Visual branch graph
git log -n 5                # Last 5 commits
git log --author="name"     # Commits by a specific author
git log -- <file>           # Commits that touched a file
git diff                    # Unstaged changes
git diff --staged           # Staged changes (vs last commit)
git diff <branch1>..<branch2>  # Diff between two branches
git show <commit>           # Show a specific commit's changes
git blame <file>            # Show who changed each line
```

---

## Undoing Changes

```bash
git restore <file>              # Discard unstaged changes in a file
git restore --staged <file>     # Unstage a file (keep changes)
git reset HEAD~1                # Undo last commit, keep changes staged
git reset --soft HEAD~1         # Undo last commit, keep changes in working tree
git reset --hard HEAD~1         # Undo last commit, DISCARD all changes
git revert <commit>             # Create a new commit that undoes a commit
git clean -fd                   # Remove untracked files and directories
```

>  `reset --hard` is destructive. Use `revert` on shared/public branches.

---

## Stashing

```bash
git stash                   # Stash current uncommitted changes
git stash push -m "label"   # Stash with a descriptive label
git stash list              # List all stashes
git stash pop               # Apply latest stash and remove it
git stash apply stash@{2}   # Apply a specific stash (keep it)
git stash drop stash@{0}    # Delete a specific stash
git stash clear             # Delete all stashes
```

---

## Tags

```bash
git tag                         # List all tags
git tag v1.0.0                  # Create a lightweight tag
git tag -a v1.0.0 -m "message"  # Create an annotated tag
git push origin v1.0.0          # Push a specific tag
git push origin --tags          # Push all tags
git tag -d v1.0.0               # Delete a local tag
git push origin --delete v1.0.0 # Delete a remote tag
```

---

## Cherry-Pick

```bash
git cherry-pick <commit>        # Apply a specific commit to current branch
git cherry-pick A..B            # Apply a range of commits
git cherry-pick --no-commit <commit>  # Apply changes without committing
```

---

## Common Combos / Workflows

```bash
# Start a feature branch, work, and push
git checkout -b feature/my-feature
git add . && git commit -m "feat: add my feature"
git push -u origin feature/my-feature

# Sync your branch with main before pushing
git fetch origin
git rebase origin/main

# Undo a bad push (only on your own branches!)
git reset --hard HEAD~1
git push --force-with-lease

# See what changed in the last commit
git show HEAD

# Find which commit introduced a bug (binary search)
git bisect start
git bisect bad                  # Current commit is bad
git bisect good <commit>        # Known good commit
# Git checks out commits for you to test — mark each as good/bad
git bisect reset                # End bisect session
```

---

## .gitignore Tips

```gitignore
# Ignore a file
secret.env

# Ignore a folder
node_modules/
dist/

# Ignore all .log files
*.log

# But track this one
!important.log
```

```bash
git rm --cached <file>      # Stop tracking a file (already committed)
git check-ignore -v <file>  # Debug why a file is ignored
```

---

## Quick Reference Card

| Task | Command |
|---|---|
| Init repo | `git init` |
| Stage all | `git add .` |
| Commit | `git commit -m "msg"` |
| Push | `git push` |
| Pull | `git pull` |
| New branch | `git checkout -b <name>` |
| Merge branch | `git merge <name>` |
| View log | `git log --oneline` |
| Discard changes | `git restore <file>` |
| Stash work | `git stash` |
| View remotes | `git remote -v` |

---

*Generated as a quick reference — for full docs visit [git-scm.com/docs](https://git-scm.com/docs)*
