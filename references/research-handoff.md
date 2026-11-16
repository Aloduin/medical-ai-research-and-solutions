# 研究交接协议

从 [YAML 模板](../assets/research-handoff.yaml) 拷贝初始结构。每次针对实际决策填写最新一版，引用项目工作区中用户提供或获授权访问的文件位置。已完成交接至少有项目、决策问题、支持或制约决策的发现，以及可执行的下一步。只为当前任务有用的信息建条目。

## 字段与关系

| 字段 | 填写方法 |
| --- | --- |
| `schema_version` | 格式版本，当前为字符串 `"1.0"`。 |
| `project` | `name`、`revision`（整数）、`previous_revision`（首版留空）、`as_of`（ISO 日期字符串）和 `track`。主路径用 `CLINICAL_RESEARCH`、`HOSPITAL_INNOVATION` 或 `MEDICAL_BUSINESS`。 |
| `decision` | `question` 写本轮要做的具体决定，`audience` 写主要受众。 |
| `research_questions` | 每行有 `id`、`question`、`finding_refs`。研究尚缺证据时用发现条目的状态或对应未知项记录。 |
| `sources` | 每行有 `id`、`title`、`kind`、`locator`、`date_or_version` 和 `access`。位置用 DOI、网页、文件及页码或会议记录位置。访问状态如 `FULL`、`EXCERPT`、`ABSTRACT`、`UNREAD`。 |
| `findings` | 每行有 `id`、`statement`、`status`、`source_refs`、`applicable_scope`、`limitations`。使用主入口定义的四种陈述状态。 |
| `data_conditions` | 每行有 `id`、`item`、`availability`、`authorization`、`detail`、`finding_refs`。用 `detail` 写采样、链接、覆盖率或质量核验范围。 |
| `candidate_directions` | 每行有 `id`、`direction`、`problem`、`finding_refs`、`data_refs`、`validation`。 |
| `open_questions` | 每行有 `id`、`question`、`decision_impact`、`check` 和 `owner`。未知责任人可注明待确认的角色。 |
| `next_step` | 填写 `action`、`owner`、`depends_on` 和 `acceptance_check`。依赖指向数据条件或未知项。 |
| `changes` | 多轮时填 `feedback`、`source_refs`、`impact` 和 `affected_refs`。引用前版条目时写明前版版本。 |

- 项目可读性需要时使用 `Q-001`、`S-001`、`F-001`、`D-001`、`C-001`、`U-001` 格式，让引用指向当前版已经定义的相应条目。发现限制按需使用字符串列表，所有引用用 ID 列表。
- `VERIFIED` 至少引用一条实际阅读且支持所述范围的来源。综述所证实的观察、研究中的关联、院内结果及可部署性的证据范围各有自己的表述。已有计划只能核实计划本身。
- 数据状态采用已知的最高可证明阶段。`DESCRIBED` 表示有字段或设备说明，`OBSERVED` 表示已看到存在的记录，`OBTAINABLE` 表示已验证获取方式，`QC_PASSED` 表示指定任务的质量检查通过。`UNKNOWN` 表示当前证据不足。可获取性与用途授权独立填写，授权用 `CONFIRMED`、`PENDING`、`UNKNOWN` 或 `OUT_OF_SCOPE`。
- 修订时为改变含义的发现设新 ID，保留原来不受影响的链接。以 `changes` 说明原因和前后版本。交接文件仅保存完成决策所需的摘要、定位和状态。
