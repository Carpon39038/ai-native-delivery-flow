# AI Native Delivery Flow

AI Native 团队研发交付工作流 Skill，集成飞书（lark-cli）实现文档获取和任务同步。

## 安装

```bash
npx skills add carpon/ai-native-delivery-flow
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
飞书产品需求 → 1. 开发需求文档 → [人工审核] → 2. 开发设计 + 测试清单 → [人工审核] → 3. 任务拆分 + 同步飞书任务 → 4. 开发执行 + 自动代码审核 + MR人工审核 → 5. 发布确认/发布清单
```

文档回补贯穿全程，每次对话发现不一致立即更新对应文档。

## 5 个核心步骤

| 步骤 | 说明 | 产物 | 审核 |
|------|------|------|------|
| 1. 开发需求 | 从飞书获取产品需求，生成开发需求初稿 | `02_dev_requirement.md` | 人工审核 |
| 2. 开发设计 + 测试清单 | 基于开发需求生成工程方案和测试清单 | `03_dev_design.md` + `04_test_checklist.md` | 人工审核 |
| 3. 任务拆分 | 拆分为可独立执行的小任务，同步飞书任务 | `05_task_breakdown.md` + 飞书任务 | 确认 |
| 4. 开发执行 | 按任务开发 + 自动代码审核 + 提交 MR | MR + 代码 | MR 人工审核 |
| 5. 发布确认 | 发布前检查 + 监控计划 + 回滚方案 | `06_release_checklist.md` | 人工确认 |

## 使用方式

在 Claude Code 中触发 skill 后，按提示选择步骤或提供飞书文档链接开始新功能。

## License

MIT
