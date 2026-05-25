# AI Native Delivery Flow

AI Native 团队研发交付工作流 Skill。从飞书产品需求出发，经过开发需求、开发设计、任务拆分、开发执行到发布确认，完成完整的交付闭环。集成 [lark-cli](https://github.com/larksuite/cli) 实现飞书文档读取和任务同步。

## 安装

```bash
npx skills add Carpon39038/ai-native-delivery-flow
```

### 前置依赖

需要安装 [lark-cli](https://github.com/larksuite/cli)：

```bash
npx @larksuite/cli@latest install
lark-cli config init
lark-cli auth login --recommend
```

## 核心流程

```
飞书产品需求
  → 1. 开发需求文档        → [人工审核]
  → 2. 开发设计 + 测试清单  → [人工审核]
  → 3. 任务拆分 + 同步飞书   → [确认]
  → 4. 开发执行 + 代码审核   → [MR 人工审核]
  → 5. 发布确认 / 发布清单   → [人工确认]

（文档回补贯穿全程，每次对话发现不一致立即更新）
```

## 5 个核心步骤

| 步骤 | 说明 | 产物 | 审核方式 |
|------|------|------|----------|
| 1. 开发需求 | 从飞书获取产品需求，AI 生成开发需求初稿 | `02_dev_requirement.md` | 人工审核 |
| 2. 开发设计 + 测试清单 | 基于开发需求生成工程方案和测试清单 | `03_dev_design.md` + `04_test_checklist.md` | 人工审核 |
| 3. 任务拆分 | 拆分为可独立执行的小任务，同步到飞书任务 | `05_task_breakdown.md` + 飞书任务 | 确认 |
| 4. 开发执行 | 按任务开发 + AI 自动代码审核 + 提交 MR | MR + 代码 | MR 人工审核 |
| 5. 发布确认 | 发布前检查 + 监控计划 + 回滚方案 | `06_release_checklist.md` | 人工确认 |

## 文档结构

每个功能的文档统一存放在 `requirements/<功能名>/` 下：

```
requirements/<功能名>/
  01_product_requirement.md    # 飞书原始产品需求
  02_dev_requirement.md        # 开发需求文档
  03_dev_design.md             # 开发设计文档
  04_test_checklist.md         # 测试清单
  05_task_breakdown.md         # 任务拆分清单
  06_release_checklist.md      # 发布确认清单
```

## 核心原则

- **产品需求可以轻，开发需求必须准** — 产品需求从飞书获取，允许不完整；开发需求是进入开发的正式契约
- **开发需求和开发设计必须分开** — "做什么"和"怎么做"由不同的人审核
- **AI 辅助生成，关键节点人工审核** — AI 生成初稿和预审代码；人工确认需求定稿、设计定稿、MR 审核、发布
- **文档回补贯穿全程** — 任何阶段发现不一致，立即更新对应文档
- **交付 = 发布后可观测闭环** — 不止于代码合并，包含监控和回滚方案

## 使用方式

安装后在 Claude Code 中触发 skill，提供飞书文档链接即可从步骤一开始；也可以选择从任意步骤继续已有功能的交付流程。

## License

MIT
