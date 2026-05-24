# my-superpowers-md

用于创建或更新 `CLAUDE.md` / `AGENTS.md` 的技能与模板仓库，重点解决“已有说明文件如何安全合并”和“用户已有原文/PDF/真实数据如何优先复用”这两类问题。

## 包含内容

- **instruction-file skill**：用于创建或合并 `CLAUDE.md` / `AGENTS.md`
- **证据优先 merge 规则**：用户已有测试数据、真实数据、PDF、原文和现成表述优先于 agent 自行改写
- **模板与文档**：用于快速生成或维护仓库级 agent 规范

## 使用方法

### 方法 1：使用 Skill（推荐）

```bash
# 在 Claude Code 中直接调用
/my-superpowers-md
```

Skill 会自动：
- 检查目标目录是否已有 `CLAUDE.md` / `AGENTS.md`
- 无 → 创建模式：引导式提问后生成文件
- 有 → 合并模式：优先复用已有说明文件、PDF、原文和现成表述，再补缺失规则

### 方法 2：手动复制

```bash
cp CLAUDE-template.md /path/to/your/project/CLAUDE.md
# 编辑项目特定部分
```

## 关键规则

- 强制优先复用用户已有 `测试数据 / 真实数据 / PDF / 原文 / 现成表述`
- 如果关键信息缺失，应先向用户询问
- 未经允许，不可仔细编撰事实性、行为性或人物性内容

## 许可证

MIT License
