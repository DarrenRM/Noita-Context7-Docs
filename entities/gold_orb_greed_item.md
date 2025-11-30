---
title: Gold Orb Greed Item
category: entities
---

# Gold Orb Greed Item

This document details the `physics_gold_orb_greed.xml` entity, representing a gold orb pickup in Noita. It focuses on its physical properties, visual representation, and interaction logic.

## Core Components

### PhysicsBodyComponent
Manages the physical behavior of the orb.

| Attribute           | Description                                      |
| :------------------ | :----------------------------------------------- |
| `allow_sleep`       | `1` - Allows the physics body to sleep when idle. |
| `is_bullet`         | `1` - Treats the object as a projectile.         |
| `hax_fix_going_through_ground` | `1` - A fix to prevent it from falling through terrain. |

### PhysicsImageShapeComponent
Defines the visual shape and material of the orb.

| Attribute    | Description                               |
| :----------- | :---------------------------------------- |
| `image_file` | `data/items_gfx/orb_greed.png` - The sprite for the orb. |
| `material`   | `metal_hard` - The physical material.     |

### LuaComponent
Attaches custom script logic to the orb.

| Attribute     | Description                                      |
| :------------ | :----------------------------------------------- |
| `script_kick` | `data/scripts/items/gold_orb_greed.lua` - The script handling its behavior. |

### ItemComponent
Defines the item's properties for inventory and gameplay.

| Attribute              | Description                                      |
| :--------------------- | :----------------------------------------------- |
| `item_name`            | `$item_gold_orb_greed` - The internal name.      |
| `is_pickable`          | `1` - Allows the player to pick it up.           |
| `is_equipable_forced`  | `1` - Can be equipped directly.                  |
| `ui_sprite`            | `data/ui_gfx/items/orb_gold_greed.png` - The UI icon. |
| `ui_description`       | `$itemdesc_gold_orb_greed` - The UI description text. |
| `preferred_inventory`  | `QUICK` - Defaults to the quick inventory.       |

### AbilityComponent
Grants the orb specific abilities.

| Attribute     | Description                                      |
| :------------ | :----------------------------------------------- |
| `throw_as_item` | `1` - Allows the orb to be thrown as an item.    |

## Visual Effects (Particle Emitters)

The orb utilizes several `SpriteParticleEmitterComponent` instances to create visual flair. These contribute to its "shine" and visual presence.

### Particle Emitter 1
*   **Sprite File:** `data/particles/shine_07.xml`
*   **Lifetime:** `0.3`
*   **Emission Interval:** `20-250` frames
*   **Count:** `1`
*   **Additive:** `1`
*   **Randomization:** Scale, position, and animation speed are randomized within defined ranges.

### Particle Emitter 2
*   **Sprite File:** `data/particles/shine_08.xml`
*   **Lifetime:** `0.2`
*   **Randomize Lifetime:** `0.1-0.8`
*   **Emission Interval:** `10-100` frames
*   **Count:** `1`
*   **Additive:** `1`
*   **Randomization:** Scale, position, and animation speed are randomized.

### Particle Emitter 3
*   **Sprite File:** `data/particles/shine_06.xml`
*   **Lifetime:** `0.56`
*   **Emission Interval:** `100-600` frames
*   **Count:** `1`
*   **Additive:** `1`
*   **Randomization:** Scale, position, and animation speed are randomized.

## Other Notable Components

### CameraBoundComponent
*   `max_count`: `50` - Limits the number of these entities within camera view.
*   `distance`: `500` - The maximum distance from the camera to render.

### VariableStorageComponent
*   `name`: `kick_count` - Stores an integer value, likely for tracking interactions.

### PhysicsThrowableComponent
*   `max_throw_speed`: `180`
*   `throw_force_coeff`: `1.5`

### PhysicsBodyCollisionDamageComponent
*   `speed_threshold`: `140.0` - The speed at which collisions start dealing damage.

### UIInfoComponent
*   `name`: `$item_gold_orb_greed` - Provides the name for UI display.

### SpriteComponent
*   `image_file`: `data/items_gfx/in_hand/orb_greed.png` - The sprite when held in hand.
*   `_enabled`: `0` - This sprite is likely disabled by default and enabled by other components or scripts.