📘 Git Basics – Cheatsheet
🔧 Git Configuration
git config --global user.name "Your Name"
git config --global user.email "you@example.com"

git config --list          # View all configuration settings
📁 Repository Operations
git init                   # Initialize a new repository
git clone <repo_url>      # Clone an existing repository
✅ Basic Workflow
git status                # Check repository status
git add <file>           # Stage a file
git add .                # Stage all changes

git commit -m "message"   # Commit changes
git push                 # Push changes to remote
git pull                 # Pull latest changes
🌿 Branching
git branch               # List branches
git branch <name>        # Create new branch
git checkout <name>      # Switch branch
git checkout -b <name>   # Create + switch branch

git merge <branch>       # Merge branch into current
git branch -d <name>     # Delete branch
📜 Logs & History
git log                  # Full commit history
git log --oneline        # Short history
git show <commit_id>     # Show specific commit
🔄 Undo / Reset
git restore <file>             # Undo unstaged changes
git restore --staged <file>    # Unstage file

git reset <commit_id>          # Soft reset to commit
git reset --hard <commit_id>   # Hard reset (destructive)
🔄 Stashing
git stash              # Save changes temporarily
git stash list         # List stashes
git stash apply        # Apply last stash
git stash drop         # Delete last stash
🔗 Remote Repositories
git remote -v                  # Show remotes
git remote add origin <url>    # Add remote repo

git push -u origin main        # Push and set upstream
📄 Tagging
git tag                        # List tags
git tag <name>                # Create tag
git push origin <tag_name>    # Push tag
🧹 Cleanup
git clean -n   # Preview untracked files to delete
git clean -f   # Delete untracked files
📘 Useful Extras
git diff              # Unstaged changes
git diff --staged     # Staged changes
git reflog            # Full reference history
🔀 Git Merge Cheatsheet
🚀 Basic Merge
git checkout main
git merge feature-branch
📍 Fast-Forward Merge
git merge <branch>

✔ Happens when no new commits exist on main
✔ Moves pointer forward
✔ No merge commit created

🛑 No Fast-Forward Merge
git merge --no-ff <branch>

✔ Always creates a merge commit
✔ Preserves branch history

🧩 Merge with Message
git merge --no-ff -m "Merge feature branch" feature-branch
🔄 Abort Merge
git merge --abort
⚠️ Resolve Conflicts
# Fix files manually
git add <file>
git commit
👀 Preview Merge
git merge --no-commit --no-ff <branch>
🧼 Branch Cleanup
git branch -d <branch>   # Safe delete
git branch -D <branch>   # Force delete
📊 Visual History
git log --oneline --graph --all
⚡ Advanced Git Concepts (Session Notes)
📌 Session-74 (14-AUG-2025)
🔹 Git Reset
Moves HEAD to a specific commit
Can be soft, mixed, or hard
git reset --soft <commit>
git reset --hard <commit>
🔹 Git Revert
Creates a new commit that undoes changes
git revert <commit>

✔ Safe for shared repositories

🔹 Git Squash
Combines multiple commits into one
git rebase -i HEAD~n

✔ Clean commit history

🔹 Git Stash
Temporarily stores uncommitted work
git stash
git stash pop
🔹 Git Cherry-Pick
Apply a specific commit from another branch
git cherry-pick <commit>