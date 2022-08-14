---
title: "Python下web框架比较"
date: 2021-11-05T16:16:23+08:00
draft: true
---

Benchmark FastAPI vs Falcon vs Flask 

https://gist.github.com/nhymxu/814cf9b3294276629d2231248b709e26



Fastapi 教程

https://fastapi.tiangolo.com/zh/tutorial/



总体印象，这些框架的速度取决于底层的轮子，

fast api可以保证参数的有效性，可以支持文档，因而得到更多的实施项目的支持

参考：https://www.pythonf.cn/read/56890



如果只是作为api服务器使用，那么最高效的做法其实应该是使用redis这样的消息中间件，而不是http接口。看这里，充分优化后，每秒可以收发40000RPS，有golang 一半性能。这才是答案。那么接下来要放弃web框架的选择了

https://testerhome.com/topics/25448
