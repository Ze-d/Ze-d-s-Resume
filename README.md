---
name: 张津远
header:
  - text: <strong>求职意向：AI应用开发工程师 | Agent开发方向 </strong>
    newLine: true
  - text: <span class="iconify" data-icon="tabler:phone"></span> (+86) 152-9224-6365
    newLine: true
  - text: <span class="iconify" data-icon="tabler:mail"></span> 1337200048@qq.com
    link: mailto:1337200048@qq.com
  - text: <span class="iconify" data-icon="charm:person"></span><font color="#36557C"> Portfolio</font>
    link: https://ze-d.github.io/Portfolio/#/
  - text: <span class="iconify" data-icon="tabler:brand-github"></span> <font color="#36557C"> github</font>
    link: https://github.com/Ze-d
---

<!-- Important: Replace all template content, especially contact details, with your own information. -->

<!-- Important: When updating your email address, remember to change both the "text" (visible text) and the "link" (underlying hyperlink) fields. -->




## <font color="#36557C">个人简介</font>
华中科技大学通信工程硕士在读，专注于Agent架构与应用开发。具备从底层Agent Loop、记忆系统到多智能体协作的全栈设计与实现能力，独立打造了具备复杂任务调度和长期记忆的Coding Agent系统。



## <font color="#36557C">教育背景</font>
**华中科技大学 (985)** | 通信工程 硕士 | 09/2024 - 06/2027

**华中科技大学 (985)** | 电子信息科学与技术 本科 | 09/2018 - 07/2022

**TP-LINK（普联技术）**| 后端开发|07/2022-07/2024 
## <font color="#36557C">项目经历</font>

**ZCLI：具备长期记忆与任务调度的Coding Agent** 
| _Python, Anthropic SDK, Pytest, Git Worktree, CLI_
*   **背景**：为解决现有Coding Agent在长周期、多文件重构任务中容易丢失上下文、无法处理子任务依赖以及缺乏安全沙箱的痛点，我参考Claude Code的设计哲学，从零构建了一个生产级的Coding Agent。
*   **主要工作**：
    1.    **分层上下文压缩机制**：为应对长时间 Agent 会话和大型工具输出的Token超限难题，设计了一种混合压缩方案。在权衡了“纯摘要”的高失真和“纯裁剪”的信息丢失后，通过大结果磁盘寻址、近期历史LLM慢蒸馏、旧工具结果元数据裁剪的方式，在保留关键决策链的前提下，将长任务的Token消耗降低了约60%，使Agent能连续处理200+步的复杂任务而不失忆。
    2.    **健壮的内存与会话系统**：针对网络抖动导致的工具调用失败会污染Agent记忆链的棘手问题，我实现了异常调用的识别与回溯修复算法。该机制能在下次循环中自动剔除无效历史，**确保Agent在遭遇故障后能100%恢复并继续原有任务，杜绝了上下文级联污染**。
    3.    **支持依赖的持久化任务图**：为使Agent能处理带依赖关系的任务，我基于图结构设计了持久化的Task Graph。通过严格的DAG状态流转控制，**从机制上避免了子任务死锁**。并创新地将Task Node与Git Worktree绑定，**实现了任务维度的代码沙箱隔离，为后续的并行Subagent协同提供支持**。

**ScholarForge：基于多智能体的深度研究Agent**
 | _Python, LangGraph, LangChain, MCP, Tavily, RAG_
*   **背景**：为解决单Agent在复杂学术文献调研中搜索面窄、易产生认知偏差的问题，我构建了一个利用本地Zotero论文库和网络交叉验证的深度研究Agent。
*   **主要工作**：
    1.    **Supervisor-Worker多智能体架构**：在对比链式ReAct和群组辩论两种方式后，我选择了Supervisor-Worker架构以平衡多样性和效率。由Supervisor动态拆分查询，并行调度多个Researcher，在验证数据集上将零样本复杂查询的结果覆盖率从70%提升到到92%。
    2.    **高鲁棒性的LangGraph工作流**：为解决长链路研究因单点失败而整体作废的问题，我利用LangGraph的状态图特性，将研究流程建模为可中断、可恢复、可回溯的有状态图。**这从根本上提升了研究过程的工程鲁棒性，使其具备应对网络波动和LLM限流的韧性**。
    3.    **本地-网络知识交叉验证**：通过MCP协议集成Zotero本地文献库，实现本地论文知识图谱与Tavily网络搜索结果的交叉验证，确保生成的报告既有学术深度又有信息时效性。

**无线终端定位与热力图系统**
_后端开发_
*   **背景**：面向地铁、机场、商场等高密度场景，解决海量无线终端在多 AP 高频上报下的数据聚合与历史热力图查询性能问题。
*   **主要工作**：
    1.   针对多 AP 数据聚合及历史热力图查询性能问题，设计 Redis Hash 缓存、30 秒窗口聚合、实时/历史数据分层及时序降采样方案，实现多 AP 探针数据汇总和小时/天级热力图查询。
    2.   设计基于 RSSI 分级与随机重采样的多 AP 终端分布算法，解决随机 MAC、信号波动下传统精确定位失效问题，实现 1000 终端热力图计算耗时低于 1 秒。



## <font color="#36557C">专业技能</font>
-  **LLM Agent架构**：精通Agent核心闭环（Tool Loop, ReAct），具备从工具注册、权限控制到长程记忆系统的完整构建能力。
-   **Agent应用开发**：熟练运用LangChain/LangGraph进行Agent编排，熟悉状态管理、子图编排及工作流持久化。
-   **Python与工程实践**：熟悉异步编程与CLI开发，掌握Pytest、类型注解等工程方法；在ZCLI项目中实践**TDD**核心模块测试覆盖率达90%。
-   **效能最大化AI工具**：在日常开发中重度使用Claude Code/Codex等Coding Agent，并总结出基于SDD范式的有效Prompt链，使个人开发效率提升了约30%-50%。
-   **前沿了解**：了解Transformer架构及LoRA微调原理，并持续关注多Agent协同和Agent安全领域的最新进展。
