# EvoAgent：面向PR研发治理的自进化Multi-Agent Harness系统9150期

## 项目概述

本项目**不是Coding Agent**，而是一个面向 **Pull Request 风险治理与安全修复场景**的自研系统。其核心是构建一个**可持久化、可恢复的 Agent Runtime Harness**，完成从**风险发现、证据复核、补丁生成、结果验证、离线评测到反馈学习和版本回滚**的端到端闭环。
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/5a4b122416604c79a4628dd136c32604.png)

## 项目核心信息

| 项目 | 详细说明 |
| :--- | :--- |
| **项目定位** | 自进化Multi-Agent Harness系统，面向PR研发治理 |
| **技术栈** | Python、Harness Engineering、Multi-Agent Orchestration、Self-Evolution、PostgreSQL、OpenTelemetry、Docker、Prometheus |
| **交付内容** | 项目详细讲解文档 + 简历写法 + 完整可运行代码 |
| **部署方式** | Docker一键部署，无Docker环境也可依据文档本地运行，小白可跑通 |
| **评测支持** | 提供具体评测集，支持端到端评测指标本地复现 |
| **应用价值** | 1. **研发治理**：面向PR风险治理与安全修复，自动化完成风险发现、证据复核与补丁生成。<br>2. **自进化能力**：Prompt/Skill双轨自进化，支持候选生成、门禁激活与版本回滚。<br>3. **可观测性**：全链路Trace与指标监控，支持执行链路回放、失败归因与断点恢复。 |


![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/998ed6738aae4b4e99fbef18d4ee2ea1.png)

## 系统核心模块

**1. 自研 Agent Runtime Harness**

Pull Request审查建模为**可持久化长任务**，统一管理任务状态、执行预算、节点重试、持久化Checkpoint、任务取消、断点续跑及Run Trace。

**2. Prompt/Skill 双轨自进化**

Prompt与Agent Skill双轨独立进化链。自动Prompt和Skills候选生成，三层门禁激活。提供内容指纹去重、版本血缘追踪、历史回放和一键回滚。

**3. 分层多 Agent 协作**

主从协作架构，Lead动态任务、Skill分派，双Worker并行React循环。

**4. Agent 端到端评测**

100个受控PR Diff样本的端到端Evaluation Harness，支持PR Diff审查准确率、多agent/单agent消融分析、Critic消融分析。

**5. 上下文压缩与 Memory 管理**

风险Hunk、历史Observation和Token预算有限上下文。Working、Episodic、Semantic、Procedural四类记忆。租户及仓库级检索隔离、任务归档和过期清理。

**6. 异步与可观测体系**

有界Agent Loop。异步任务投递、ACK、Worker租约、指数退避重试和死信队列。支持执行链路回放、失败归因、评测复现和断点恢复。

## 知识普及：Agent Runtime Harness 的设计要点

*   **Harness Engineering（执行框架工程）**：不同于单纯的Agent编排，Harness关注的是Agent运行时的可靠性——包括任务持久化、状态管理、错误重试、断点恢复等工程化能力，使Agent系统从Demo走向生产可用。
*   **自进化机制**：Prompt和Skill的独立进化链，配合门禁激活与版本回滚，使系统能够在使用中不断优化自身，无需人工干预即可迭代。
*   **可观测性三要素**：Trace（链路追踪）、Metrics（指标监控）、Logging（日志记录），三者结合实现全链路可观测，是复杂Agent系统稳定运行的基础。
*   **多Agent协作模式**：Lead-Worker架构中，Lead负责任务分解与调度，Worker并行执行，适合处理PR审查这类需要多维度分析的复杂任务。

## 技术架构概览

| 层次 | 技术选型 |
| :--- | :--- |
| **编排层** | Multi-Agent Orchestration、双Worker并行React循环 |
| **进化层** | Prompt/Skill双轨自进化、三层门禁激活 |
| **记忆层** | Working/Episodic/Semantic/Procedural四类记忆 |
| **异步层** | 有界Agent Loop、异步任务投递、死信队列 |
| **可观测层** | OpenTelemetry、Prometheus、Run Trace |
| **存储层** | PostgreSQL |
| **部署层** | Docker一键部署 |

## 交付清单

*   **完整可运行代码**：Docker一键部署
*   **项目详细讲解文档**：含架构设计、模块说明
*   **简历写法指导**：适合求职者包装项目经历
*   **评测集**：支持端到端评测指标本地复现

## 标签
`EvoAgent` `自进化Agent` `Multi-Agent` `PR研发治理` `Harness Engineering` `Agent Runtime` `可观测性` `Docker部署`
