# 医疗 AI 调研与方案设计

技能名称与源码目录名均为 `medical-ai-research-and-solutions`。入口是 [SKILL.md](SKILL.md)。它适用于医疗 AI 临床科研、医院智慧化建设和企业产品合作中的项目决策。

## 用法

在 ChatGPT 用 `@medical-ai-research-and-solutions` 选择技能，在本地 Codex 用 `$medical-ai-research-and-solutions`。在请求中提供当前项目资料、想支持的决定和预期交付。

> 根据这份神经重症医院的会议纪要，研究院方真正需要改善的工作，比较首期切入点，并写出需要找医生、护理和设备部门确认的问题。

> 这份方案按旧研究问题写成。根据医生的新反馈，识别需要重新研究的内容，更新关键假设和首期验证范围。

本地源文件可放在 `D:\projects\Agent\skills\medical-ai-research-and-solutions\`。需要让本地 Codex 按项目发现时，将技能目录放到项目根的 `.agents/skills/` 中，或在那里建指向源码目录的链接。全局使用可放到用户目录的 `.agents/skills/`。详见 [OpenAI 的技能文档](https://learn.chatgpt.com/docs/build-skills)。

## 文件

| 位置 | 用途 |
| --- | --- |
| `SKILL.md` | 任务识别、选定路径与完成标准 |
| `agents/openai.yaml` | 界面名称和调用示例 |
| `references/` | 专业调研、方案设计、交接、反馈修订 |
| `assets/research-handoff.yaml` | 研究与方案间的项目级交接模板 |
| `tests/` | 由华山、冬雷和快合医康材料抽取的三组回归输入及检查标准 |

[回归检查说明](tests/regression-rubric.md)给出测试顺序与验收规则。初始请求和后续反馈分两轮输入。
