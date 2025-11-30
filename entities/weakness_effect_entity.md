---
title: Weakness Effect Entity
category: entities
---

# Weakness Effect Entity

This entity defines the "Weakness" status effect in Noita. When applied, it reduces the target's damage output.

## Key Components

### `GameEffectComponent`

This component governs the behavior and duration of the status effect.

| Attribute | Description                                   |
| :-------- | :-------------------------------------------- |
| `effect`  | Specifies the type of effect: `WEAKNESS`.     |
| `frames`  | Duration of the effect in game frames (600 frames ≈ 10 seconds). |