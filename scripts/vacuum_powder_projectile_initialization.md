---
title: Vacuum Powder Projectile Initialization
category: scripts
---

---

# Vacuum Powder Projectile Initialization

This script initializes the `vacuum_powder` projectile, specifically setting its `execute_every_n_frame` property based on its lifetime.

## Key Components and Attributes

This script primarily interacts with two components of the projectile entity:

### LuaComponent ("vacuum_powder_helper")

This component is assumed to be present and is used to set its `execute_every_n_frame` property.

### ProjectileComponent

This component is essential for retrieving the projectile's starting lifetime.

## Initialization Logic

The core logic of this script is as follows:

1.  **Get Entity ID and Position**: Retrieves the unique identifier and world coordinates of the projectile entity.
2.  **Find Components**: Locates the `LuaComponent` with the name "vacuum\_powder\_helper" and the `ProjectileComponent`.
3.  **Conditional Execution**: If both components are found:
    *   **Retrieve Lifetime**: The `mStartingLifetime` from the `ProjectileComponent` is fetched.
    *   **Set Execution Frame**: The `execute_every_n_frame` property of the "vacuum\_powder\_helper" `LuaComponent` is set to `lifetime - 1`. This ensures the helper script runs just before the projectile expires.