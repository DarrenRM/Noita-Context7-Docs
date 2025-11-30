---
title: All Spells Part Projectile Logic
category: scripts
---

---

# All Spells Part Projectile Logic

This script defines the behavior for a projectile component used in the "All Spells" spell. It manages its position, rotation, and interaction with other "all_spells_part" entities owned by the same player.

## Key Attributes and Functionality

This script primarily interacts with `VariableStorageComponent` to retrieve and update projectile properties.

### Variable Storage Components

The script looks for specific variable names within `VariableStorageComponent` attached to the projectile entity:

| Variable Name | Type    | Description