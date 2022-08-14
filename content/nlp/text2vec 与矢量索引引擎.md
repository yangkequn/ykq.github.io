---
title: "text2vec 与矢量索引引擎"
date: 2021-09-01T21:58:16+08:00
draft: false
---

1.milvus Milvus 是一款开源的、针对海量特征向量的相似性搜索引擎。
https://github.com/milvus-io/milvus
文档 https://milvus.io/cn/

各种各样的语料库，非常全，而且可以下载
冷眼-风雨飘摇
专注于python、自然语言处理
https://cold-eye.github.io/post/nlp-corpus/
2021-09-01 13:39:39 星期三

2. text2vec引擎
推理速度可以满足实时性要求。https://github.com/NVIDIA/FasterTransformer

ELECTRA模型
https://www.leiphone.com/category/academic/i2yH9anJWkh8rd6r.html
中文预训练模型
https://www.leiphone.com/category/academic/i2yH9anJWkh8rd6r.html
https://github.com/ymcui/Chinese-ELECTRA
科大讯飞某个主要技术负责人的github https://github.com/ymcui
中文训练数据集扩大9倍后的效果
https://www.jiqizhixin.com/articles/2020-10-26-11

苏剑林的反省：吐槽贴：用ELECTRA、ALBERT之前，你真的了解它们吗？
https://bbs.huaweicloud.com/blogs/226675
苏剑林的博客
https://kexue.fm/

对bert 进行蒸馏，tinyBERT,推理速度提高9倍
https://zhuanlan.zhihu.com/p/94359189
这是很棒的模型，一来可以直接训练，二来，可以用来蒸馏后使用

最后，github 上找出了一个质量很不错的答案，来解决计算文本相似度的问题
https://github.com/shibing624/text2vec
具体实现包括wordVector 平均值法，以及small Bert 模型，重要的是这个是开箱可用的
https://www.sbert.net/index.html

2021-09-02 15:06:43 星期四
---
fasterTransformer
https://baike.baidu.com/item/Faster%20Transformer/23737285?fr=aladdin

最新的媲美Bert的模型
PRADO，pQRNN
https://zhuanlan.zhihu.com/p/257934777
：印象是虽然小，但是没有放出的代码实现。也没有中文版本的踩坑记录

2021-09-01
---
