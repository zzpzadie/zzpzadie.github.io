---
title: 'el-tree'
date: '2024-6-26 17:46:00'
description: 'el-tree'
cover: "./image/haibiantian.jpg"
categories:
- [vue3,el-tree]
------
# 树的展开
## 展开所有
```bash

                <el-form-item label="">
                  <el-checkbox v-model="menuExpand" @change="handleCheckedTreeExpand($event, 'menu')">展开/折叠
                  </el-checkbox>
                  <el-checkbox v-model="menuNodeAll" @change="handleCheckedTreeNodeAll($event, 'menu')">全选/全不选
                  </el-checkbox>
                  <el-checkbox v-model="form.menuCheckStrictly" @change="handleCheckedTreeConnect($event, 'menu')">父子联动
                  </el-checkbox>
                  <el-tree
                      class="tree-border"
                      :data="menuOptions"
                      show-checkbox
                      ref="menuRef"
                      node-key="id"
                      empty-text="暂无数据源"
                      :check-strictly="!form.menuCheckStrictly"
                      :props="{ label: 'label', children: 'children' }"
                  ></el-tree>
                </el-form-item>
#                /** 树权限（展开/折叠）*/
function handleCheckedTreeExpand(value, type) {
  console.log(value)
  if (type == "menu") {
    console.log(menuRef.value.store._getAllNodes())
    for (let i = 0; i < menuRef.value.store._getAllNodes().length; i++) {
      menuRef.value.store._getAllNodes()[i].expanded = value;
    }
  } else if (type == "dept") {
    let treeList = deptOptions.value;
    for (let i = 0; i < treeList.length; i++) {
      deptRef.value.store.nodesMap[treeList[i].id].expanded = value;
    }
  }
}
```

## 展开第一层级

```bash
/** 树权限（展开/折叠）*/
function handleCheckedTreeExpand(value, type) {
  if (type == "menu") {
    let treeList = menuOptions.value;
    for (let i = 0; i < treeList.length; i++) {
      menuRef.value.store.nodesMap[treeList[i].id].expanded = value;
    }
  } else if (type == "dept") {
    let treeList = deptOptions.value;
    for (let i = 0; i < treeList.length; i++) {
      deptRef.value.store.nodesMap[treeList[i].id].expanded = value;
    }
  }
}
```
## 展开指定层级

```bash
function handleCheckedTreeExpand(value, type) {
  if (type == "menu") {
    let treeList = menuOptions.value;
    // for (let i = 0; i < menuRef.value.store._getAllNodes().length; i++) {
    //   menuRef.value.store._getAllNodes()[i].expanded = value;
    // }
    for (let i = 0; i < treeList.length; i++) {
      menuRef.value.store.nodesMap[treeList[i].id].expanded = value;
      if (treeList[i].children) {
        for (let j = 0; j < treeList[i].children.length; j++) {
          if(treeList[i].children[j].children){
            menuRef.value.store.nodesMap[treeList[i].children[j].id].expanded = value;
          }
        }
      } else {

      }
    }
```
