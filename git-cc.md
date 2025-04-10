


# Git Commands and Troubleshooting Guide

## Cloning a Repository

```bash
git clone <repository-url>
```

For example, to clone the Git repository, you would use:
```bash
git clone https://github.com/git/git.git
```

## Branch Operations

### How to checkout Git, create branch, push

1. Switch head branch
```bash
git checkout <branch>
```

2. Create new branch
```bash
git branch <new-branch>
```

3. Create and switch to new branch
```bash
git checkout -b <branch-name>
```

> **Note**: The easiest way to create a Git branch is to use the `git checkout` command with the `-b` option for a new branch.

## Checking Repository Status

```bash
git status
```

## Staging Changes

### Add specific file
```bash
git add <filename>
```

For example, to add a file named index.html:
```bash
git add index.html
git add web.html
```

### Add all changes
```bash
git add -A
# or
git add --all
```

> This will recursively add all changes (new/modified/deleted files) to the staging area.

## Committing Changes

### Basic commit
```bash
git commit -m "commit message"
```

Example:
```bash
git commit -m "Updated index.html"
git commit -m "changes"
```

### Commit all tracked files
```bash
git commit -a
```

## Pushing Changes

### Push to default remote
```bash
git push
```

### Push to specific remote
```bash
git push origin
```

If you encounter:
```
fatal: The current branch akim-gocd has no upstream branch.
To push the current branch and set the remote as upstream, use
    git push --set-upstream origin akim-gocd
```

### Pull changes
```bash
git pull git@github.com:yourrepo/chef.git
```

## Troubleshooting Git Issues

### Git not recognizing changes
```bash
git add <filename>
```

### Merge conflicts
Resolve conflicts manually, then:
```bash
git commit
```

### Pushing to protected branch
Ensure you have proper permissions.

### Authentication issues
Check credentials or set up SSH key.

## Syncing Local Repository

```bash
git fetch origin
git reset --hard origin/master  # change master to your branch
git clean -f -d
git fetch --prune
```

### Sync all in one command
```bash
git fetch origin && git reset --hard origin/master && git clean -f -d
```

## Common Git Commands

### Working with changes
1. Changed files in working directory
```bash
git status
```

2. Changes to tracked files
```bash
git diff
```

3. Add current changes to next commit
```bash
git add .
```

4. Add some changes in file to next commit
```bash
git add -p <file>
```

5. Commit all local changes in tracked files
```bash
git commit -a
git commit -m "comment"
```

6. Commit previously staged changes
```bash
git commit
```

7. Change the last commit
```bash
git commit --amend
```

## Commit History

1. Show all commits
```bash
git log
```

2. Show changes for specific file
```bash
git log -p <file>
```

3. Who changed what and when
```bash
git blame <file>
```

## Branches & Tags

1. List all branches
```bash
git branch -av
```

2. Switch branch
```bash
git checkout <branch>
```

3. Create new branch
```bash
git branch <new-branch>
```

4. Create tracking branch from remote
```bash
git checkout --track <remote/branch>
```

## Git Auto Clone/Pull with Token

```bash
mkdir dir-name
cd dir-name
git init
# For master branch
git pull https://<token>:x-oauth-basic@github.com/<org>/<repo-name>.git

# For specific branch
git clone https://<token>:x-oauth-basic@github.com/<org>/<repo-name>.git --branch=<branch-name> <branch-name>
```

## Switching Git User

### View current user
```bash
git config user.email
```

### Change user
```bash
git config --global user.email "myemail@gmail.com"
```

### Add SSH key
```bash
ssh-add -K ~/.ssh/id_rsa
git clone git@github.com:repo/dummy-test.git
```

## Discarding Changes

### Discard all local changes
```bash
git reset --hard
```

### Remove file from index
```bash
git rm --cached <file>
git reset --hard
```

### Remove folder recursively
```bash
git rm -r --cached <folder>
```

### For tracked files
```bash
git checkout -f
```

### For untracked files
```bash
git clean -fd
```

## Stashing Changes

### Basic stash
```bash
git stash
```

### Stash including untracked files
```bash
git stash -u
```

### Reapply stash
```bash
git stash pop
```

## Important Note

If you get error:
```
fatal: unable to auto-detect email address (got 'xxx')
```

Add to your `~/.gitconfig`:
```ini
[user]
    name = "your name"
    email = "your email as in github"
```

Reference: [Git Comprehensive Guide](https://mytechtrace.com/git-a-comprehensive-guide-to-commands-and-troubleshooting/)
