---
title: Git branches
category: Git
layout: 2017/sheet
updated: 2020-02-13
---

## Working with branches
{: .-three-column}

### 创建分支

```bash
git checkout -b $branchname
git push origin $branchname --set-upstream
```

在本地创建一个新的分支，然后推送它。

### 从远程拉取分支

```bash
git fetch origin
git checkout --track origin/$branchname
```

获取远程仓库中的分支。

### 跟随远端仓库删除本地分支

```bash
git remote prune origin
```

删除本地副本中的分支。不会影响远端分支。

### 查看存在的分支

```bash
git branch --list
```

列出了现有的所有分支。当前分支将用星号突出显示。

### 列表合并分支

```bash
git branch -a --merged
```

列出已经合并到当前分支中的过时分支。

### 删除本地分支

```bash
git branch -d $branchname
```

当前没有修改并且不在 merge 状态时时才删除分支。

### 强制删除分支

```bash
git branch -D $branchname
```

```bash
git branch -d $branchname
```

> Note: 您还可以使用 -D，它是 -delete -force 的缩写，而不是 -d。不管其合并状态如何强行删除分支。
> 删除分支，而不考虑其合并状态。

### 删除远端分支

```bash
git push origin --delete :$branchname
```

对标签也适用!

### 得到 HEAD 指针的 sha1

```bash
git show-ref HEAD -s
```
### 重置分支并删除所有

```bash
git reset --hard
```

### 回退或前进到指定提交

```bash
git reset --hard $commit_id

# 强行推送本地分支到远端
git push --force
```

> Note: 使用 --force 提交可能会覆盖远端分支的内容，请谨慎使用。
