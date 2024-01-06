## Table of Contents
- [add](#add)
- [commit](#commit)

## add
1. **`git add .`**
   - Adds all changes in the working directory to the staging area, including modifications, deletions, and new files.
   ```bash
   git add .
   ```
   
2. **`git add *`**:
    - Adds all files in the current directory to the staging area.
    ```bash
    git add *
    ```

3. **`git add *.c`**:
   - Adds all files with a ".c" extension in the current directory to the staging area.
   ```bash
   git add *.c
   ```

4. **`git add -A` or `git add --all`**:
    - Adds changes from all tracked and untracked files to the staging area.
    ```bash
    git add -A
    ```

2. **`git add -p` or `git add --patch`**
   - Interactively adds changes to the staging area, allowing you to review and selectively choose which changes to include.
   ```bash
   git add --patch
   ```

4. **`git add -i`**:
   - Invokes the interactive mode, providing a menu to choose various actions, including adding changes, reverting changes, updating changes, showing status and diffrence, and patch. It's a more comprehensive interactive interface compared to `git add -p`
   ```bash
   git add -i
   ```

5. **`git add -n` or `git add --dry-run`**
   - Shows what would be added to the staging area without actually adding or modifying any files.
   ```bash
   git add -n
   ```

6. **`git add -v` or `git add --verbose`**
   - Displays detailed information about each file being added to the staging area.
   ```bash
   git add -v
   ```

7. **`git add -e` or `git add --edit`**:
   - Opens the editor to edit the index or the specified files before committing.
   ```bash
   git add -e
   ```

8. **`git add -f` or `git add --force`**:
    - Allows adding files that are otherwise ignored by Git (e.g., files listed in `.gitignore`).
    ```bash
    git add -f file_to_add.txt
    ```

9. **`git add -u` or `git add --update`**:
    - Adds changes only to already tracked files. It does not include untracked files.
    ```bash
    git add -u
    ```

10. **`git add --renormalize`**:
    - Updates the index and working directory to reflect changes in line endings. It implies `-u`.
    ```bash
    git add --renormalize
    ```

11. **`git add -N` or `git add --intent-to-add`**:
    - Records only the fact that a path will be added later. It stages the path without its content.
    ```bash
    git add -N new_file.txt
    ```

12. **`git add --refresh`**:
    - Doesn't add files but refreshes the index, useful if you want to update the staging area without adding new changes.
    ```bash
    git add --refresh
    ```

13. **`git add --ignore-removal`**:
    - Ignores paths removed in the working tree, similar to `git add --all`.
    ```bash
    git add --ignore-removal
    ```

14. **`git add --ignore-errors`**:
    - Ignores errors encountered while adding files and continues with the remaining files.
    ```bash
    git add --ignore-errors
    ```

## commit 
1. **`git commit -m "initial commit"`**
   - Commits the changes you've made with a brief commit message.
   ```bash
   git add .
   git commit -m "initial commit"
   ```

2. **`git commit -a -m "my message"`**
   - Commits all changes (including modifications and deletions) without the need for `git add` first.
   ```bash
   git commit -a -m "my message"
   ```

3. **`git commit -am "my message"`**
   - Combines the effects of `-a` (automatically stage modified and deleted files) with the `-m` flag to provide a commit message.
   ```bash
   git commit -am "my message"
   ```

4. **`git commit -a -S -m "signed commit"`**
   - Commits changes with a GPG (GNU Privacy Guard) signature for added security (if GPG signing is set up). The `-S` flag signs the commit.
   ```bash
   git commit -a -S -m "signed commit"
   ```

5. **`git commit --amend`**
   - Modifies the last commit by adding staged changes or editing the commit message.
   ```bash
   git commit -am "initial commit"
   git add forgotten_file
   git commit --amend -m "first commit"
   ```

6. **`git commit --amend --no-edit`**
   - Modifies the last commit without changing the commit message.
   ```bash
   git add new_changes
   git commit --amend --no-edit
   ```

7. **`git commit --no-verify`**
   - Commits changes without running pre-commit or commit-msg hooks. It allows you to bypass pre-commit checks.
   ```bash
   git commit --no-verify
   ```

8. **`git commit --allow-empty -m "my message"`**
   - Commits an empty change with a message. Useful in scenarios where you want to trigger a CI/CD pipeline.
   ```bash
   git commit --allow-empty -m "my message"
   ```

## branch
### Create branch
1. **`git branch mybranch`:**
   - Creates a new branch named "mybranch".
   ```bash
   git branch mybranch
   ```

2. **`git branch mybranch ab1afef`:**
    - Creates a new branch named "mybranch" starting from the commit with hash "ab1afef."
    ```bash
    git branch mybranch ab1afef
    ```

3. **`git branch mybranch remotes/origin/opera`:**
    - Creates a new local branch named "mybranch" that tracks the remote branch "origin/opera."
    ```bash
    git branch mybranch remotes/origin/opera
    ```

### Delete a branch
1. **`git branch -d mybranch`:**
   - Deletes the branch "mybranch" if its changes have been merged. Use `-d` for a safe delete.
   ```bash
   git branch -d mybranch
   ```

2. **`git branch -D mybranch`:**
   - Forces the deletion of the branch "mybranch," even if changes are not merged.
   ```bash
   git branch -D mybranch
   ```

### List branches
1. **`git branch`:**
   - Lists all local branches.
   ```bash
   git branch
   ```

2. **`git branch -a` or `git branch --all`:**
    - Lists all local and remote branches.
    ```bash
    git branch --all
    ```

3. **`git branch -v`:**
   - Lists all local branches with additional information (last commit message and hash).
   ```bash
   git branch -v
   ```

4. **`git branch -vv`:**
    - Lists local branches with information about their upstream branches.
    ```bash
    git branch -vv
    ```

5. **`git branch --merged`:**
   - Lists branches that have been merged into the current branch.
   ```bash
   git branch --merged
   ```

6. **`git branch --no-merged`:**
   - Lists branches that have not been merged into the current branch.
   ```bash
   git branch --no-merged
   ```

7. **`git branch --no-merged master`:**
   - Lists branches that haven't been merged into the "master" branch.
   ```bash
   git branch --no-merged master
   ```

### Rename branch
1. **`git branch --move bad-branch-name corrected-branch-name`:**
   - Renames a branch from "bad-branch-name" to "corrected-branch-name."
   ```bash
   git branch --move bad-branch-name corrected-branch-name
   ```

2. **`git branch --move master main`:**
    - Renames the local branch "master" to "main."
    ```bash
    git branch --move master main
    ```

### Track branch
1. **`git branch -u origin/serverfix`:**
    - Sets up the tracking branch for the current branch to track the remote branch "serverfix" on the "origin" remote.
    ```bash
    git branch -u origin/serverfix
    ```
