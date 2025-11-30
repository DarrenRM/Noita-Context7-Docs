---
title: Loose Ground Entity
category: guides
---

<Entity>
  <LooseGroundComponent
    probability="0.1" />
  <LifetimeComponent
    lifetime="240"
    randomize_lifetime.min="-50"
    randomize_lifetime.max="50" />
</Entity>
```

---
title: Loose Ground Entity
category: entities
---

# Loose Ground Entity

This entity represents loose ground that can be generated in the game world.

## Components

### LooseGroundComponent

This component governs the behavior of loose ground.

*   **`probability`**: (float) The chance of this entity spawning. A value of `0.1` means a 10% chance.

### LifetimeComponent

This component defines how long the entity will exist.

*   **`lifetime`**: (float) The base duration the entity will last in seconds.
*   **`randomize_lifetime.min`**: (float) The minimum amount to subtract from the base `lifetime`.
*   **`randomize_lifetime.max`**: (float) The maximum amount to add to the base `lifetime`.