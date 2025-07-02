## SIG简介

本SIG专注于大模型推理技术中的 PD 分离技术领域。PD 分离，即 Prefill-Decode Disaggregation，作为近年来大模型推理领域的关键突破，正重塑着推理效率与资源利用的格局。​

PD 分离技术的核心便是将这大模型推理中Prefill和Decode两个阶段解耦，分配至不同类型计算设备执行。让 Prefill 阶段在高算力硬件上全力发挥并行计算优势，Decode 阶段在具备大显存和高内存带宽的硬件上满足其内存访问需求。如此一来，该技术带来了多方面显著优势：消除了 Prefill 和 Decode 阶段间的资源竞争，使每个阶段都能以最优配置运行；允许两个阶段并行处理不同请求，大幅提升系统吞吐量；资源分配更为灵活，可依据工作负载特征动态调整 Prefill 和 Decode 资源比例。​
然而，实现 PD 分离技术并非易事，从技术实现角度看，仍面临诸多挑战，如如何高效地在 Prefill 和 Decode 节点间传输 KV 缓存；怎样设计调度策略以确保请求在不同阶段间的平滑流转；以及为每个阶段选择何种最优并行策略（如张量并行、流水线并行等）。这也正是本 SIG 的核心使命所在。

## Maintainers

* Ryan Blue 
* Dong Guyin 
* Tong Shaojun

## Committers

* Jiang Yaoguo
* Yao Yunxiang
* Wang Rui
* Wu Hang

## 2025年目标

1. TBD

## [SIG例会](meetings/sig-pd-seperation/)

可参考社区共同的[例会要求](meetings/sig-meetings-requirement.md)

### SIG例会2025年07月第一次

0. Omni-Infer社区开放策略介绍，RoadMap介绍 -- Ken
1. 当前PD分离架构介绍及当前系统性能瓶颈分析，及优化需求讨论 -- Ken， Tong Shaojun
2. 7月份特性开发计划介绍 -- Ryan Blue
3. 其他事项

