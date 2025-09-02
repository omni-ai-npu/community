### 会议纪要

本次会议主要讨论了PD分离场景下的安装部署优化以及global prox到omni prox的演进规划。参会者围绕新工具链适配、请求调度平台升级及性能提升方案进行了技术交流。

1、会议开场与自我介绍

2、PD分离场景的安装部署优化

在0.4.0版本中已对PD分离场景的脚本用户体验进行了优化，0.5.0版本将基于Omni-CLI工具进行安装部署。目标是实现一键拉起，适配k8s和未来MaaS服务化场景的部署。
当前版本基于裸机OS安装，未来会解耦为无状态的omni entry point，通过配置文件启动。

3、global proxy演进为omni proxy

global proxy将演进为omni proxy，目标是在0.6.0或0.7.0版本中开放给社区。omni proxy将基于大模型推理的业务特征进行优化，支持请求delay和batching。
omni proxy将引入全局状态机和请求生命周期控制，支持多种调度策略（sequential和parallel）。

4、omni prox的架构设计

omni proxy架构包括多个worker、一个master和基于全局状态的共享内存。支持vLLM和未来SGLang等推理平台。
omni proxy将支持动态扩缩容，通过全局管理模块和monitor实现节点健康检测和弹性伸缩。

5、QA预热与调度优化

omni proxy将支持QA预热，通过外部QA引擎（如Mooncake或LMCache）提前预取数据，优化调度效率。
调度算法将综合考虑KV亲和性和节点负载，实现全局负载均衡。
6、后续计划与讨论

omni proxy将在0.6.0版本中引入，0.7.0版本并行运行，0.8.0版本完成切换。
鼓励社区在微信群中交流需求和问题，持续改进omni proxy设计。