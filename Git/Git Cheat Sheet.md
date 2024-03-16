
## Git Basic
---

| Command                     | Description                                                                                                                                    |
| --------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| [[git init]]                | Create empty Git repo in specified directory. Run with no arguments to initialise the current directory as a git repository.                   |
| [[git clone]]               | Clone repo located at repo onto local machine. Original repo can be<br>located on the local filesystem or on a remote machine via HTTP or SSH. |
| [[git config user.]]        | Define author name to be used for all commits in current repo. Devs<br>commonly use --global flag to set config options for current user.      |
| [[git add file_name]]       | Stage all changes in directory for the next commit.Replace directory with a file to change a specific file.                                    |
| [[git commit -m "Message"]] | Commit the staged snapshot, but instead of launching a text editor, use message as the commit message.                                         |
| [[git status]]              | List which files are staged, unstaged, and untracked.                                                                                          |
| [[git log]]                 | Display the entire commit history using the default format. For customisation see additional options.                                          |
| [[git diff]]                | Show unstayed changes between your index and working directory.                                                                                |


## Undoing changes
---

| Command                 | Description                                                                                                                                                                                                |
| ----------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [[git revert commit ]]  | Create new commit that undoes all of the changes made in commit, then apply it to the current branch.Create new commit that undoes all of the changes made in commit, then apply it to the current branch. |
| [[git reset file_name]] | Remove file from the staging area, but leave the working directory unchanged. This unstages a file without overwriting any changes.                                                                        |
| [[git clean -n]]        | Shows which files would be removed from working directory. Use the -f flag in place of the -n flag to execute the clean.                                                                                   |

## Rewriting git history
---

| Command                | Description                                                                                                                             |
| ---------------------- | --------------------------------------------------------------------------------------------------------------------------------------- |
| [[git commit --amend]] | Replace the last commit with the staged changes and last commit<br>combined. Use with nothing staged to edit the last commit’s message. |
| [[git rebase base]]    | Rebase the current branch onto base. base can be a commit ID, branch name, a tag, or a relative reference to HEAD.                      |
| [[git reflog]]         | Show a log of changes to the local repository’s HEAD. Add --relative-date flag to show date info or --all to show all refs.             |

## Git Branches
---

| Command                    | Description                                                                                               |
| -------------------------- | --------------------------------------------------------------------------------------------------------- |
| [[git branch]]             | List all of the branches in your repo. Add a branch argument to create a new branch with the name branch. |
| [[git checkout -b branch_name]] | Create and check out a new branch named branch. Drop the -b flag to checkout an existing branch.          |
| [[git merge branch]]       | Merge branch into the current branch.                                                                     |
| [[git branch]]             | Show list branch                                                                                          |

## Remote repositories
---

| Command                     | Description                                                                                                                       |
| --------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| [[git remote add name url]] | Create a new connection to a remote repo. After adding a remote, you can use name as a shortcut for url in other commands.        |
| [[git fetch remote branch]] | Fetches a specific branch, from the repo. Leave off branch to fetch all remote refs.                                              |
| [[git pull remote]]         | Fetch the specified remote’s copy of current branch and immediately merge it into the local copy.                                 |
| [[git push remote branch]]  | Push the branch to remote, along with necessary commits and objects. Creates named branch in the remote repo if it doesn’t exist. |
