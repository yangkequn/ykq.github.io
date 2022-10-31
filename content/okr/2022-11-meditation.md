---
title: "202211_meditation"
date: 2022-11-01T07:17:00+08:00
draft: false
---


``` mermaid
gantt
    title O:实现冥想平台
    dateFormat  YYYY-MM-DD
    excludes    sunday

    section KR：修复hrv的准确性,一周
    hrv 分类预测，结合mse:done,2022-10-30,2d
    预测时的bug,数值剧烈波动:2022-11-01,1d
 
    section KR-使用声音强化冥想
    使用声音强化冥想:2022-10-20,10d
    读取trajectory ogg文件并记录:2022-10-21,3d

    section KR：saavuu框架的改进
    安全性改进，避免扫描攻击：把userInfo,userAuth,改为key-value形式,并存放到单独的db当中:2022-12-15,done,1d 

    section 推广冥想软件
    各种微信等注册账号的接入:2022-10-15,5d
    bilibili,youtube 等视频发布:2022-10-15,15d
    论坛反馈的预备:2022-10-15,5d

    section 定位推广群体
    可能更适宜婴儿这样没有额外心理活动的群体: cl1,2022-10-20,10d
    
    %% 衡量运动疲劳情况，什么时候应该重新运动。https://www.whoop.com/thelocker/heart-rate-variability-hrv/
    #度量所有药品的有效性，例如亚精胺
    #度量作品的欢乐程度
    %% 最粗略的入职体检，快速判断一个人的身体状态。员工每日状态检测。很难作弊的方式判断一个人是否疲劳
    # 搞笑诺贝尔奖中的会约会的人心率会同步。
    #芬兰的产品芬兰Firstbeat心率变异性分析 https://item.taobao.com/item.htm?spm=a230r.1.14.142.20d05a7b6FbkvI&id=680802758929&ns=1&abbucket=16#detail
    #员工情绪变化波动。
    # 健康，死亡率监测 https://www.frontiersin.org/articles/10.3389/fpubh.2017.00258/full04T22
    # 短期harv 和死亡有强关联。需要评估测量。https://www.ahajournals.org/doi/10.1161/01.cir.0000047275.25795.17
    # polar 设备也许可以直接读取HBV     https://www.polar.com/blog/heart-rate-variability-hrv/ https://www.polar.com/vantage/v2 
    # 背景音乐强化
    背景音乐市场应该是最佳市场。    最好的背景音乐要求先是具有正念效应，也就是积极的压力，但是稍后有利于提升hrv :2022-10-20,10d
    # 一个手机，可以控制前端网页上的各种操作
    # [emotion control](https://www.frontiersin.org/articles/10.3389/fnins.2019.01131/full)

    section 通过gitpages部署网站
    通过gitpages 部署网站saavuu:2022-10-20,1d 
    git actions 部署网站saavuu:2022-10-20,2d 
    网站回撤机制:2022-10-20,3d 
    考虑新域名策略，happyhabbi:2022-10-20,1d 
    
```

## 博能读取数据 2021-10-20
 [SDK Mode](https://github.com/polarofficial/polar-ble-sdk/blob/master/technical_documentation/SdkModeExplained.md)
