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


    section KR-使用声音强化冥想,22-11-15,21 days
    强化学习选择语音引导词:2022-12-06,1d
    强化学习选择背景音乐:2022-12-06,1d
    强化学习training:2022-12-07,3d
    强化学习之dataloader:2022-12-09,1d

    采集大量数据，以便训练神经网络:2022-12-13,3d
    使用手机同时采集心率和加速度，放弃，蓝牙的mut受限:done,2022-12-14,1d
    计算PolarH10的冥想得分:done,2022-12-12,2d
    使用polarH10计算冥想得分:done,2022-12-13,1d
    网页读取使用polarh10的加速度，以便获得非常高质量的加速度数据:done,2022-12-12,2d
    分析博能读取加速度计的办法:done,2022-12-11,2d
    dongle解决博能读取加速度数据的设置：购买的设备并不支持:done,2022-12-10,1d


    能正常地记录冥想数据-要求必须先启动设备:done,2022-12-09,1d
    强化学习完成Reward 代码:done,2022-12-06,1d
    完整播放完毕背景音乐:done,2022-12-06,1d
    前端可以不使用背景音乐:done,2022-12-06,1d
    前端可以使用指定的背景音乐:done,2022-12-06,1d
    解决多片段的背景音乐播放的流畅性:done,2022-12-01,3d
    提高背景音乐的质量:done,2022-12-01,1d
    前端使用多片段的背景音乐:done,2022-11-29,1d

    指令也分成以秒为单位:done,2022-11-27,1d
    背景音乐、指令以秒计数后重算vector:done,2022-11-28,1d
    背景音乐ID以秒计数,（约定不管一条指令时间多长，都算一秒，一个操作步骤）:done,2022-11-27,2d


    section devOps改进
    #使用portainer的cicd:2022-11-15,2d
    上传神经网络项目到github:done,2022-12-14,5d
    添加UpdateSchme以便方便地更新struct Schema:done,2022-12-14,1d
    使用dragonflyDB 和AOF,放弃，仅用keydb已经足够:done,2022-12-08,1d
    saavuu 自动配置批访问权限。前三天采用自动配置:done,2022-12-08,1d

##博能读取数据 2021-10-20
# [SDK Mode](https://github.com/polarofficial/polar-ble-sdk/blob/master/technical_documentation/SdkModeExplained.md)
    # 2022-11-11采集lz数据时手机摔坏，淘宝送修
    # 2022-11-12 重新用修复了训练的稳定性。对label-smoothing 的class-weight 添加一个平均权重，避免label-smoothing无效。
    # 2022-11-12 把dataloader的threading number 从24降低到8，解决总是卡死断开的问题。
    # 2022-11-12 把机器内存从48G增加到96G，避免swap导致训练崩溃




    section 推广冥想软件
    各种微信等注册账号的接入:2022-11-15,5d
    bilibili,youtube 等视频发布:2022-11-15,15d
    论坛反馈的预备:2022-11-15,5d

    section 定位推广群体
    可能更适宜婴儿这样没有额外心理活动的群体: cl1,2022-11-20,10d
    
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
    背景音乐市场应该是最佳市场。    最好的背景音乐要求先是具有正念效应，也就是积极的压力，但是稍后有利于提升hrv :2022-11-20,10d
    # 一个手机，可以控制前端网页上的各种操作
    # [emotion control](https://www.frontiersin.org/articles/10.3389/fnins.2019.01131/full)

    section 通过gitpages部署网站
    通过gitpages 部署网站saavuu:2022-12-20,1d 
    git actions 部署网站saavuu:2022-12-20,2d 
    网站回撤机制,docker版本:done,2022-11-20,3d 
    考虑新域名策略，happyhabbi:done,2022-11-13,26d 
    # 2022年11月13日，全天都在琢磨名字
    #基本选定： youthenforce,longyouth,youthforever,youthpower,youthyoung,youthate,uthen,uthate,youthor,youthur,永远年轻的人
    #让我激动：youthate，youthor,backtoyouth,youthbacks✅,iam26,manofrl,backto18✅，18backs✅, backtoyoung
    # youthgeek,youthkeep,youthQ,youngKQ,youthtracker,youthiam,
    # 考虑核心词汇 longevity,refresh
    # 考虑 youngever,youngagain,backtoyouth,backtoyoung,youngAgain,youthub
    # 动词化 youthen,youthwise,youthfy,youthart
    # 前缀 enyouth,enuth,enyoung
    # avalable:uthgeek,uthkeep,uthbit,youthhabit,uthback,uthuth,uthzen,youthback,youthtrace,
    # not avalable:youthgeek,youthbit,youthagain,backtoyouth,youthward

    section 计划外工作
    最近4天采购了万兆交换机和40G交换机。在升级硬件:done,2022-12-02,3d
    完成40G交换机静音配置:done,2022-12-07,1d
    在proxmox服务器中创建keydb虚拟机:done,2022-12-08,1d
    使用keydb+7T保存数据:done,2022-12-08,1d
    编译成功支持flash的keydb:done,2022-11-23,1d
 
```

