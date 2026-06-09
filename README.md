# \# Git basics









Git Commands Cheatsheet 



🔧 Git Configuration

```

git config --global user.name "Your Name"

git config --global user.email "you@example.com"

```

```

git config --list                     # Show current config

```



📁 Repository Operations

```

git init                                          # Initialize a new Git repo

git clone <repo\_url>                  # Clone an existing repo

```



✅ Basic Workflow

```

git status                              # Show status of working directory

git add <file>                        # Stage a file

git add .                                # Stage all changes

git commit -m "Your message"          # Commit changes

git push                                Push to remote repo

git pull                              # Pull latest changes

```

🌿 Branching

```

git branch                            # List branches

git branch <name>                     # Create new branch

git checkout <name>                   # Switch to branch

git checkout -b <name>                # Create + switch to new branch

git merge <branch>                    # Merge branch into current

git branch -d <name>                  # Delete branch

```



📜 Logs \& History

```

git log                               # Show commit history

git log --oneline                     # Condensed history

git show <commit\_id>                  # Show specific commit

```

🔄 Undo \& Reset

```

git restore <file>                    # Undo changes to a file (unstaged)

git restore --staged <file>          # Unstage a file

git reset <commit\_id>                 # Reset to a specific commit (soft)

git reset --hard <commit\_id>          # Reset and delete changes

```



🔄 Stashing

```

git stash                             # Save changes temporarily

git stash list                        # List stashes

git stash apply                       # Reapply last stash

git stash drop                        # Delete last stash

```



🔗 Remote Repositories

```

git remote -v                         # List remotes

git remote add origin <url>           # Add remote repo

git push -u origin main               # Push and set upstream

```



📄 Tagging

```

git tag                               # List tags

git tag <tag\_name>                    # Create tag

git push origin <tag\_name>            # Push tag to remote

```



🧹 Clean Up

```

git clean -n                          # Preview files to be deleted

git clean -f                          # Delete untracked files



📘 Extra Tips

git diff – View changes not yet staged

git diff --staged – View staged changes

git reflog – View all references (even deleted commits)

```



🔀 Git Merging Commands Cheatsheet

🚀 Basic Merge

```

git merge <branch-name>

Merges <branch-name> into the current branch.

Example:

git checkout main

git merge feature-branch

```



📍 Fast-Forward vs. No Fast-Forward

✅ Fast-Forward (default)

```

git merge <branch>

```

Happens if there's no new commit on the current branch since it branched off.



🛑 No Fast-Forward (preserve history)

```

git merge --no-ff <branch>

```

Forces a merge commit even if fast-forward is possible.



📖 Merge with Commit Message

```

git merge --no-ff -m "Merging feature-branch into main" feature-branch

```



🔄 Abort a Merge

```

git merge --abort

```

Stops the merge and resets to pre-merge state (if conflicts arise).



🧩 Resolving Merge Conflicts

After git merge, Git shows conflicting files:

CONFLICT (content): Merge conflict in <file>

Manually edit the conflicted files to resolve.



After resolving:

```

git add <file>

git commit                      # If not auto-committed

```



🧠 Check for Merge Conflicts Before Merging

```

git merge --no-commit --no-ff <branch>

```





Starts merge but doesn’t create a commit—useful for previewing.

🧪 Check if Branch is Already Merged

```

git branch --merged

git branch --no-merged

```



🧼 Clean Up Merged Branch

```

git branch -d <branch-name>        # Safe delete (only if merged)

git branch -D <branch-name>        # Force delete

```



👀 Visualize Merges (Optional)

```

git log --oneline --graph --all

```



⚡️ Fast-Forward Merge

A fast-forward merge happens when the branch you’re merging can be applied directly to the current branch without needing a new merge commit.

🧠 In Other Words:

Git just moves the pointer forward.

No new commit is created (unless you force it).

This only happens when no new commits exist on the base branch since the branches diverged.



📈 Visual:

Before:

A---B---C (main)

&#x20;        \\

&#x20;         D---E (feature)

After Fast-Forward Merge (main → feature):



A---B---C---D---E (main, feature)

No merge commit is created; the history is linear.



✅ Pros:

Clean, simple commit history.

No extra commits.



❌ Cons:

You lose context that a "merge" actually happened.

Not great for understanding collaboration history.



🚫 No Fast-Forward Merge (--no-ff)

✅ What It Is:

This forces a merge commit, even if a fast-forward is possible.



🧠 In Other Words:

A merge commit is always created.

Preserves the branching structure in history.

📈 Visual:

After No Fast-Forward Merge:

A---B---C-----------G (main)

&#x20;        \\         /

&#x20;         D---E---F (feature)

G is the merge commit, combining both branches.



✅ Pros:

Clear record that a branch was merged.

Easier to trace feature integration.

Preferred in collaborative teams and large projects.

❌ Cons:

Messier history if overused.

Slightly more complex log.



