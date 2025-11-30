---
title: Perk Item Entity
category: entities
---

# Perk Item Entity

This document describes the XML structure for a perk item entity in Noita, designed for AI-assisted modding.

## Core Entity Definition

The `Entity` tag defines the fundamental properties of the perk item.

```xml
<Entity tags="teleportable_NOT,perk,item_perk">
  ...
</Entity>
```

### Key Attributes:

*   **`tags`**: A comma-separated list of tags that define the entity's behavior and interactions.
    *   `teleportable_NOT`: Prevents the perk from being teleported.
    *   `perk`: Identifies this entity as a perk.
    *   `item_perk`: Further specifies it as a perk item that can be picked up.

## Lua Component for Pickup Logic

The `LuaComponent` handles the logic when the perk item is picked up by the player.

```xml
  <LuaComponent 
    script_item_picked_up="data/scripts/perks/perk_pickup.lua" >
  </LuaComponent>
```

### Key Attributes:

*   **`script_item_picked_up`**: Specifies the Lua script file that will be executed when the player picks up this perk. In this case, it points to `data/scripts/perks/perk_pickup.lua`, which contains the core logic for applying perks.