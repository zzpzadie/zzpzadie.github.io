---
title: 'stash'
date: '2024-7-17 15:17:00'
description: 'stash的使用'
cover: "./image/haibiantian.jpg"
categories:               
    - Git

---

### 相关命令：

```bash
# 保存当前未commit的代码
git stash

# 保存当前未commit的代码并添加备注
git stash save "备注的内容"

# 列出stash的所有记录
git stash list

# 删除stash的所有记录
git stash clear

# 应用最近一次的stash
git stash apply

# 应用最近一次的stash，随后删除该记录
git stash pop

# 删除最近的一次stash
git stash drop
```

### 当有多条 stash，可以指定操作stash，首先使用stash list 列出所有记录：

```bash
git stash list
#效果：
stash@{0}: WIP on ...
stash@{1}: WIP on ...
stash@{2}: On ...
```
### 应用第二条记录：
```bash
git stash apply stash@{1}
```
