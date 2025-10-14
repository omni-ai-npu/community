本次会议介绍了Global Proxy的新版本Omni Proxy，说明了其重新设计的架构、核心功能及后续规划。

## 小结
**1. Omni Proxy项目介绍与演进**
- Omni Proxy是为替代Global Proxy而开发的新版本，已在master及多个分支上线。
- 项目采用了全新的架构设计，基于NGNIX生态，重点在于对大模型推理的延迟和批处理特性进行优化。
- Omni Proxy与Global Proxy将并行一段时间，未来将成为主推请求及调度框架。

**2. 核心架构与技术方案**
- **数据采集**：系统在请求生命周期内进行性能数据随路采集，以便于调度和推理特征分析。
- **调度器**：框架已具备基于智能预测进行调度的能力，并已完成APC（请求幂等）的适配。
- **文本处理与批处理**：集成了tokenizer与chat模板展开功能，并利用fast tokenizer库实现了batch级别的处理，通过并行线程显著提升了token化速度。
- **APC机制**：通过内部构建Redis树来管理和查询APC缓存，使各个worker节点能够并行进行APC匹配，并将结果作为调度权重。
- **监控接口**：通过open-telemetry暴露了可对接Prometheus的metrics接口，并计划后续补充histogram指标。

**3. 代码结构与未来规划**
- 当前代码结构中，部分代码仍与engineer强耦合，但整体已趋向纯C代码。
- 计划将内部的复杂性进一步封装，提供更多标准的C接口，供社区开发者更轻松地开发调度特性。
- Omni Proxy将承担更多职责，后续将集成APC、GPU预留、节点快速发现等管控能力，作为集群的协调和协调者。

## 待办
**1. 统一tokenizer接口修改**
- 推动社区将支持在chat接口中使用input_id的能力回归，以便未来移除项目中的patch。

## 录屏

https://www.bilibili.com/video/BV1v144zDEMt/