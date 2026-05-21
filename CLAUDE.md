# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 项目概述

本仓库致力于**一次性、高效、约束性强**的 `CLAUDE.md` / `agents.md` 文件创建。产出物为基于 Karpathy 核心原则的行为规范模板，供其他项目直接采用。

## 核心工作流

本仓库的主要任务是为用户的目标项目生成定制化的 `CLAUDE.md`。执行流程：

1. **收集信息** — 询问用户的目标项目技术栈、开发命令、架构特点
2. **基于模板** — 以 `CLAUDE-template.md` 为骨架
3. **填充定制** — 将占位符替换为项目实际信息
4. **输出文件** — 生成可直接使用的 `CLAUDE.md`

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
