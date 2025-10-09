## SIG简介

本SIG专注于大模型推理技术中的 PD 分离技术领域。在深度学习和大模型推理的背景下，PD 分离，即 Prefill-Decode Disaggregation，作为近年来大模型推理领域的关键突破，正重塑着推理效率与资源利用的格局，如何高效地调度计算资源成为了提升推理性能的关键因素。为了解决这一挑战，Omni Infer开源项目实现了针对昇腾硬件的亲和性PD调度能力。该调度策略以P（推理实例）和D（数据实例）为核心，利用VLLM作为推理实例进行高效的分布式模型推理。

### Omni Infer PD分离 当前架构
![PD Arch](https://foruda.gitee.com/images/1751597908163756090/9cac0f6d_14535041.png "pd-arch.png")

### Omni Infer PD分离目标架构和创新方向
![PD directions](https://foruda.gitee.com/images/1751597832712790503/81c18c4f_14535041.png "pd-direction.png")

详情参见[Issue:PD分离场景下的动态扩缩容（Elastic Scaling）](https://gitee.com/omniai/omniinfer/issues/ICJXBN?from=project-issue)

### Maintainers

* Lan Longwen
* Dong Guyin
* Tong Shaojun

### Committers

* Jiang Yaoguo
* Yao Yunxiang
* Wang Rui
* Wu Hang

### 社交群组

![image](figures/sig-pd-sep-wechat.jpg)

### 例会要求
可参考社区共同的[例会要求](meetings/sig-meetings-requirement.md)

### 例会纪要
每次例会纪要与录屏均可在[归档文件夹](meetings/sig-pd-seperation)查看


### 会议信息

会议主题：Omni-Infer社区PD分离SIG例会
会议时间：2025/10/14 19:00-19:30 (GMT+08:00) 中国标准时间 - 北京
重复周期：2025/10/14-2026/04/14 19:00-19:30, 每月第2个周二

点击链接入会，或添加至会议列表：
https://meeting.tencent.com/dm/VgFEul3XKcxc

#腾讯会议：479-8774-3471

### SIG例会2025年07月8日

#### 会议议程

0. Omni-Infer社区开放策略介绍，RoadMap介绍 -- Ken
1. 当前PD分离架构介绍及当前系统性能瓶颈分析，及优化需求讨论 -- Ken， Tong Shaojun
2. 7月份特性开发计划介绍 -- Ryan Blue
3. 其他事项

### SIG例会2025年07月22日

#### 会议议程

0. [PD联合调度优化分享](https://gitee.com/omniai/omniinfer/issues/ICO1VS?from=project-issue) -- Wang Jun
1. 其他事项