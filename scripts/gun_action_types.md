---
title: Gun Action Types
category: scripts
---

# Gun Action Types

This document outlines the different action types available for guns in Noita, crucial for AI-assisted modding to understand how a gun component behaves.

## Key Action Types

These enums define the fundamental behavior of a gun's action.

| Enum Name               | Value | Description                                                                 |
| :---------------------- | :---- | :-------------------------------------------------------------------------- |
| `ACTION_TYPE_PROJECTILE` | 0     | The gun fires a projectile.                                                 |
| `ACTION_TYPE_STATIC_PROJECTILE` | 1 | The gun fires a projectile that remains stationary after firing.            |
| `ACTION_TYPE_MODIFIER`   | 2     | The gun modifies existing projectiles or entities.                          |
| `ACTION_TYPE_DRAW_MANY`  | 3     | The gun draws multiple entities or projectiles simultaneously.              |
| `ACTION_TYPE_MATERIAL`   | 4     | The gun applies a material to a target.                                     |
| `ACTION_TYPE_UTILITY`    | 6     | The gun performs a utility function, not directly projectile-related.       |
| `ACTION_TYPE_PASSIVE`    | 7     | The gun has a passive effect that is always active or triggered by conditions. |

## Other Action Types

These are less common or more specialized action types.

| Enum Name            | Value | Description                                                                 |
| :------------------- | :---- | :-------------------------------------------------------------------------- |
| `ACTION_TYPE_OTHER`  | 5     | A catch-all for actions that don't fit other categories.                    |