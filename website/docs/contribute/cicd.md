# CI/CD Pipeline

## Trunk-based Development

Trunk-based Development is a streamlined development practice where all developers collaborate on a single branch (here: `master`), and commit their changes frequently. This approach promotes continuous integration, reduces the risk of complex merge conflicts, and encourages faster delivery of features.


### Step 1: Start from the master branch and pull the latest changes
First, ensure that you're working on the latest version of the `master` branch:
```bash
git checkout master
```
This command switches your working directory to the `master` branch, which is the main branch in our trunk-based development workflow.

Next, pull the latest changes from the remote repository:
```bash
git pull origin master
```
This command fetches and integrates changes from the remote `master` branch into your local `master` branch. It ensures that your local branch is up-to-date with any new commits made by other collaborators.


### Step 2: Create a new branch for your feature or bugfix

Now, create a new branch where you can work on your changes without affecting the `master` branch:
```bash
git checkout -b feature-branch
```
This command creates a new branch called `feature-branch` and switches to it. The `-b` flag both creates and checks out the new branch in one step. The new branch is based on the current `master` branch.


### Step 3: Work on your changes, then add and commit them

After making the necessary changes to the code, you'll need to add and commit them:
```bash
git add .
```
This command stages all the changes in your working directory (represented by the .) for the next commit. Staging files tells Git to include them in the next commit.

Next, commit the staged changes with a descriptive message:
```bash
git commit -m "Describe the changes you made"
```
This command creates a new commit with the changes you've staged. The `-m` flag allows you to include a commit message inline, which should clearly describe the changes you’ve made.

### Step 4: Switch back to the master branch

After committing your changes, switch back to the `master` branch:
```bash
git checkout master
```
This command switches your working directory back to the master branch.

### Step 5: Pull the latest changes from the remote master to ensure you're up-to-date

Before merging your changes, it's important to ensure that your `master` branch is up-to-date with the latest changes from the remote repository.
```bash
git pull origin master
```
This command fetches and merges any new commits from the remote `master` branch into your local `master` branch, ensuring it reflects the most current state of the project.

### Step 6: Merge your feature branch into the master branch

Now, merge the changes from your `feature-branch` into the `master` branch.
```bash
git merge feature-branch
```

This command merges the changes from `feature-branch` into the `master` branch. If there are any conflicts, Git will notify you, and you'll need to resolve them before completing the merge.

### Step 7: Push the updated master branch to the remote repository

Finally, push the updated `master` branch with your changes back to the remote repository:
```bash
git push origin master
```
This command uploads your local `master` branch commits to the remote repository, making your changes available to other collaborators.