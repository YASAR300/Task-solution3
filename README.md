Welcome to Git





# Part 1: Creating and Cloning Repositories


## Task 1: Create a Local Git Repository



1. Create a New Project Folder
  The first step is to create a new directory to hold your project. This can be done using the mkdir (make directory) command. For example:

   ```bash
   mkdir MyProject
   cd MyProject
   ```

2. Initialize the Repository
  Once you're inside the folder, you can initialize a new Git repository with the following command:
   ```bash
    git config --list
   ```
   
## Task 2: Initialize a Repository
- Create and initialize a directory as a Git repository:
  ```bash

    git init
  ```  
  This creates a .git folder, which contains all the configuration files, logs, and metadata for your Git repository.

2. Verify the Repository Status
You can check the status of your repository with:



 ```bash
git status

 ```
It will show something like this:


 ```vbnet
On branch main
No commits yet
nothing to commit (create/copy files and use "git add" to track)

 
 ```
 This means there are no files added yet, and the repository is ready to track changes.


## Task 2: Clone a Remote Repository


 2. Clone a GitHub Repository
To clone a remote repository (e.g., from GitHub), you use the git clone command:
 ```bash

 git clone https://github.com/username/repo.git

```
- This command downloads all the files from the remote repository to your local machine.

2. Verify the Cloned Repository Structure
 After cloning, you can check the directory structure of the cloned repository:



 ```bash

cd repo
ls -a


```
The .git folder will be present, indicating it's a Git repository.

# Part 2: Understanding Commits and Commit Messages
## Task 3: Commit Changes Locally
1. Create a New File and Add Content
 For example, create a README.md file:



 ```bash

echo "Welcome to Git" > README.md

```
2. Stage the File

   Before committing a file, you need to stage it with the git add command:



 ```bash

git add README.md
 ```
 This moves the file into the staging area, meaning it's ready to be committed.

3. Commit the Staged File
 
 Now, you can commit the staged file with a message:

 ```bash
git commit -m "Initial commit: Added README.md"

 ```
- This saves the current state of the repository with a message describing the change.

## Task 4: Write Effective Commit Messages

1. Create a Detailed Commit Message
A good commit message should be clear and concise. Here's an example of an improved message:
 ```bash

git commit -m "Added initial version of README.md with project overview"

 ```
2. Commit Multiple Files with One Message

- You can stage and commit multiple files at once:


 ```bash

touch file1.txt file2.txt
git add .
git commit -m "Added two new files for feature setup"

 ```
 This commits all the changes in the current directory.

# Part 3: Viewing Commit History with git log

## Task 5: View Detailed Commit History

1. View Full Commit Logs
The git log command shows the full commit history, with details like the commit hash, author, date, and commit message:

 ```bash
git log

 ```
2. View Commit History in a Compact Format

- To see a concise history, use:

 ```bash

git log --oneline

 ```
 It will show output like this:

  ```sql
  e23d8a7 Added initial #0a192f version of README.md
f7b3c62 Initial commit: Added README.md
 ```

## Task 6: Customize Log Outputs

1. View Logs with Graphical Representation
For a visual representation of the commit history, you can use:

 ```bash

git log --oneline --graph --decorate

 ```
This will display the commit history with a graph showing branches and merges.

2. Filter Logs for a Specific File
If you want to see the commit history for a particular file, you can use:


 ```bash
git log README.md

 ```
 This shows the history of changes made to README.md.


# Part 4: Understanding Branching and Merging
## Task 7: Understanding Branching
1. List All Branches
To see all the branches in your repository, use:




 ```bash
git branch

 ```
 This lists the current branch and any other branches in the repository.

2. Create a New Branch
You can create a new branch with:


 ```bash
git branch feature-branch

 ```
 3. Switch to the New Branch
After creating the branch, you need to switch to it using:
 
 ```bash
git checkout feature-branch

 ```
 Alternatively, you can create and switch to the branch in one command:
  ```bash
     git checkout -b feature-branch
   ```

# Part 5: Creating and Working with Branches

## Task 8: Make Changes in a Branch
1. Add Content to a File in the New Branch
For example, add a new file:

 ```bash
echo "Feature in progress" > feature.txt
git add feature.txt
git commit -m "Added feature.txt in feature-branch"

  ```
## Task 9: Merging Branches

1. Switch Back to the Main Branch
To merge a branch into the main branch, first switch to the main branch:

 ```bash
git checkout main

 ```
2. Merge the Feature Branch into Main
Now, merge the feature branch into the main branch:

 ```bash
git merge feature-branch

 ```
 This will incorporate the changes from feature-branch into main.

# Part 6: Resolving Merge Conflicts

## Task 10: Simulate a Merge Conflict

1. Modify the Same Line in Two Branches
Create conflicting changes in two branches. For example:


- In main, create conflict.txt:

 ```bash
echo "Main branch content" > conflict.txt
git add conflict.txt
git commit -m "Added conflict.txt in main branch"

 ```
- Switch to feature-branch and create a conflicting change:

 ```bash
git checkout feature-branch
echo "Feature branch content" > conflict.txt
git add conflict.txt
git commit -m "Modified conflict.txt in feature-branch"

 ```
2. Merge and Resolve the Conflict

- Try merging the feature branch into main:



 ```bash
git checkout main
git merge feature-branch

 ```
- Git will report a conflict and mark the file for resolution.

3. Resolve the Conflict

- Open conflict.txt and decide which changes to keep. After editing the file, stage the resolved file:

 ```bash
git add conflict.txt

```
4. Commit the Merge
After resolving the conflict, commit the changes:

 ```bash
    git commit -m "Resolved conflict in conflict.txt"
 ```

# Part 7: Deleting and Renaming Branches

## Task 11: Delete a Branch

1. Delete a Local Branch
To delete a local branch that has been fully merged, use:


 ```bash

git branch -d feature-branch

```
2. Force-Delete a Branch
If the branch hasn't been merged, you can force-delete it:

 ```bash

git branch -D feature-branch

```

## Task 12: Rename a Branch
1. Rename the Current Branch
To rename the branch you're currently on:

  ```bash
  git branch -m new-branch-name
  ```
2. Rename Another Branch
If you're not on the branch you want to rename:

   ```bash
   git branch -m old-branch-name new-branch-name
   ```
# Consolidated Flow Summary

- Start by creating and cloning repositories: Create a local Git repository or clone an existing one from a remote server.
- Learn to commit changes effectively with clear messages: Create files, stage changes, and commit them with concise, descriptive messages.
- Explore commit history: Use git log and its variations to view commit history in detail.
- Understand branching and practice creating, switching, and merging branches: Manage feature branches and merge them back into the main branch.
- Resolve merge conflicts: Learn how to handle conflicting changes between branches.
- End by managing branches: Delete or rename branches to keep the repository clean.

