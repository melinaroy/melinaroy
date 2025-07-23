# Git Cheatsheet

Useful Git commands for initializing a repo, managing remotes and submodules, and performing interactive rebases.

## 🛠️ General

```bash
# clone
git clone <url>

# push changes (only pushes if remote hasn't changed since last fetch)
git push --force-with-lease

# apply local commits after the latest origin/main
git rebase origin/main

# reset current branch to match origin/main, discarding all local changes
git reset --hard origin/main

# list all remote branches (fetched but not necessarily tracked locally)
git branch -r

# create and switch to a local branch that tracks the remote one
git checkout feature-x
```

## ✅ Status and staging

```bash
```

## 🔧 Interactive Rebase

```bash
# start interactive rebase
git rebase -i HEAD~2

# inte the intercative editor
edit 123abcd first commit
pick 456efgh second commit

# after editing the code
git add .
git commit --amend
git rebase --continue

# push changes (only pushes if remote hasn't changed since last fetch)
git push --force-with-lease
```

## 🌐 Remote

```bash
# change the remote URL (origin)
git remote set-url origin <new-url>

# add a remote and push an existing repo
git remote add origin <url>
git branch -M main
git push -u origin main
```

## Submodules

```bash
# add submodule
git submodule add <url> <destination_folder>

# initialize and update all submodules
git submodule update --init --recursive

# submodule status
git submodule status

# remove submodule (or remove to change location)
git submodule deinit <submodule_path>
git rm -f <submodule_path>
```
