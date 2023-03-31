---
title: "202301_meditation"
date: 2023-01-01T10:44:00+08:00
draft: false
---


``` mermaid
gantt
    title O:实现冥想平台
    dateFormat  YYYY-MM-DD
    excludes    sunday


    section reinfy前后端重构
    读取hrv放入后端:done,2023-02-01,1d
    hrv的波动区间锁定:done,2023-02-01,1d

    section saavuu 框架优化
    统一pipeline读取service:done,2023-01-30,1d
    saavuu使用pubsub来降低延迟,放弃，pubsub会重复发送数据:done,2023-01-30,1d
    saavuu使用stream来降低延迟:done,2023-01-31,1d
    SERVICE_BATCH_SIZE 从newService移到configuration:done,2023-02-01,1d
    支持延迟调用:done,2023-02-04,1d
    用pipeline改写pendingtask:done,2023-02-05,1d
    rpc调用时，struct不用转map:done,2023-02-05,1d

    section 冥想体验的优化
    现有的得分，波动区间大小，状态好坏的差别很小.重写得分定义:done,2023-01-28,2d
    修复datagrid无法退出编辑Bug，原因是必须返回原始model:done,2023-01-28,1d
    分数同时考虑hrv 变低和hrv的std 变低:done,2023-02-02,1d
    当天必须先评价才能看得分,为后续训练做准备:done,2023-02-03,1d
    
    #添加单条指令，开始深深的呼吸:2023-01-26,4d

    不同的意志等级（收费）,放弃:done,2023-01-15,10d
    把意愿和罚金区别开，两次付账,放弃:done,2023-01-15,10d
    使用对冲的思想来逼近动力均衡,放弃，采用常用的增值服务收费:done,2023-01-26,1d
    调研导致坚持的游戏规则，采用常用的增值服务收费:done,2023-01-26,2d
    风险与动力的关系，采用常用的增值服务收费:done,2023-01-26,2d
    修复声音卡顿的Bug:done,2023-01-26,1d
    声音卡顿的Bug-确认原始音频的质量,无问题，移动时间起始位置就可以:done,2023-01-25,2d
    终止播放后要求不继续加载音频:done,2023-01-25,1d
    满心冥想功能正常: done,2023-01-19,5d
    声音跳变的Bug:done,2023-01-18,1d
    解决偶尔声音指令同时播放的Bug:done,2023-01-18,1d
    修正hrv的定义:done,2023-01-16,1d
    #Heart rate variability (HRV) designates the continuous oscillations of uccessive RR intervals around the mean
    calculate cvRR As score:done,2023-01-16,1d
    客户端展示的hrv 值，修正为local mean :done,2023-01-16,1d

    完成阅读论文,并重写score代码,www.ncbi.nlm.nih.gov/pmc/articles/PMC6527777/pdf/fcvm-06-00062.pdf:done,2023-01-16,1d
    # what is heartful meditation:https://iyta.com.au/yoga-blog/five-steps-to-experiencing-heartfulness-meditation/

    section 重构工作
    #安装Drone,跑saavuu:2023-01-17,1d
    重启服务后，web server 会提示 Conn has unread data:done,2023-01-17,7d

    saavuu 自动添加权限，开发者模式:done,2023-01-17,1d
    Score数据结构不使用数组，使用单一记录:done,2023-01-15,1d

    section 结束不必要的工作
    关闭PH10蓝牙加速度计:done,2023-01-15,d

    section 逻辑的闭环化,音乐、指令的选择
    强化学习选择语音引导词,放弃:done,2023-01-15,1d
    强化学习选择背景音乐,放弃:done,2023-01-15,1d
    强化学习之dataloader,放弃:done,2023-01-15,1d
    meditaion RL training debug,放弃:done,2023-01-15,4d

    指令速度可调:done,2023-01-13,1d
    冥想得分的推导，单调函数:done,2023-01-14,1d
    可以查看冥想得分后文字加粗变色:done,2023-01-13,1d
    
    section 记录的准确可靠性
    确认手机播放是否影响心率准确性，放弃手机评估:done,2023-01-10,4d
    确保手机和PolarH10评估hrv评分一致性，放弃手机评估:done,2023-01-10,4d
    同时显示手机和H10的评分比对，放弃手机评估:done,2023-01-11,4d
    主观评价后才能查看得分，放弃，不使用主动评价，应使用非主观评价数据:done,2023-01-11,4d
    冥想记录能添加备注:done,2023-01-11,1d
    冥想记录格式改为 [ {}],并可以添加备注，而不是现在的{[]}:done,2023-01-11,1d

    section 确保冥想得分的合理性
    冥想得分改进，消除hrv std 的影响。消除hrv高值的高权重影响:done,2023-01-13,1d    
    # 手机能完美适用的应用
    冥想评分可合理，仅考虑低hrv部分(意外的高hrv 值应被丢弃):done,2023-01-09,1d
    冥想评分可合理，反应长程相关性:done,2023-01-09,1d
    必须看着波形来调试加速度计计算hrv,放弃，不再采用手机加速度:done,2023-01-05,4d
    与时长无关:done,2023-01-05,4d

    section KR-使用声音强化冥想
    可以立刻停止:done,2023-01-09,1d
    切换页面之后可以正确显示冥想状态:done,2023-01-09,1d
    支持删除不合理的背景指令:done,2023-01-05,4d
    #卡住的原因，解析MP3x需要指定类型
    使用HDEL删除语音指令:done,2023-01-05,1d
    冥想躲分类正常使用:done,2023-01-01,4d

    #saavuu 支持直接删除
    #saavuu取消Service，直接加入JWT:2023-01-03,1d

    section 推广冥想软件
    各种微信等注册账号的接入:2023-01-15,5d
    bilibili,youtube 等视频发布:2023-01-15,15d
    论坛反馈的预备:2023-01-15,5d

    section 定位推广群体
    可能更适宜婴儿这样没有额外心理活动的群体: cl1,2023-01-20,10d
    
    %% 衡量运动疲劳情况，什么时候应该重新运动。https://www.whoop.com/thelocker/heart-rate-variability-hrv/
    #度量所有药品的有效性，例如亚精胺
    #度量作品的欢乐程度
    %% 最粗略的入职体检，快速判断一个人的身体状态。员工每日状态检测。很难作弊的方式判断一个人是否疲劳
    # 搞笑诺贝尔奖中的会约会的人心率会同步。
    #芬兰的产品芬兰Firstbeat心率变异性分析 https://item.taobao.com/item.htm?spm=a230r.1.14.142.20d05a7b6FbkvI&id=680802758929&ns=1&abbucket=16#detail
    #员工情绪变化波动。
    # 健康，死亡率监测 https://www.frontiersin.org/articles/10.3389/fpubh.2017.00258/full04T22
    # 短期harv 和死亡有强关联。需要评估测量。https://www.ahajournals.org/doi/10.1161/01.cir.0000047275.25795.17
    # 背景音乐强化
    背景音乐市场应该是最佳市场。    最好的背景音乐要求先是具有正念效应，也就是积极的压力，但是稍后有利于提升hrv :2023-01-20,10d
    # 一个手机，可以控制前端网页上的各种操作
    # [emotion control](https://www.frontiersin.org/articles/10.3389/fnins.2019.01131/full)

    section 通过gitpages部署网站
    通过gitpages 部署网站saavuu:2023-01-20,1d 
    git actions 部署网站saavuu:2023-01-20,2d 

 
```

# 春节期2023-01-21前后，间放松了几天