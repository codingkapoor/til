## Adding code to existing github repository

- Create a github repository if not already created.

- Initialize the local project directory as a Git repository.
  ```
  $ git init
  ```

- Add the URL for the remote repository where your local repository will be pushed.
  ```
  $ git remote add origin <remote repository URL>
  # Sets the new remote

  $ git remote -v
  # Verifies the new remote URL
  ```

- Pull the latest changes from the remote repository.
  ```
  $ git pull origin master
  ```

- Add the files in your new local repository. This stages them for the first commit.
  ```
  $ git add .
  ```

- Commit the files that you've staged in your local repository.
  ```
  $ git commit -m "your first commit"
  ```

- Push the changes in your local repository to GitHub.
  ```
  $ git push --set-upstream origin master
  ```

## Delete git branch 

```
// locally
git branch -d <branch name>

// remotely
git push origin --delete <branch name>
```

## Git branch descriptions

### Add/Edit

`git branch --edit-description`

### Read

`git config --get branch.{branchName}.description`


## Create a tag

```
git tag <tag name>
```

## Delete a tag

```
git tag --delete v.3.0.0
```

## Delete a remote tag

```
git push --delete origin v6.0.2.75
```

## Push tags created locally
```
git push --tags origin master
```

## Push single tag created locally

```
git push origin <tag name>
```

## Fetch all remote tags

```
git fetch --tags
```

## List changes in stash

```
git stash show -p stash@{0}
```

## List only file names in stash

```
git stash show stash@{0} --name-only
```

## Merge Unrelated Local Remote Repositories

Suppose you have created a repository in github and also an unrelated repository locally with an intent of merging it with the one created in github.

Merging these repositories could be achieved as described below.

### Initialize the local repository as a Git repository.

`$ git init`

### Add the URL for the remote repository where your local repository will be pushed.

```
$ git remote add origin <remote repository URL>
# Sets the new remote

$ git remote -v
# Verifies the new remote URL
```

### Pull the latest changes from the remote repository.
```
$ git pull origin master --allow-unrelated-histories
```

### Add the files in your new local repository. This stages them for the first commit.
```
$ git add .
```

### Commit the files that you've staged in your local repository.
```
$ git commit -m "your first commit"
```

### Push the changes in your local repository to GitHub.
```
$ git push --set-upstream origin master
```

## Most recent commit log with the file names

```
git show --stat 
```

## Other commits

```
git show --stat  HEAD~1
```

## Revert Commit Already Pushed To Github

- Revert the commit already pushed to github.
  ```
  git revert 2473667a14b01fb96758c2a1a85d66acd6fdb42b
  ```

- Rid the changes made in the last commit.
  ```
  git reset --hard HEAD~2
  ```

- Rewrite history.
  ```
  git push -f
  ```

## Revert commit head to second last commit

### Preserve changes

```
git reset HEAD~1 --soft
```

### Rid all changes

```
git reset HEAD~1 --hard
```

## Selectively stash git changes

```
git stash -p
```
