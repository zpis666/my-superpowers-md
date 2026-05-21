# Claude Code CLAUDE.md 模板

通用的 CLAUDE.md 模板，包含 Karpathy 核心原则和强制性约束。

## 包含内容

- **行为约束表**：单一表格整合 7 项核心原则（编码前思考、简洁优先、外科手术式修改、目标驱动执行、测试约束、子代理管理、需求确认）
- **交流规范**：中文交流、英文术语附中文解释
- **执行策略**：sub-agent 并行执行、自动回收

## 使用方法

### 方法 1：使用 Skill（推荐）

```bash
# 在 Claude Code 中直接调用
/my-superpowers-md
```

Skill 会自动：
- 检查目标目录是否已有 `CLAUDE.md` / `agents.md`
- 无 → 创建模式：引导式提问后生成文件
- 有 → 合并模式：逐模块对比，冲突时让用户选择

### 方法 2：手动复制

```bash
cp CLAUDE-template.md /path/to/your/project/CLAUDE.md
# 编辑项目特定部分
```

## 许可证

MIT License
