# proj287-Android-performance-analysis-tool
## 基于eBPF和Perfetto的Android性能分析工具



## 项目描述



- Perfetto

Perfetto当前已经是Android平台中不可或缺的一种通用性能检测和跟踪分析工具，其可以将采集到的Linux kernel ftrace events、perf events、Android atrace events、logcat等数据直观呈现在Web UI中，极大地方便了Android平台性能问题的分析与定位。

- eBPF

eBPF是一种当前非常热门的Linux内核可观测技术，它提供了一种在不修改Kernel代码的情况下，通过注入的方式对内核进行观测的能力，有庞大的社区支撑，极好的发展前景。新版的Android已经集成了libbpf-CORE相关核心功能，GKI支持的标准内核也均以启用了BPF相关配置。



**赛题要求** (运行环境可以选择Android emulator或cuttlefish环境)

1. Android系统中很多应用会大量、频繁地创建线程来执行一些异步操作，这给CPU调度带来不少负载压力。本课题希望从源头上跟踪线程创建，比如哪个应用/进程、哪个线程、哪个用户态调用栈创建的，线程存活时间，通过对这些数据进行归类分析，来定位不合理的线程创建代码，引导应用开发者进行优化。

这些数据可以在控制台中通过频度、数量、调用栈、存活时间、父线程名、应用名等不同维度展现统计结果；也可以将关键指标数据写入Perfetto，最终在Perfetto UI中呈现；

 

2. Android系统中经常会有线程因IO、低内存或者其他原因进入D状态，导致UI显示、合成流程被阻塞，造成卡顿，本课题希望在Perfetto UI中对进入D状态的线程标记出其内核+用户态调用栈；

 

以上课题对Kernel/用户态调用栈要求：从目标函数开始往上算起至少包含6级调用栈，内核态/用户态调用栈显示要准确 (正确解析Android odex/oat文件中的符号)。



## 预期目标

- 见项目描述



## 特征



## 已有参考资料

- Perfetto分析（[简介](https://perfetto.dev/docs/)，[进阶](https://mp.weixin.qq.com/s/gXNm24I1qFw-xRhQC-Zsow)）；
- [eBPF在Android平台的实践](https://www.bilibili.com/video/BV1wY411f7aM/?p=6)



## 赛题分类

全系统功能/性能验证



## 参赛要求

以小组为单位参赛，最多三人一个小组，且小组成员是来自同一所高校的本科生或研究生；

允许学生参加大赛的多个不同题目，最终自己选择一个题目参与评奖；

请遵循“2024全国大学生操作系统比赛”的章程和技术方案要求。



## 难度

中等



## License

Apache-2.0 or BSD-2



## 所属赛道

2024全国大学生操作系统比赛的“OS功能挑战”赛道

## 项目导师

- 姓名：燕青洲（OPPO）
- 单位：OPPO
- email：[eric.yan@oppo.com](mailto:eric.yan@oppo.com)
