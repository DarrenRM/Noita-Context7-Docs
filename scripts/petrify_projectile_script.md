---
title: Petrify Projectile Script
category: scripts
---

# Petrify Projectile Script

This script defines the behavior of a projectile that petrifies enemies. When a projectile with this script hits an entity, it checks its health. If the entity's health is below a certain threshold, it inflicts curse damage and converts the entity's ragdoll material to petrified sand. It also converts gold to air and spawns a physics stone prop.

## Key Attributes and Behaviors

### Health Threshold for Petrification

*   **`health_ratio`**: `0.4`
    *   Determines the health percentage below which the petrification effect will trigger.

### Conversion Radius

*   **`convert_radius`**: `25`
    *   The radius around the hit entity within which materials will be converted.

### Material Conversion Components

The script adds two `MagicConvertMaterialComponent` instances to the projectile entity:

1.  **Ragdoll Material Conversion:**
    *   **`from_material`**: The entity's current `ragdoll_material` (e.g., "meat").
    *   **`to_material`**: `CellFactory_GetType("sand_petrify")` - Converts the ragdoll to petrified sand.
    *   **`radius`**: `convert_radius`
    *   **`steps_per_frame`**: `1`
    *   **`kill_when_finished`**: `"1"` - The component is removed once the conversion is complete.

2.  **Gold Conversion:**
    *   **`from_material`**: `CellFactory_GetType("gold_box2d")` - Targets gold materials.
    *   **`to_material`**: `CellFactory_GetType("air")` - Converts gold to air.
    *   **`radius`**: `convert_radius`
    *   **`steps_per_frame`**: `convert_radius` - This value is set to the radius, potentially affecting conversion speed.
    *   **`loop`**: `"1"` - The conversion will loop.

### Damage Infliction

*   **`EntityInflictDamage`**:
    *   Inflicts curse damage equal to the target's `max_hp`.
    *   Damage type: `"DAMAGE_CURSE"`.
    *   Damage name: `"$damage_curse"`.

### Prop Spawning

*   **`EntityLoad`**:
    *   Spawns a physics stone prop (`data/entities/props/physics_stone_0X.xml`).
    *   The specific stone variant (`X`) is determined randomly using `ProceduralRandomi(x, y, 1, 4)`.
    *   Spawn position is offset from the hit entity's center.

### Conditional Logic

*   **`if EntityHasTag(root_id, "polymorphable_NOT") then`**:
    *   If the target entity has the tag "polymorphable\_NOT", the projectile is immediately killed, preventing petrification.
*   **`if comp.hp / comp.max_hp <= health_ratio then`**:
    *   This is the main condition for petrification. If met, the conversion and damage effects are applied.
*   **`else EntityKill(entity_id)`**:
    *   If the target entity's health is above the `health_ratio` threshold, the projectile is killed without applying any effects.

### Other Important Elements

*   **`EntityGetRootEntity(entity_id)`**: Retrieves the root entity of the projectile.
*   **`EntityRemoveFromParent(entity_id)`**: Detaches the projectile from its parent to prevent it from being destroyed with the target.
*   **`get_variable_storage_component(entity_id, "projectile_who_shot")`**: Retrieves information about who shot the projectile, used for damage attribution.
```