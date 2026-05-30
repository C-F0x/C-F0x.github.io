---
title: "聊聊efisp，以及真我遗响"
description: 
date: 2026-05-30T16:15:31+08:00
image: 
math: 
license: 
comments: true
categories:
    - LIFE
build:
    list: always 
tags:
    - android
---

## 前言

去年末加加ace3虚焊了，先是蓝牙打不开，然后不读卡了。我那时候以为persist炸了需要重刷校准，结果刷了备份文件，嗯，指纹也炸了。

反正最后得出结论是要换新了。

于是乎一直物色新机。

本着买新不买旧，以及能解锁。看了一圈只有一加，oneui7的三星，moto，以及真我。

最后选中了neo8，但考虑到大R角的生理性恶心和可能出turbo机型，以及莫须有的大促折扣，就一直没有下单。

后面就是简中真我合并拆解，eol了。

嗯，最后以接近首销价的价格购入了。又买亏了（ace3买了不到一个月就出国补政策了，再叠上各种折扣，以1900的ace3pro 16+512来看，我亏了八百。哈哈

## 聊聊临时root
```shell
fastboot oem set-gpu-preemption 0 androidboot.selinux=permissive
```
提权拿root，我在12turbo上也试过了，算是day0。

没啥好说的，有fastboot的设备都是重灾区，除非和vivo一样内核反root，或者更新补丁

## 聊聊efisp

不聊深奥的，可以直接理解为sub bootloader，而且还是不做校验的那种。转译一下就是，电脑的secure boot关了，还把u盘侧载设为优先启动项。

大概的链路就是 上电 --> abl --> efisp --> 启动

没efisp就直接进入后续路径。

各大厂商更新封堵的方案基本都是 跳过 efisp

对抗措施也很简单，可以参考[三星 OneUI7 to OneUI8 的保留 OEM选项的操作](https://xdaforums.com/t/oneui8-kernelsu-tab-s10-series.4761094/)，

简而言之就是继续用老版的abl来进行引导。

当然，最好也需要继续刷打好补丁的efisp，免得厂商ota自动刷入。


打补丁也有现成的方案了，[superturtlee@GitHub](https://github.com/superturtlee/gbl_root_canoe)，ota和线刷都有方案。

值得一提的是，bootloader还是要解的，免得efisp/abl被干掉了开不了机，也补救不了，那就操蛋了。

当然，做好最坏的打算。

如果厂商和三星一样的升sw bit来彻底修补漏洞，而又用高版本的abl开机了，cpu熔断了。

那就该死心了。不过往好处想，只是没了假回锁，还是能选择正常root或者回锁的。

隔壁三星物理熔断无解，升sw bit 再开机导致oem解锁丢失也无解。结果就是强制回锁且享受残缺系统。

## 聊聊具体开机流程

老abl+efisp共同决定tee状态，

新abl单独决定tee状态，

tee状态通俗来讲就是回锁与否。

状态切换后data不再被正常解密，数据丢失。

当然你要是能把状态换回来还是能正常解密的，这个比三星好。

所以我说解锁bl很重要，留条退路

## 聊聊设备

屏幕不错，梦回使用s23p的年代，

相机不清楚，但女友拿来长焦拍bjd倒是挺满意的

就是这个R角。。。一言难尽。