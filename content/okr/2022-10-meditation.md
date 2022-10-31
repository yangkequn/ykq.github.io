---
title: "202210_meditation"
date: 2022-10-04T09:30:00+08:00
draft: false
---


``` mermaid
gantt
    title O:实现冥想平台
    dateFormat  YYYY-MM-DD
    excludes    sunday

    section KR：修复hrv的准确性,一周
    基于hrv数据的数据采集:done,2022-10-23,1d
    # 本日，2022-10-243090 gpu 驱动故障，无法使用，到2022-10-25 早上修复
    使用简单的监督训练同时预测hr、hrv:done,2022-10-25,3d
    放弃：使用vit神经网络来更有效提取特征,少量数据residual更加:done,2022-10-24,1d
    更新计算冥想得分,采用std 比对:done,2022-10-28,2d
    修改hrv 为分类预测，可以更好捕获hrv:done,2022-10-29,2d
    hrv 分类预测，结合mse:2022-10-30,2d
    更新计算冥想得分显示:done,2022-10-29,1d
    
    section KR：修复hrv的准确性时间时间漂移，现在仅当重启服务，丢失状态时候，才会恢复准确性
    从博能H10中读取原始的心率:done,2022-10-20,3d
    放弃：搞明白，什么是streaming 传输:done,2022-10-25,5d
    放弃：建立监听后，能否实时收到每秒数据，还是说只能批量读取一次数据:done,2022-10-30,5d
    放弃：是否有必要编译安卓应用并且调试:done,2022-11-05,5d
    放弃：从追踪h10源码中的characteristic 入手:done,2022-11-10,5d

    


    section KR：hrv准确性优化
    使用更底层的特征匹配，使得算法神经网络准确可靠计算HRV值,放弃，没有可靠的理论依据:done,2022-10-15,2d
    使用传统算法来强化修正HRV,已放弃，接收深度学习的预测为可靠值:done,2022-10-09,3d
    显示hrv 的变化:done,2022-10-09,10d
    在后端计算hrv的变化:done,2022-10-11,1d
    使用热图算法神经网络准确可靠计算HRV值，放弃，算法太过复杂:done,022-10-13,5d
    预测通过心率周期，构造目标心率图形，可靠计算HRV值，效果良好:done,2022-10-16,1d
    预测注意力掩码，通过注意力掩码可靠计算HRV值,放弃，太过复杂:done,2022-10-16,2d
    训练神经网络的序列读取每个Batch时，引入随机偏移:done,2022-10-17,1d
    训练神经网络的序列长度可变:done,2022-10-17,1d
    要求高级特征必须直接反应原始特征:done,2022-10-17,1d
    添加额外的维度，x^2+y^2+z^2:done,2022-10-17,1d
    加入原始心率图形与预期目标心率波形的比较,使用更底层的特征比对,放弃，同样无法对高级特征构建可学习梯度:done,2022-10-17,1d
    加入原始心率图形与预期目标心率波形的比较,放弃，无法构建梯度:done,2022-10-17,1d
    谷歌浏览器，缺点时的点序号校准:done,2022-10-18,1d
    将神经网络心率调准确，舍弃17日中的过于复杂的心率波形计算:done,2022-10-18,1d
    data corrupt when using data augmentation :done,2022-10-19,1d
    修正bug,使用mse而不是log_prob来作为hr的loss !极大地修复了准确性:done,2022-10-19,1d

    section KR：saavuu框架的改进
    安全性改进，避免扫描攻击：把userInfo,userAuth,改为key-value形式,并存放到单独的db当中:2022-12-15,done,1d 
    已放弃：saavuu中的Delete，Get 等操作，jwt也放入数据，给每个服务来处理,放弃，考虑Jwt安全性:done,2022-10-09,4d

    section 使用声音强化冥想
    使用声音强化冥想:2022-10-20,10d
    读取trajectory ogg文件并记录:2022-10-21,3d

    section KR：用户习惯榜单
    显示冥想得分，和得分排行榜,后端:done,2022-10-11,2d
    显示冥想得分，和得分排行榜,前端:done,2022-10-13,2d



    section 改进冥想软件
    使用摄像头来作为监督心率信号，放弃，摄像头太烫，稳定性太差:done,2022-10-06,1d
    1.能准确预测heart_rate:done,2022-10-07,2d
    2.可靠反应hrv的变化:done,2022-10-07,2d
    2.要求hiddenstate 能还原出波形分布:done,2022-10-07,2d

    采集高精度加速度计数据，来自蓝牙信号（效果不佳）:done,2022-10-05,1d
    采集高精度加速度计数据，来自firefox信号:done,2022-10-05,1d    


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

 #说明
 2022年10月27日用proxmox 重装开发服务器，并迁移开发服务器
 2022年10月28日.放弃proxmox的虚拟机备份计划，改用vmware的自动快照