---
title: Explosion Was Here Entity
category: entities
---

# Explosion Was Here Entity

This entity represents a simple, short-lived explosion effect. It's primarily used for visual feedback and doesn't have complex interactions.

## Key Components

### LifetimeComponent

This component defines how long the entity will exist before disappearing.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `lifetime` | The duration in seconds the entity persists. |

**Example:**

```xml
<LifetimeComponent
    lifetime="50"
    >
</LifetimeComponent>
```