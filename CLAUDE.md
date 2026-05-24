# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 项目概述

本仓库致力于**一次性、高效、约束性强**的 `CLAUDE.md` / `AGENTS.md` 文件创建与合并。产出物强调证据优先：用户已有测试数据、真实数据、PDF、原文和现成表述优先于 agent 自行改写。

## 核心工作流

本仓库的主要任务是为用户的目标项目生成定制化的 `CLAUDE.md`。执行流程：

1. **检查现有材料** — 优先读取已有 `CLAUDE.md` / `AGENTS.md`、PDF、原文、真实数据与现成表述
2. **收集缺失信息** — 仅对缺失的项目技术栈、开发命令、架构特点等进行提问
3. **基于模板** — 以 `CLAUDE-template.md` 为骨架
4. **最小定制** — 优先复用已有 wording，仅补缺失规则
5. **输出文件** — 生成可直接使用的 `CLAUDE.md` 或 `AGENTS.md`

## 模板修改原则

修改 `CLAUDE-template.md` 时：

- 规范措辞以**强制性**为主（必须/禁止），非建议性
- 保持通用性，不绑定特定技术栈
- 模板结构变更需同步更新 `skill.md` 和 `README.md`

## 模板结构

模板采用单文件结构，包含以下模块：

1. **交流规范** — 中文交流、英文术语附中文解释
2. **执行策略** — sub-agent 并行执行与自动回收
3. **行为约束表** — 单一表格整合 Karpathy 原则（编码前思考、简洁优先、外科手术式修改、目标驱动执行）+ 测试约束 + 子代理管理 + 需求确认
4. **项目信息** — 用户背景、开发命令、架构概览（通过引导式提问填充）

## Skill

配套 skill 位于 `~/.claude/skills/my-superpowers-md/skill.md`，提供创建/合并双模式入口。修改模板时需同步更新 skill。
