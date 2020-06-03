---
title: 'paper notes'
date: 2016-11-28
permalink: /posts/2016/11/blog-paper_notes/
tags:
  - SLAM
  - ORB-SLAM
  - Relocalisation
  - Loop Closing
---

Fast Relocalisation and Loop Closing in Keyframe-Based SLAM
======

简介
------

这是2014年6月ICRA（中国香港）的文章，7月份作者`Raul Mur`就在RSS14的workshop上发表了ORB-SLAM。

摘要
------

In this paper we present for the first time a relocalisation method for keyframe-based SLAM that can deal with severe viewpoint change, at frame-rate, in maps containing thousands of keyframes. 

亮点：第一次提出基于关键帧的SLAM的重定位方法

As this method relies on local features, it permits the interoperability between cameras, allowing a camera to relocalise in a map built by a different camera. We also perform loop closing (detection + correction), at keyframerate, in loops containing hundreds of keyframes. 

重点：局部特征；在关键帧上进行闭环

For both relocalisation and loop closing, we propose a bag of words place recognizer with ORB features, which is able to recognize places spending less than 39 ms, including feature extraction, in databases containing 10K images (without geometrical verification). 

核心：ORB特征词袋

We evaluate the performance of this recognizer in four different datasets, achieving high recall and no false matches, and getting better results than the state-of-art in place recognition, being one order of magnitude faster.

实验


ORB-SLAM: Tracking and Mapping Recognizable Features
======

简介
------

经典的ORB-SLAM第一篇文章，发表在2014年RSS的workshop上，网上有很多对这篇文章的分析、翻译。

摘要
------

Current visual SLAM systems build maps that are very good to track a camera during a session. However these maps are not designed to perform localisation in other sessions, with a different camera, or even the same camera, but observing the map from different viewpoints. This limitation comes from the lack of the map capacity to be recognized. 

问题：由于地图缺乏可识别能力，当前视觉SLAM系统可以很好的跟踪相机，但是不能进行重定位

In this paper we present a new keyframe-based SLAM system, which boosts the reusability of the maps, by directly mapping features that can be used for recognition. 

亮点：基于关键帧，地图可复用

Our system performs relocalisation and loop closing with a high invariance to viewpoint in real time. Large scale is addressed building a covisibility graph that allows to perform most mapping and tracking operations locally. We also incorporate a pruning mechanism to reduce the redundancy of keyframes in the map. 

重点：实时重定位和闭环；Covisibility graph能局部处理大部分建图和跟踪，用来解决大规模；剪枝机制降低关键帧冗余；

We believe that the capacity of our system to build reusable maps makes it a good choice for the community to investigate in long-term and recognition problems.

ORB-SLAM至今一直都是最好的框架之一。