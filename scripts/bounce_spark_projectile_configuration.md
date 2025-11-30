---
title: Bounce Spark Projectile Configuration
category: scripts
---

---

# Bounce Spark Projectile Configuration

This script modifies the `ProjectileComponent` of a target entity to define its bounce effect. It's primarily used to link a specific visual effect to projectile bounces.

## Key Attributes Modified

The script focuses on modifying the `ProjectileComponent` of the entity it's attached to, or its parent if it has one.

### `ProjectileComponent` Modifications

*   **`bounce_fx_file`**: This is the core attribute modified. It specifies the XML file that defines the visual effect (particle effect, sound, etc.) to be spawned when the projectile bounces.

    *   **Value**: `"data/entities/projectiles/deck/bounce_spark_main.xml"`

## Logic Overview

1.  **Get Entity ID**: Retrieves the unique identifier for the current entity.
2.  **Get Parent Entity**: Determines if the current entity has a parent. This is crucial for identifying the projectile that spawned this effect.
3.  **Determine Target Entity**: If a parent exists, the parent entity is considered the target. Otherwise, the current entity is the target. This ensures the `ProjectileComponent` of the actual projectile is modified.
4.  **Access `ProjectileComponent`**: Attempts to retrieve the `ProjectileComponent` from the target entity. If none exists, the script exits.
5.  **Edit `ProjectileComponent`**: If the `ProjectileComponent` is found, the script uses `edit_component` to modify its properties.
6.  **Set `bounce_fx_file`**: The `bounce_fx_file` attribute within the `ProjectileComponent` is set to `"data/entities/projectiles/deck/bounce_spark_main.xml"`.

## Usage Notes

*   This script is typically attached to a projectile entity that is intended to have a specific bounce visual.
*   The `bounce_spark_main.xml` file referenced must exist and be correctly configured to provide the desired bounce effect.