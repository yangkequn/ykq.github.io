
---
title: "202304_reinfy"
date: 2023-06-02T15:10:00+08:00
draft: false
---

``` mermaid
gantt
    title O:实现learnWithAGI
    dateFormat  YYYY-MM-DD
    excludes    sunday

    section 学习新知改进
    自动选择一个知识点 :done,2023-05-06,2d
    回答后，加分:done,2023-05-06,1d
    提问后，加分:done,2023-05-06,1d
    首页显示学习内容列表:done,2023-06-02,1d
    保存项目到github:done,2023-06-02,1d
    新知只专注于一个主题:done,2023-06-03,1d
    二级菜单显示主题，显示奖励内容:done,2023-06-03,1d

    写skill列表页面，和skillsearch:done,2023-06-04,1d

    搭开发环境，写text2vec:done,2023-06-07,1d

    调试把skill-topic 保存到milvus:done,2023-06-13,1d
    可以查询skill-topic:done,2023-06-11,2d
    text2vec服务后台运行:done,2023-06-13,1d
    可以添加和查询skill-topic:done,2023-06-13,1d
    使得创建课程自动化-调试api接口:done,2023-06-14,3d
    使得创建课程自动化-正确自动化索引:done,2023-06-17,1d
    使得创建课程自动化-对3.5,先试用plus,再使用api:done,2023-06-17,1d
    使得创建课程自动化-使用完成conversation后，删除conversation:done,2023-06-17,1d

    使得创建课程自动化-获取QAs格式支持良好:done,2023-06-18,1d

    使得创建课程自动化-获取Socratics格式支持良好:done,2023-06-19,1d

    列表，问题练习，苏格拉底发问直接模块划分不清，重新模块化这三个模块，差不多用了一天:done,2023-06-19,1d

    左侧skillPath除了按难易度划分，还要按主题划分:done,2023-06-20,1d
    直接支持chatgptplus的绕过cloudflare的自定义接口,失败:done,2023-06-20,2d
    chatgptapi稳定性，调试基于fakeopenai接口:done,2023-06-22,1d
    指定更确切的模型，避免结果的不确定,giveup,实际模型都是text-davinci-002-render-sha:done,2023-06-22,1d

    把skillPath中的回答分离出来,以便可以不登录查看:done,2023-06-23,2d
    
    回顾中的等级评分采用均分，使得不同等级的点数一样多:done,2023-06-25,2d
    解决答案的错误问题:done,crit,2023-06-25,1d
    自动选择收个未回答项目:done,2023-06-25,1d

    section 后端支持系统：
    重写q-milvus,直接支持带类型的collection:done,2023-06-05,1d
    虚拟机安装新版本的milvus（旧版本空间不足，已经损坏了）:done,2023-06-06,1d
    重新部署stream版本的word2vec2:done,2023-06-06,1d
    低产出，试图取消esxi服务器，完全搬到proxmox，失败:done,2023-06-08,1d
    重新调整proxmox的虚拟机结构，把全部虚拟机从esxi迁移到proxmox:done,2023-06-09,2d

```