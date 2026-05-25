# AGENTS.md

This file provides guidance to AI coding agents working on this repository.

## Repository Overview

A skill for AI coding agents that implements an AI Native team delivery workflow. Integrates with Feishu/Lark via `lark-cli` to fetch product requirements and sync tasks.

## Skill Structure

```
skills/
  ai-native-delivery-flow/
    SKILL.md              # Skill definition (5-step delivery workflow)
```

## Dependencies

- [lark-cli](https://github.com/larksuite/cli) — Feishu/Lark CLI for document fetching and task management
