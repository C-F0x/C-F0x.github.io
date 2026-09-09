---
title: "当我们设定setCaseSensitiveInfo的时候，我们究竟在设定些什么？"
description: 
date: 2026-03-11T11:59:38+08:00
image: 
math: 
license: 
comments: true
categories:
    - CODE
tags:
    - debug
    - dev
build:
    list: always

---
先说结论：几乎没有用

可用场景是浏览Linux相关文件，并且只能浏览，真生产力还得换系统。不过我为什么不从开始就换系统，或者用wsl2也吼的。

我这边setCaseSensitiveInfo enable 是因为想要看看三星内核和尝试去掉安全组策略，毕竟棒子的原生内核阻拦修改init_boot来提权拿root的行为。
若干年后我打算统一一下代码目录，于是乎把所有项目都clone到这个文件夹里了。

Koltin倒没有什么影响。

Flutter炸完了

简而言之就是盘符和文件夹大小写被强制转换大小写了
比如
```log
PS F:\...> dart fix . --dry-run
File doesn't exist: f:\...
```

关掉就正常了。呵呵，也就耗时了两小时。