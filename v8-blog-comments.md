# V8 Blog 的内容同步阅读

Google V8 团队的技术博客（Blog）是理解V8架构和实现细节、后续研发进展的重要的来源。
另一方面，V8的技术实现一直在快速变化，博客内容从2015到2020时间跨度很大，
是否与代码一致，需要读者自己去对比才行。
我们在《深入V8引擎》的repo中记录自己阅读V8博客中的笔记和评论，方便后续我们新加入V8项目的同事理解。

目前的技术评论的时间节点是2020年第二季度。

## V8 Blog

### 013

### 012

### 011

### 010 V8 release v4.8

25 November 2015 🏷️release

ES6的两个特性的实现

### 009 Jank Busters Part One

30 October 2015 🏷️memory

原理和开发人员的关注点（需求来源）可以看下。改进的目标讲解的比较清楚。技术细节没有讲。

### 008 V8 release v4.7

14 October 2015 🏷️release

不熟悉JS的可以看看，熟悉的可以跳过。

### 007 Custom startup snapshots

25 September 2015 🏷️internals

TODO 确认下这里的 snapshot 跟目前V8代码中的 mksnapshot 等概念是否是一致的。

概念上类似于将代码内容确定的 builtin 编译成 so 库直接加载。

另一个概念是JS是有宿主环境这个概念的，不同的宿主环境给出来的可用的函数不一样，例如nodejs和浏览器。

### 006 V8 release v4.6

28 August 2015 🏷️release

1. 介绍了几个ES6的特性。对JS熟悉的可以跳过，不熟悉的建议看看，多学习点。
2. 提到了四个避免 jank 的优化。目前建议是不用看了。可能已经过时。

### 005 Getting garbage collection for free

07 August 2015 🏷️internals 🏷️memory

如果是没有接触过GC的概念的话，这篇需要看下。目前的GC已经有了一些改进，参考
[Orinoco: The new V8 Garbage Collector Peter Marshall](https://www.bilibili.com/video/BV1TJ411n7pi)
同时，增量GGC的基本思路目前是没变的。

TODO 提到的Chromium的 task scheduler 不确定现在是否淘汰了。以及 vsync 的概念是否还有。

### 004 Code caching

27 July 2015 🏷️internals

TODO 确认，不确定是否目前还是同样的实现。

这里的 Code Caching 是类似将JS源代码解析到 BaseCompiler 编译之后的结果，
优化的假设是一个脚本文件可以被多次使用，那么可以节约AST解析和输出的时间。
现在这个想法可能逐步发展成了 WebAssembly？

### 003 V8 release v4.5

17 July 2015 🏷️release

版本发布类的并不需要仔细看。主要都是 feature 的内容。本次添加了一些ES2015的语言特性。

### 002 Digging into the TurboFan JIT

13 July 2015 🏷️internals

开始针对某些特定的JS代码启用 turbofan。提到了特性：SoN，多层次翻译和优化。
明确的区分了JS语言、VM层和特定架构后端。这个目前也还是的。
给了一个 SoN IR 的例子。具体的IR细节内容可以看V8文档中的 IR 介绍。

### 001 Hello, World!

https://v8.dev/blog/hello-world

从 chromium blog 中剥离出来的第一篇。没技术内容。

## Chromium Blog

这里收录了 Chromium Blog 中标记了 v8 tag 以及我们觉得跟理解V8代码相关的内容。

### Better code optimization decisions for V8
Tuesday, May 1, 2012

https://blog.chromium.org/2012/05/better-code-optimization-decisions-for.html

PR成分多一些，介绍的是 Chrome 20 相对于 Chrome 19 的提升。

### V8 Benchmark Suite extended with physics simulation
Thursday, March 15, 2012

https://blog.chromium.org/2012/03/v8-benchmark-suite-extended-with.html

内容关系不大，可以不看。

### A game changer for interactive performance.
Monday, November 21, 2011

https://blog.chromium.org/2011/11/game-changer-for-interactive.html

GC的内容，本篇是PR，没有技术细节。而后续可以参考另一个演讲视频：

[Orinoco: The new V8 Garbage Collector Peter Marshall](https://www.bilibili.com/video/BV1TJ411n7pi)

### Updating JavaScript Benchmarks for Modern Browsers

Wednesday, May 4, 2011

https://blog.chromium.org/2011/05/updating-javascript-benchmarks-for.html

内容相关，有效。信息量不大，知道 Kraken、SunSpider 和 Octane 是 JS 测试集就行。

### A New Crankshaft for V8
Tuesday, December 7, 2010

https://blog.chromium.org/2010/12/new-crankshaft-for-v8.html

Crankshaft 在 V8 7.x 之后就没有了。

## V8 开发人员或其他同行的博客内容

## 国内同行写的中文分析内容

欢迎国内的伙伴提交PR将自己的文章加入进来，一起积累❤️
