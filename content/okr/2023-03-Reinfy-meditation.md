---
title: "202303_meditation"
date: 2023-03-06T10:44:00+08:00
draft: false
---

``` mermaid
gantt
    title O:实现冥想平台
    dateFormat  YYYY-MM-DD
    excludes    sunday

    section 面向移动版本的调试
    历史页面适配手机:done,2023-03-17,2d
    添加冥想页面适配手机:done,2023-03-16,1d
    开始冥想页面适配手机:done,2023-03-15,1d
    popup login if login needed:done,2023-03-15,1d
    添加菜单，适应不止一个的强化选项。:done,2023-03-14,2d
    
    section 后端改进
    重构saavuu的data和api显示约定名称，并且可以直接通过变量调用:done,2023-03-04,2d
    Hash支持任意类型的Fields:done,2023-03-01,2d

    section 站外冥想内容
    站外内容不使用background music:done,2023-03-12,1d
    添加站外冥想链接:done,2023-03-09,2d
    使用站外冥想链接:done,2023-03-011,2d

    section saavuu后端
    修改saavuu的参数约定更易读:done,2023-03-07,2d

    确定网站的定位，是reinfy还是评价系统，也就是定位人还是定位测试冥想内容受欢迎程度,定位weekChallenge,人为主，结合最好的工具和测量:done,2023-03-06,7d
    
    section 多用户强化机制
    直接使用加速度计，来评估冥想的质量。放弃，只采用心率带来解决:done,2023-03-06,2d
    采集加速度计 数据，polarH10的数据。放弃，只采用心率带来解决:done,2023-03-06,2d
    用polarH10的hrv下降、stdhrv 下降来训练加速度数据的冥想评分。放弃，只采用心率带来解决:done,2023-03-06,2d
    
```

# 确定网站的定位
网站定位在量化一个人的行为表现。并为这种表现提高最好的工具和测量。