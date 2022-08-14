---
title: "react 拖拽组件的比较"
date: 2021-04-09T17:10:16+08:00
draft: false
---

## react drag and drop 插件的选择

### ract-dnd
#### 优点
* 用的人似乎很多
#### 缺点
* 需要指定两个后端


### react-sortable-hoc
#### 优点
* 似乎用起来的接口比较简单

#### 缺点
* 无法为可以被拖动的组件添加事件，提示需要设置为passive event
2021-04-08 花了一天的时间最后在github的issue 上确认了插件没有引入这个特性，暂时是无法解决的问题

#### react-beautiful-dnd
#### 缺点
* 文档接口杂乱，demo不能查看对应的源码

#### 优点
* 实际上该有的文档，连视频教程都有
* 源码和demo的入口位于：[ https://github.com/atlassian/react-beautiful-dnd/blob/master/docs/about/examples.md](https://github.com/atlassian/react-beautiful-dnd/blob/master/docs/about/examples.md " https://github.com/atlassian/react-beautiful-dnd/blob/master/docs/about/examples.md")
* 似乎各种后端都能良好支持，如作者所言，抽象度高
* 能支持键盘操作
