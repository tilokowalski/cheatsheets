# Git Feature Branch Workflow

This cheatsheet provides a comprehensive overview of Git operations for managing a feature branch, along with essential Git concepts.

## Basic Git Concepts

### Understanding 'origin'
- 'origin' is the default name for the remote repository from which your local repository is cloned. It's an alias for the remote repository URL.
- When you clone a repository, Git automatically sets this remote repository as 'origin'.
- Commands like `git pull origin develop` and `git push origin develop` use 'origin' to refer to this remote repository. 
  - **Pulling Changes**: `git pull origin develop` fetches and merges changes from the 'develop' branch of the 'origin' into your current branch.
  - **Pushing Changes**: `git push origin develop` sends your branch's changes to the 'develop' branch on 'origin'.

### Local vs Remote Branches
- Local branches exist on your machine and become public when pushed to a remote repository.
- Remote branches are on the remote server, accessible to anyone with access to the repository.

### Committing vs Pushing
- Committing (`git commit`) saves changes to your local repository.
- Pushing (`git push`) sends your commits to a remote repository.

### Fetching vs Pulling
- **Fetching** (`git fetch`): Downloads updates from a remote repository but doesn't merge them.
- **Pulling** (`git pull`): A combination of fetching and merging. It fetches updates and immediately merges them.

## Managing a Feature Branch

Note: All commands are executed in the context of the current branch you are on.

### Creating and Switching Branches
- **Create Feature Branch**: `git checkout -b feature/[feature-name] develop`
- **Switch Between Branches**: `git checkout [branch-name]`

### Adding and Committing Changes
- **Add Changes**: `git add [file-or-directory]`
- **Commit Changes**: `git commit -m '[commit message]'`

### Pushing and Pulling Changes
- **Push to Remote**: `git push origin feature/[feature-name]`
- **Pull from Develop**: `git pull origin develop` (a combination of `git fetch origin develop` and `git merge origin/develop`)
- **Fetch and Merge**: `git fetch origin` followed by `git merge origin/develop`

### Rebasing vs Merging
- **Rebasing**: `git rebase origin/develop`
  - Reapplies changes from your branch onto the latest `develop`.
  - Creates a clean, linear history.
- **Merging**: `git merge origin/develop`
  - Combines the histories of the feature and `develop` branches.
  - Preserves the exact history of changes.

### Handling Conflicts
- Conflicts may arise during merge or rebase.
- Manually resolve conflicts and continue with `git merge --continue` or `git rebase --continue`.

### Finalizing the Feature Branch
- **Create Pull Request**: Push your branch, afterwards create a pull request from `feature/[feature-name]` to `develop` for review (on your hosting service, e.g. GitHub).
- **Review and Merge**: Once the pull request is approved, it can be merged into `develop`.
- **Delete Local Feature Branch**: After merging, delete the local branch with `git branch -d feature/[feature-name]`

