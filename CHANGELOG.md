# 版本记录

## v1.1 · 2026-10-20

面向 GPT-6 Astra 极高推理的提示词设计习惯调整。保留提示词生成、诊断、模板和科研场景支持，避免为简单任务加载整套方法或流程。

- 收紧技能描述，缩短入口，取消宽泛的场景强制读取。
- 明确用户要求优先、生成与执行的边界，以及目标模型偏好不等于修改运行配置。
- 区分一次性提示词、可复用模板和常驻规则；独立使用时保留必要上下文，已有规则不重复全文注入。
- 区分硬约束与风格偏好，避免为“去 AI 味”过度润色；保留科学准确性、数据与引用的必要约束。
- 不把高推理等级转化为额外的角色、计划或反复自评要求，不设通用字数与条数上限。
- 一次性模板不自行增加分批收集、确认口令或审批阶段，避免用户填好材料后仍被不必要的流程阻断。
- 补充维护用行为检查案例。结构校验与行为抽查不能证明相较旧版的总体性能提升。

### 维护依据

以下资料于 2026-10-20 核对，仅用于解释本次设计取舍，不要求技能每次调用时重新读取或联网。

- [OpenAI：Rethinking skills and prompts for GPT-6 Astra](https://developers.openai.com/blog/rethinking-skills-and-prompts-for-gpt-6-astra)，2026-09-11：精确限定技能触发，按需加载参考，并重新审视可能过度约束新模型的旧流程。
- [OpenAI：GPT-6 prompting best practices](https://developers.openai.com/api/docs/guides/latest-model#prompting-best-practices)：明确指令优先级、完成范围与写作要求；技能中的含糊或冲突规则可能改变 Astra 的行为。
- [Codex 最佳实践](https://learn.chatgpt.com/docs/learn/best-practices)：用目标、上下文、约束和完成标准说明任务，保持常驻规则实用，并依据反复出现的问题迭代。
- [OpenAI：Reasoning best practices](https://developers.openai.com/api/docs/guides/reasoning-best-practices)：使用直接指令，按需要增加示例，无需额外要求逐步展示推理。
- [Evaluating AGENTS.md，v3](https://arxiv.org/html/2602.11988v3)，2026-09-29 修订：在所测编码任务中，上下文文件没有显著改善成功率，且增加成本。研究没有发现文件长度对结果的显著影响，不能解释为“所有长提示词都会变差”。
- [The First Drop of Ink，ICML 2026](https://proceedings.mlr.press/v306/gao26b.html)：固定长度下，少量有迷惑性的相关材料也可影响长上下文推理。该结果不直接验证学术写作提示词的效果。

以上证据支持检查相关性、冲突与不必要流程。本版本尚无控制条件下的 v1.0/v1.1 对照评估，不承诺准确率、文风或延迟改善。

## 初始版本

提交 `5389144`：提示词生成与诊断、七类场景适配、方法选择参考和中文使用说明。初始提交未设置版本标签。
