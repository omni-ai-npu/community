本次会议讨论了MTP中采样及拒绝采样的现有问题，以及为优化SetgX智能投掷技术所进行的相关优化设计。

## 小结
**1. MTP采样逻辑优化**
- 当前MTP流程在获取最后一个token后，会先进行一次采样以取得bonus tokens，然后将完整的logits传入拒绝采样阶段，此过程未完全应用用户的采样参数（如penalty），可能影响模型精度并重复计算概率。
- 新的设计目标是只进行一次sample调用即可实现MTP所需的正向生成和概率计算，以提升效率和准确性。

**2. Penalty机制优化**
- 讨论了在Decode阶段应用penalty机制时，CPU与NPU间的数据同步和scatter操作会引入延迟和算子空泡的问题。
- 提出了在NPU上进行penalty caching的解决方案，通过将相关state（prefill mask, decode mask, decode count）缓存在NPU侧，并使用一个更新成本更低（常数大小）的操作而不再是完整的scatter操作，来避免数据传输和复杂的散列计算，从而显著加快惩罚计算的速度。

## 待办
**1. Penalty机制优化介绍**
- @@(高宇)@@需详细介绍在NPU上实现penalty caching的具体方案和技术细节。


## 会议录屏

https://www.bilibili.com/video/BV1u2HYz2E7s/ 