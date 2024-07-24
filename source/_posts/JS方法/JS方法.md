---
title: 'JS方法'
date: '2024-7-4 10:22:00'
description: 'JS的一些数据处理方法'
cover: "./image/haibiantian.jpg"
categories:
  - [JS,JS方法]
---

# 生成随机#409EFF这样的颜色参数
```bash
function generateRandomColor() {
  const r = Math.floor(Math.random() * 256);
  const g = Math.floor(Math.random() * 256);
  const b = Math.floor(Math.random() * 256);
  return '#' + r.toString(16).padStart(2, '0') + g.toString(16).padStart(2, '0') + b.toString(16).padStart(2, '0');
}
```

# 时间戳1717201004000转换为'2021-06-18'格式
```bash
function formatTimestamp(timestamp) {
  const date = new Date(timestamp / 1000);
  const isoString = date.toISOString();
  const year = isoString.slice(0, 4);
  const month = isoString.slice(5, 7);
  const day = isoString.slice(8, 10);
  return `${year}-${month}-${day}`;
}
```
# 对象返回数组(只包含值，不包含键)
```bash
#Object.values(groupedData) 是一个JavaScript表达式，用于获取对象 groupedData 中所有属性的值，并将它们作为数组返回。
#例如，假设我们有以下对象：
const groupedData = {
  key1: 'value1',
  key2: 'value2',
  key3: 'value3'
};
    
#使用 Object.values(groupedData) 将返回一个数组，包含这些键对应的值：
['value1', 'value2', 'value3']
```
# 日期字符串转换为时间戳（从1970年1月1日00:00:00 UTC（协调世界时）到该日期的毫秒数）
```bash
Date.parse(item.startTime)
```
#  Date(val) 是 JavaScript 中用于创建一个新的日期对象的构造函数。它接受一个参数 val，该参数可以是以下几种类型：

字符串：表示日期的字符串，如 "2022-08-15" 或 "August 15, 2022"。
数字：表示从1970年1月1日00:00:00 UTC开始的毫秒数。
多个数字：分别表示年、月、日、小时、分钟、秒和毫秒。
包含日期组件的对象：具有年份、月份、日期、小时、分钟、秒和毫秒属性的对象。
例如：


```bash
// 使用字符串创建日期对象
var date1 = new Date("2022-08-15");
console.log(date1); // 输出：Tue Aug 15 2022 00:00:00 GMT+0800 (中国标准时间)

// 使用毫秒数创建日期对象
var date2 = new Date(1628956800000);
console.log(date2); // 输出：Tue Aug 15 2022 00:00:00 GMT+0800 (中国标准时间)

// 使用多个数字创建日期对象
var date3 = new Date(2022, 7, 15, 12, 30, 45);
console.log(date3); // 输出：Mon Aug 15 2022 12:30:45 GMT+0800 (中国标准时间)

// 使用包含日期组件的对象创建日期对象
var date4 = new Date({year: 2022, month: 7, day: 15, hour: 12, minute: 30, second: 45});
console.log(date4); // 输出：Mon Aug 15 2022 12:30:45 GMT+0800 (中国标准时间)

```
