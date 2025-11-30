---
title: Chain Shot Projectile Initialization
category: scripts/
---

# Chain Shot Projectile Initialization

This script initializes the `chain_shot` variable for a projectile, tracking its iteration count. This is crucial for implementing chained effects or behaviors that depend on how many times a projectile has "chained."

## Key Attributes

*   **`iteration`**: An integer representing the current chain count of the projectile. It starts at 1 and increments with each subsequent chain.

## Initialization Logic

The script first checks if the projectile already has a `VariableStorageComponent` with the name "chain_shot".

*   If it exists, it retrieves the current `iteration` value.
*   If it does not exist (meaning this is the first iteration of the chain), it initializes the `iteration` to 1 and adds a `VariableStorageComponent` to the entity with the following properties:

```lua
{
    name = "chain_shot",
    value_int = 1,
}
```