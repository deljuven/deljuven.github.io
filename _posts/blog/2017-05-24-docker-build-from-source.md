---
layout: post
title: "论墙内编译docker的正确方式"
categories: blog
excerpt:
tags: []
image:
  feature:
date: 2017-05-24T18:39:55+08:00
modified: 2017-08-15T13:39:19+08:00
---

最近开始折腾自己的小论文，发现想法需要修改docker源代码，于是开启了折腾docker的不归路:satisfied:

docker的官方编译方法是开一个docker来编译自己（如果能告诉我怎么自己在本地编译那就更好了），嗯，这很docker。。。然而众所周知的原因，大陆的IT狗表示爸爸我连不上啊==前两天尝试不带梯子自行编译，卒……不得已，尝试自备梯子，然而发现丫的是在docker容器里面编译的，我配系统的代理有个毛用，摔！于是手动修改Dockerfile，添加proxy相关的环境变量，又是美好的一天过去了==以为改了Dockerfile就美好了么，我还是太年轻……proxy声明放在apt-get操作之前直接导致apt-get都失败……我一定是买了假的梯子==后面放在了docker pull的extra镜像之前，结果反而能编译了，一定是有神秘的东方力量……

最后花了一天来解决在docker编译的容器中设定mirror-registry的问题，不过相比之前而言这都是小问题，3个小时搞定一系列边角料。

接下来就是对docker的代码阅读和修改了，但愿本周末之前能有一点新的进展……

最后再次吐槽一下golang，作为一门语言而言真是稀烂稀烂的……