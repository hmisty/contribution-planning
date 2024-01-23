# contribution-planning
My personal contribution planning mainly to [Jouleverse](https://github.com/Jouleverse).

Jouleverse采取去中心化的协作模式，不存在一个中心化的项目主体，也就没有所谓的路线图、项目计划等等需要中央计划的东西。为了提高点对点协作的效率，作为节点和贡献者之一，我将尝试把向Jouleverse做出贡献的个人计划公开公示，以求产生更多的共鸣，吸引更多人参与进来一起贡献。

[Jouleverse工作包定义规范](https://github.com/Jouleverse/workspace/blob/main/work-package-specs.mediawiki)

以下是2024.1.23更新的个人贡献计划列表：

## JTI 2.0

对应工作包：
- JTI WP-10

具体工作：
1. 写个脚本，扫描链上数据，拉一份完整的JTI 1.0认证记录（JTI #ID - 链地址 - 认证日期）出来
2. 设计JTI 2.0的合约
3. 实现前端界面（整合到区块链浏览器）

## 区块链浏览器/红包

对应工作包：
- 区块链浏览器 WP-8
- 红包 WP-16

具体工作：
1. 红包的前端开发，集成在区块链浏览器中。目前由 @yj 在开发中。视情况配合。@Jeff 亦对此有兴趣（优化J红包封面）。
   - [红包合约源代码](https://github.com/Jouleverse/redpacket)
   - 红包封面（前端）作为区块链浏览器的一部分，目前在区块链浏览器源代码的[redpacket分支(skeleton)](https://github.com/Jouleverse/explorer/tree/redpacket)和[redpacket_dev分支(@yj)](https://github.com/Jouleverse/explorer/tree/redpacket_dev)进行开发中，与此相关的讨论在[issue#1](https://github.com/Jouleverse/explorer/issues/1)
3. 链上合约bytecode与源码一致性校验。初步考察发现，市面上并没有可用的开源实现。需研究一个可行的serverless的解决方案。
4. 合约工具加入calldata提取以及解码功能，方便多签操作之用（比如JNS铸造发放工作）。

## 链

对应工作包：WP-7

具体工作：
1. 节点包之geth客户端，在admin.peers的name字段中，希望增加一个可配置的versionTag，以便于在更新节点包配置而不变更bin的情况下，也能通过admin.peers识别对端节点采用的配置版本。已委托 @一痕 帮助给出解决方案。
2. 审计脚本，希望结合admin.peers的enode连通性，以及rpc 8501检查blockNumber，联合确认见证节点的活性。审计节点 @Jeff 提出可以统计当月活性率，作为审计指标。具体由 @Jeff 尝试编写。视情况或有需配合之处。
3. 合规备案。以节点名义，企业身份，尝试合规备案，探索合规路径。

## veJ和链上治理

对应工作包：WP-15

具体工作：
1. veJ的合约设计
2. 治理合约设计
3. timelock
4. 链上提案和投票系统
5. 治理攻击风险评估
6. 锁定tokenomics
7. 创世金库从多签迁移到治理控制
