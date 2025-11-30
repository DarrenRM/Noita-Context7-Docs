---
title: Zero Damage Projectile Configuration
category: scripts
---

# Zero Damage Projectile Configuration

This script configures a projectile entity to deal zero damage and disable various explosion and damage-related components. It's primarily used for creating projectiles that have visual effects or other behaviors without inflicting harm.

## Key Components and Attributes

This script focuses on modifying the `ProjectileComponent` and disabling other damage-dealing components.

### ProjectileComponent Modifications

The following attributes of the `ProjectileComponent` are explicitly set to prevent damage and explosions:

*   **`on_death_explode`**: Set to `"0"` to disable explosion upon death.
*   **`on_lifetime_out_explode`**: Set to `"0"` to disable explosion when the projectile's lifetime expires.
*   **`damage`**: Set to `"0"` to ensure the projectile deals no base damage.

### Damage Type Overrides

The script iterates through all `ProjectileComponent` instances and explicitly sets the damage for various damage types to `0`. This ensures that even if a projectile could theoretically deal damage through other means, it's nullified.

```lua
ComponentObjectSetValue2( v, "damage_by_type", "projectile", 0 )
ComponentObjectSetValue2( v, "damage_by_type", "electricity", 0 )
ComponentObjectSetValue2( v, "damage_by_type", "explosion", 0 )
ComponentObjectSetValue2( v, "damage_by_type", "fire", 0 )
ComponentObjectSetValue2( v, "damage_by_type", "melee", 0 )
ComponentObjectSetValue2( v, "damage_by_type", "drill", 0 )
ComponentObjectSetValue2( v, "damage_by_type", "slice", 0 )
ComponentObjectSetValue2( v, "damage_by_type", "ice", 0 )
ComponentObjectSetValue2( v, "damage_by_type", "healing", 0 )
ComponentObjectSetValue2( v, "damage_by_type", "physics_hit", 0 )
ComponentObjectSetValue2( v, "damage_by_type", "radioactive", 0 )
ComponentObjectSetValue2( v, "damage_by_type", "poison", 0 )
ComponentObjectSetValue2( v, "damage_by_type", "overeating", 0 )
ComponentObjectSetValue2( v, "damage_by_type", "curse", 0 )
```

### Disabled Components

The script actively disables or removes components that could cause damage or explosions:

*   **`NullDamageComponent`**: Ensures this component is added if not already present, reinforcing the zero-damage nature.
*   **`ExplosionComponent`**: All instances are disabled.
*   **`ExplodeOnDamageComponent`**: All instances are disabled.
*   **`AreaDamageComponent`**: All instances are removed from the entity.
*   **`LightningComponent`**: All instances are disabled.

## Usage for Modding

When creating custom projectiles, you can use this script as a template to ensure your projectile has no harmful effects. Simply apply this script to your projectile entity definition.

**Example Snippet in `entities.xml`:**

```xml
<Entity tags="projectile">
    <LuaComponent
        script_path="data/scripts/projectiles/zero_damage.lua"
        execute_every_frame="false"
        />
    <!-- Other components for visual effects, etc. -->
</Entity>
```