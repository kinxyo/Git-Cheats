# Git-Cheats
> **Important**
> Replace _filename_ with period (_._) to include all files.<br>
> Examples are wrapped in blockquotes.<br>
> You can add multiple commands in one line by seprating them with semi-colon (_;_)

<br>

## Basics & Commits
#### View All Files (Including Hidden)
```
ls -a
```
#### View Inside Folder:
```
ls _foldername_
```
> ls .git
#### Status of Repository:
```
git status
```
> **Note**
> Unstaged Files are Red.<br>
> Staged Files are Green.
#### Stage Files:
```
git add _filename_
```
#### Unstage Files:
```
git restore --staged _filename_
```
#### Commit file:
```
git commit -m "_yourmessage_"
```
#### View Commit History:
```
git log
```
> **Note**
> Press _q_ to exit it.

<br>

## Recovering files:
### Deleted Files
```
git restore (filename)
```
> **Note**
> Each commit has a commit ID which can be found in [Commit History](#view-commit-history).<br>
> Resetting will unstage all subsequent commits; do a `git stash` prior to save them.
### Restore Point
To reset local repository to a particular point with reference of a commit
```
git reset _commit-id_
```
### Hold/Stall Changes
When you neither want to commit the changes nor lose the them:
```
git stash
```
All staged and unstages changes will be saved to stash. You can bring them back to their respective place by:
```
git stash pop
```
Delete Stash:
```
git stash clear
```

<br>

## Remote Repository
#### Setting Origin
Just like how we assign names to phone numbers in contact list, same way we set origin for identifying repository.
```
git remote add origin _repository-url_
```
#### Pushing to Repo:
```
git push origin _branchname_
```
**When changes between local repo & remote repo aren't synced:**
> git push origin _branchname_ -f
#### View All Repo(s) Associated
```
git remote -v
```
#### Remove all pushed files
```
git rm --cached -r .
```
#### Creating Branch
```
git branch _branchname_
```
#### Switching to Branch
```
git checkout _branchname_
```
> **Note**
> _head ->_ points towards which branch is currently selected
#### Update Changes on Local Repo
```
git fetch --all
git pull origin _branchname_
```
> **Note**
> _-all_ can be replaced with _filename_
#### Merging
```
git checkout _branch-you-wanna-merge-in_
git merge _branch-to-merge_
```

<br>

## Fork
#### Getting Started
```
git clone _forked-repository-url_
git remote add upstream _repository-url_
git branch _branchname_
git checkout _branchname_
```
> **Note**
> Origin will be set by default and will refer to the forked version of original repository & Upstream will refer to the original repository.

#### Merge forked repo with original repo
You can't push to uptream directly so **you'll have to make a _Pull Request_**

#### Updating Changes
1. Automatic
   ```
   git pull upstream _branchname_
   ```
2. Manually
   ```
   git fetch --all --prune
   git checkout _branch-you-wish-to-sync_
   git reset --hard upstream/main
   ```
   > **Note**
   > _--prune_ includes deleted files as well.
