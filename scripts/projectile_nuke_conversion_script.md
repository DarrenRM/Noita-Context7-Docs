---
title: Projectile Nuke Conversion Script
category: scripts
---

# Projectile Nuke Conversion Script

This script modifies existing projectiles in Noita to behave like "nukes" upon their death or lifetime expiration. It iterates through all entities tagged as "projectile" and, if they are not already tagged as "nuke," it converts them.

## Core Functionality

The script's primary goal is to ensure that any projectile that isn't explicitly a "nuke" will explode like one when it dies or its lifespan ends.

### Key Actions:

1.  **Iterate Projectiles:** The script finds all entities with the "projectile" tag.
2.  **Check for "Nuke" Tag:** It skips any projectile that already has the "nuke" tag.
3.  **Disable Default Explosions:** For non-nuke projectiles, it disables the `on_death_explode` and `on_lifetime_out_explode` properties of their `ProjectileComponent`. This prevents them from exploding in their default manner.
4.  **Capture Velocity:** It retrieves the current velocity of the projectile.
5.  **Spawn Nuke Projectile:** It spawns a new projectile defined by `data/entities/projectiles/deck/nuke.xml` at the original projectile's position and with its captured velocity.
6.  **Kill Original Projectile:** The original projectile is then destroyed.

## Key Components and Attributes Modified

The script interacts with `ProjectileComponent` and `VelocityComponent` to achieve its effect.

### ProjectileComponent

This component governs the projectile's behavior. The script specifically targets these attributes:

*   `on_death_explode`: Set to `"0"` to prevent explosions upon projectile death.
*   `on_lifetime_out_explode`: Set to `"0"` to prevent explosions when the projectile's lifespan expires.

### VelocityComponent

This component defines the projectile's movement. The script reads the `mVelocity` attribute to ensure the spawned nuke projectile inherits the original projectile's direction and speed.

## Example Usage

This script is designed to be run in the game's environment. When executed, it will scan the current projectiles and transform them into nuke-like entities.

```lua
-- Example of how the script might be triggered (not part of the script itself)
-- This would typically be called by another game system or a mod configuration.
dofile_once("data/scripts/projectiles/all_nukes.lua")
```

## Important Considerations

*   **Tagging:** The script relies heavily on entity tags. Ensure your projectiles are correctly tagged.
*   **Nuke Definition:** The actual "nuke" behavior is defined in `data/entities/projectiles/deck/nuke.xml`. This script only facilitates the conversion.
*   **Performance:** Iterating through all projectiles and spawning new entities can have performance implications if used excessively or on a very large number of projectiles.