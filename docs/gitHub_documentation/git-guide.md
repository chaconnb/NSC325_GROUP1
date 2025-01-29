# Git Guide
Git is a free and open source distributed version control system designed to handle everything from small to very large projects with speed and efficiency. Atlassian has a very good [website](https://www.atlassian.com/git/glossary#commands) to help you learn git

### Setting up a local repo
These steps will copy the current state of the remote repository to your local PC. You can
make changes on your local copy and upload them to the remote repository. More details about
cloning a git repository can be found in the [Git documentation](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository). 

Clone the repository to local. 
```console
git clone git@github.com:chaconnb/georules.git
```
### Setting up a local repo for windows + spider
1. Open Git Bash.
2. Create a folder where you want to start your repository.
3. Go to github ->  serach for your repository -> go to <>code (Green button top right corner.) -> Go to HTTPS -> copy your repository's website. In this case:
```console
https://github.com/chaconnb/georules.git
```
4. Open Git Bash and navigate to the folder you created in step 2. Once you're in this folder in Git Bash, clone the repository from GitHub with the following command (notice after git clone you paste what you copied on step 3):
```console
git clone git@github.com:chaconnb/georules.git
```
5. Go to the spider and search for the folder you created in step 2. You should have all the files from the remote repository, and on the console, you should be ready to start interacting with GitHub!

### Setting up a local repo for vscode
1. Create a folder where you want to start your repository.
2. Go to github ->  serach for your repository -> go to <>code (Green button top right corner.) -> Go to HTTPS -> copy your repository's website. In this case:
```console
https://github.com/chaconnb/georules.git
```
3. Open VS code where your folder is (step1)
```console
git clone git@github.com:chaconnb/georules.git
```
5. Initialize the repo:
```console
git init
``` 
   
### Branching
A branch represents an independent line of development. Branches serve as an abstraction for the edit/stage/commit process. You can think of them as a way to request a brand new working directory, staging area, and project history. New commits are recorded in the history for the current branch, which results in a fork in the history of the project.

The `git branch` command lets you create, list, rename, and delete branches. It doesn’t let you switch between branches or put a forked history back together again. For this reason, git branch is tightly integrated with the git checkout and git merge commands.

Some branch commands: 
- `git branch` : list all branches in your local repo. The current branch will be indicated
- `git branch -avv` : list all local and remote branches, with rich description and display
- `git branch -D <branch-name` : delete the specified branch
- `git switch <branch-name>`: switch to the target branch

To create a new branch use the `git checkout -b` command. This will create a new branch and switch to the current branch.

IMPORTANT: To create a branch from the main, go first to the main and create the branch. 
           To create a branch from a branch, go to the branch you want to create the branch from and create the branch. 
```console
git checkout -b "my-new-branch" 
```
IMPORTANT: New branches have to start in lowercase.

IMPORTANT: To see updated branches use:
```console
git pull; git fetch
```
### Making changes to your code. 
To add a file or a change to a file. 
```console
git add <path/to/file>
```
To add multiple files at the same time
```console 
git add file1 file2 file3 
```
or to add using a wildcard (*)
```console 
git add * 
```
> WARNING: This will add everything, should only use if you know what you are doing. 

To commit those changes, and add a comment: 
```console
git commit -m "my commit message" 
```

To push changes from local to remote: 
```console
git push
```
### Updating your local code
If any changes to the remote code are made (like merging a PR, for example), you might want to 
update your local code to match with the changes in the remote repo. To do so, switch to the 
branch you want to update and perform a `git pull` command. 

To pull changes/ update local branch (go to your project in terminal)
1. Go to main
```console
git switch main
```
2. Pull all files to local from github
```console
git fetch; git pull
```

### Deleting Files
To remove a file from git tracking. You need to commit the change after deleting.
```console
git remove <filename>
```
> NOTE: This will delete the local copy of the file.

To remove the file from git tracking, but keep the local copy
```console
git remove --cache <filename>
```

## Git Workflow I
These steps describe a simple git workflow. You can see a visualization of the workflow
in the `./workflow-git.pdf`. 

1. Create a new branch 
```console
git checkout -b 'my-new-branch' 
```
2. Switch to the new branch
```console
git switch my-new-branch
```
3. To run code go to folder where the code is:
  ```console
cd directory's name
cd georules
```
Write python and file's name:
  ```console
python file's name
python M_LRB.py
```
4. Make changes/updates to the code (remember to push changes to the remote branch)
5. Create a "Pull Request" (PR)
6. If the PR can be safely merged into the main branch, merge. 
> **PR merge recommendations**  
> Use squash-merge when merging PRs
> Delete the 'my-new-branch' after the merge to keep branches clean
>

## Git Workflow II - create new branch on local machine

1. Update Main
```console
git switch main
git fetch
git pull
```
2. Create new banch (steps 1 and 2 from Git Workflow I)
3. Suggestion: Create PR to track changes!

## How to create a PR
After creating a new branch on your local, you are ready to create a PR!
1. Make a small change on your local.
2. Add and commit your new change.
3. Then push:
```console
   git push --set-upstream origin 'my-new-branch'
```
4. Go to Pull requests on github and create a new pull request!


## Delete a file from a Git repository 
1. If we want to delete a file and also delete it from local file system:
```console
git rm unwanted-file.txt
```
2. If we want only to delete the file without also deleting it from our local filesystem:
```console
git rm --cached unwanted-file.txt
```
## Basic writing and formating syntax
Visit the [Github docs](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
## Making a new folder on directory
```console
mkdir <Folder Name>
```
## Nice emojis 🧐
https://www.webfx.com/tools/emoji-cheat-sheet/

## VSCode Help 
To open VSCode from the terminal, use: 
```console 
code . 
```
To run cells in a .py file (jupyter notebook), use:

```console 
#%%
```

Remember to open the from the `georules` folder so that VSCode can recognize that this is a git repo. 
(i.e., a folder with a .git directory)