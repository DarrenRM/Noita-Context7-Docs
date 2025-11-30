---
title: The Gods Are Curious Entity
category: entities
---

# The Gods Are Curious Entity

This entity is a simple, short-lived object used for triggering specific game events or behaviors.

## Core Components

### LifetimeComponent
This component dictates how long the entity exists in the game world.

*   **lifetime**: The duration in seconds the entity will persist. In this case, it's set to `1` second, meaning it will disappear almost immediately after spawning.

RAW:

```xml
<Entity>
  <LifetimeComponent
    lifetime="1" >
  </LifetimeComponent>
</Entity>
```