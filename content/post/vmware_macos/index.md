---
title: "wsl2后，我重新安装了vmware workstation"
description: 
date: 2026-08-09T09:40:35+08:00
image: 
math: 
license: 
comments: true
categories:
    - CODE
build:
    list: always 
tags:
    - ios
    - dev
---

wsl2 确实很爽，并且短期内应该不会和wsa一样被砍掉。

不过，因为macos我又把VMware下回来了。

ipa构建依赖xcode依赖macos...

早知道早点买mac mini 4了，又涨价了，，，

感谢surrealra1n, dopamine, Relaxin, usbliter8, 我打算降级越狱一下, 把之前kmp for ios的坑补上。

```ps
winget install --id cloudbase.qemu-img
```

然后 [recoveryOS](https://github.com/DrDonk/recoveryOS/releases/latest)

后面就和正常的一样了，装15.7.9，装xcode离线包。
 
我用ssh连的，还算不错。毕竟4MB显存也只能跑cli了。

果子开发机的环境是 ios 16.6.1, Trollstore, Relaxin, Sileo.

嗯，买不起开发者授权