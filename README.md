# my-superpowers-md

用于创建或更新 `CLAUDE.md` / `AGENTS.md` 的技能与插件仓库，重点解决“已有说明文件如何安全合并”和“用户已有原文 / PDF / 真实数据如何优先复用”这两类问题。

## 包含内容

- **instruction-file skill**：用于创建或合并 `CLAUDE.md` / `AGENTS.md`
- **证据优先 merge 规则**：用户已有测试数据、真实数据、PDF、原文和现成表述优先于 agent 自行改写
- **插件结构**：包含 `.codex-plugin/plugin.json` 与 `skills/my-superpowers-md/SKILL.md`
- **模板与文档**：用于快速生成或维护仓库级 agent 规范

## 使用方法

## 安装方式

### 方法 1：作为 Codex 本地插件安装（推荐）

1. 克隆仓库到本地插件目录：

```bash
git clone https://github.com/zpis666/my-superpowers-md.git ~/plugins/my-superpowers-md
```

2. 在你的个人插件市场文件 `~/.agents/plugins/marketplace.json` 中加入以下条目：

```json
{
  "name": "my-superpowers-md",
  "source": {
    "source": "local",
    "path": "./plugins/my-superpowers-md"
  },
  "policy": {
    "installation": "AVAILABLE",
    "authentication": "ON_INSTALL"
  },
  "category": "Coding"
}
```

3. 让 Codex 重新读取插件市场后，即可在本地插件列表中使用。

### 方法 2：直接使用 Skill 文件

直接取用仓库中的：

- `skill.md`
或
- `skills/my-superpowers-md/SKILL.md`

放到你的技能目录即可。

## 关键规则

- 强制优先复用用户已有 `测试数据 / 真实数据 / PDF / 原文 / 现成表述`
- 如果关键信息缺失，应先向用户询问
- 未经允许，不可仔细编撰事实性、行为性或人物性内容

## 许可证

MIT License
