# Git Commands Guide

## Commits & Logs 🚨🚨

- **`git add <file name>`** 📂  
  Move the specified file to the staging area.

- **`git add .`** 📂  
  Move all files to the staging area.

- **`git commit -m "MSG"`** 💾  
  Save changes with a commit message.

- **`git init`** 🆕  
  Initialize a new Git repository.

---

## Log & Status

- **`git status`** 📊  
  Show the current status of the files in the working directory.

- **`git log`** 📜  
  Show the commit log of the current repository or branch.

---

## Removing Commits

- **`git reset (--hard || --soft) HEAD~N`** 🔄  
  Remove the last N commits:  
  - `--hard`: Discard changes in the working directory.  
  - `--soft`: Keep changes in the working directory.

- **`git reset <commit ID>`** ⏪  
  Revert to a specific commit if you deleted a commit by mistake.

- **`git reflog`** 🕒  
  Show the history of all actions, including commits that were reset.

- **`git reset --hard <commit ID>`** 🔄  
  Reset to a specific commit using its ID.

---

## Checkout

- **`git checkout <commit ID>`** ⏩  
  Move to the state of the project at the specified commit.

- **`git checkout <branch name>`** 🌿  
  Switch to the specified branch.

---

## Branching 🚨🚨

### Types of Branches

- **Local branch** 🏠: Exists in your local repository.
- **Remote branch** 🌐: Exists in the remote repository.
- **Remote tracking branch** 🔄: A copy of the remote branch used for merging.
- **Local tracking branch** 📡: Local branches that track remote branches with `-u`.

---

### Branch Commands 🔻

- **`git branch`** 🌿  
  Show local branches only.

- **`git branch <branch name>`** 🌿  
  Create a new branch.

- **`git checkout <branch name>`** 🌿  
  Switch to the specified branch.

- **`git checkout -b <branch name>`** 🌿  
  Create and switch to a new branch in one step.

- **`git switch <branch name>`** 🔄  
  Switch to another branch.

- **`git switch -c <branch name>`** 🔄  
  Create and switch to a new branch in one step.

---

### Show Branches

- **`git branch`** 🌿  
  Show local branches only.

- **`git branch -a`** 🌿  
  Show all branches (local and remote).

- **`git branch -r`** 🌿  
  Show remote branches only.

---

### Publish Branch

- **`git push origin <branch name>`** 🌐  
  Push a branch to the remote repository.

---

### Fetch Updates

- **`git fetch`** 🔄  
  Fetch updates from the remote repository.

---

## Delete Branch

- **`git branch -d <branch name>`** 🗑️  
  Try to delete a specified branch (only works if merged).

- **`git branch -D <branch name>`** 🗑️  
  Force delete a specified branch.

- **`git push origin --delete <branch name>`** 🗑️  
  Delete a branch from the remote repository.

---

### Restore Deleted Branch

- **`git checkout <commit ID>`** ⏩  
  Move to the last commit of the deleted branch.

- **`git reflog`** 🕒  
  Get the commit ID of the deleted branch.

- **`git switch -c <branch name>`** 🔄  
  Create a new branch from the commit ID.

---

### Rename Branch

- **`git branch -M <new branch name>`** ✏️  
  Rename a branch.

---

### Remote Repository

- **`git remote add origin <repo link>`** 🌐  
  Link the local repository to a remote repository.

- **`git push -u origin main`** 🌐  
  Push changes to the remote repository and set up tracking.

---

## Rebase 🚨🚨

- **`git switch <branch name>`** 🔄  
  Switch to the branch you want to rebase.

- **`git rebase <source branch>`** 🔄  
  Rebase the current branch onto the source branch.

---

## Cherry-pick 🚨🚨

- **`git cherry-pick <commit ID>`** 🍒  
  Apply changes from a specific commit to the current branch.

---

## Miscellaneous 🚨🚨

- **`git ls-files`** 📂  
  Show tracked files that have been moved to the staging area.

- **`git status`** 📊  
  Show the current state of tracked and untracked files.

---

## Stashing 🚨🚨

- **`git stash`** 📦  
  Temporarily save changes.

- **`git stash list`** 📋  
  Show a list of saved changes.

- **`git stash apply`** 📦  
  Restore saved changes.

- **`git stash pop`** 📦  
  Restore and delete the most recent saved change.

---

## Pulling Changes 🚨🚨

- **`git pull`** 🔄  
  Fetch updates from the remote repository and merge them into the local repository.

---

## GitHub 🚨🚨

- **`git clone <repo link>`** 📥  
  Clone a repository from the remote repository.

---

## Corrections

- To restore a deleted commit, use `git reflog` to find its ID, then use `git checkout <commit ID>`.

---

## Tags 📌

- **Add a Tag with Description**:  
  **`git tag -a <tag_name> -m "description"`** 📜  
  Add additional information, such as a description, to the tag.

- **Push Tags**:  
  **`git push origin <tag_name>`** 🌐  
  Push a specific tag to the remote repository.

- **List Tags**:  
  **`git tag`** 📋  
  Display all the tags in the repository.

---

## Submodules 📂

- **Add a Submodule**:  
  **`git submodule add <repo_url> <path>`** 📥  
  Include another repository as a submodule within the current repository.

- **Update Submodules**:  
  **`git submodule update --init --recursive`** 🔄  
  Ensure all submodules are updated to their latest version.

- **Remove a Submodule**:  
  Delete the submodule directory. Remove the submodule entry from `.gitmodules` and `.git/config`.

---

## Resolving Conflicts 🛠️

- **During a Merge Conflict**:  
  Open the conflicting files and edit to resolve the conflict.

- **Mark the file as resolved**:  
  **`git add <file_name>`** 📂

- **Complete the merge**:  
  **`git commit`** 💾

---

## Rewriting History ✍️

- **Interactive Rebase**:  
  **`git rebase -i <base_commit>`** 🔄  
  Modify commits before the `<base_commit>`. Use it carefully to avoid altering shared history.

- **Amend Last Commit**:  
  **`git commit --amend -m "new message"`** ✏️  
  Edit the most recent commit message or add changes.

---

## Workflows 🛠️

### Feature Branch Workflow:

1. **Create a new branch for a feature**:  
   **`git checkout -b feature/<feature_name>`** 🌿

2. **Work on the feature and commit changes**.

3. **Merge the feature branch into the main branch**:  
   **`git checkout main`** 🌐  
   **`git merge feature/<feature_name>`** 🔄

4. **Delete the feature branch**:  
   **`git branch -d feature/<feature_name>`** 🗑️
