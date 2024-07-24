---
title: 'Echart-xAxis. axisLabel'
date: '2024-7-8 10:50:00'
description: 'tooltips遇到的问题汇总'
cover: "./image/haibiantian.jpg"
categories:               
    - [Echart,xAxis,axisLabel]
---
*  显示

```bash
show: true,
```
* 标签高度(整个图不够高时可以给grid加height)

```bash
      height: 45,
```
*  标签换行：换行字符串之间加 + "\n" +

```bash
     formatter: function (val) {
        let date = new Date(val);
        let year = date.getFullYear();
        let month = date.getMonth() + 1; // 月份是从0开始的，所以要加1
        let day = date.getDate();
        let hours = ("0" + date.getHours()).slice(-2);
        let minutes = ("0" + date.getMinutes()).slice(-2);
        let seconds = ("0" + date.getSeconds()).slice(-2);
        let laststring = `${hours}:${minutes}:${seconds}` + "\n" + `${year}/${month}/${day}`
        return laststring;
      },
```
![](./image/axisLabel.png)
