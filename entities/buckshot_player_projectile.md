---
title: Buckshot Player Projectile
category: entities
---

# Buckshot Player Projectile

This document details the `buckshot_player.xml` entity, representing a player-fired projectile in Noita. It's a versatile projectile with several key attributes governing its behavior, appearance, and effects.

## Core Components

### Entity
The root element defining the projectile.

*   **name**: `$projectile_default` - Inherits base projectile properties.
*   **tags**: `projectile_player` - Identifies this as a player-owned projectile.

### Base
Inherits fundamental projectile mechanics.

*   **file**: `data/entities/base_projectile.xml` - Links to the core projectile definition.

#### VelocityComponent
Governs the projectile's movement.

*   **air\_friction**: `1.0` - High air friction, suggesting it slows down quickly in the air.
*   **mass**: `0.06` - A relatively low mass.

### ProjectileComponent
Defines the specific behaviors and effects of this projectile.

*   **_enabled**: `1` - Ensures this component is active.
*   **lob\_min**: `0.8` - Minimum lob angle (vertical deviation).
*   **lob\_max**: `1.3` - Maximum lob angle.
*   **speed\_min**: `500` - Minimum projectile speed.
*   **speed\_max**: `600` - Maximum projectile speed.
*   **direction\_random\_rad**: `0.04` - Small random deviation in projectile direction.
*   **on\_death\_explode**: `1` - The projectile explodes upon death (e.g., hitting a surface or expiring).
*   **on\_death\_gfx\_leave\_sprite**: `0` - Does not leave a sprite graphic upon death.
*   **on\_lifetime\_out\_explode**: `1` - Explodes when its lifetime expires.
*   **explosion\_dont\_damage\_shooter**: `1` - The explosion does not harm the player who fired it.
*   **on\_collision\_die**: `1` - The projectile is destroyed upon collision.
*   **lifetime**: `120` - The projectile's lifespan in frames.
*   **lifetime\_randomness**: `7` - Adds a small random variation to the projectile's lifespan.
*   **damage**: `0.185` - The base damage dealt by the projectile.
*   **velocity\_sets\_scale**: `1` - The projectile's velocity influences its scale.
*   **ragdoll\_force\_multiplier**: `0.0025` - Multiplier for ragdoll forces applied on collision.
*   **hit\_particle\_force\_multiplier**: `0.25` - Multiplier for particle forces when hitting something.
*   **camera\_shake\_when\_shot**: `8.0` - Amount of camera shake when the projectile is fired.
*   **create\_shell\_casing**: `0` - Does not create a shell casing.
*   **bounces\_left**: `1` - The projectile can bounce once.
*   **shoot\_light\_flash\_radius**: `100` - Radius of the light flash when shot.
*   **ragdoll\_fx\_on\_collision**: `BLOOD_EXPLOSION` - Applies a blood explosion effect on collision.
*   **muzzle\_flash\_file**: `data/entities/particles/muzzle_flashes/muzzle_flash_laser_green.xml` - Specifies the muzzle flash particle effect.
*   **knockback\_force**: `1.0` - The force applied to knock back targets.
*   **physics\_impulse\_coeff**: `2000` - Coefficient for physics impulse.

#### config\_explosion
Configuration for the projectile's explosion.

*   **never\_cache**: `1` - Prevents caching of this explosion.
*   **camera\_shake**: `0.3` - Camera shake applied by the explosion.
*   **explosion\_radius**: `4` - The radius of the explosion.
*   **explosion\_sprite**: `data/particles/explosion_008_plasma_green.xml` - The sprite used for the explosion.
*   **explosion\_sprite\_lifetime**: `0` - The explosion sprite's lifetime.
*   **create\_cell\_probability**: `0` - Probability of creating cells.
*   **hole\_destroy\_liquid**: `0` - Does not destroy liquids.
*   **hole\_enabled**: `1` - Enables the creation of holes.
*   **ray\_energy**: `50000` - Energy value for raycasting effects.
*   **damage**: `0.0` - The explosion itself deals no direct damage (damage is handled by the projectile component).
*   **hole\_image**: `data/temp/explosion_hole.png` - The image used for the explosion hole.
*   **particle\_effect**: `0` - No specific particle effect for the explosion.
*   **damage\_mortals**: `1` - The explosion damages mortals.
*   **physics\_explosion\_power.min**: `0.3` - Minimum physics explosion power.
*   **physics\_explosion\_power.max**: `0.5` - Maximum physics explosion power.
*   **physics\_throw\_enabled**: `1` - Enables physics-based throwing effects from the explosion.
*   **shake\_vegetation**: `1` - Shakes vegetation.
*   **sparks\_count\_max**: `20` - Maximum number of sparks.
*   **sparks\_count\_min**: `7` - Minimum number of sparks.
*   **sparks\_enabled**: `0` - Sparks are disabled.
*   **light\_enabled**: `0` - Light from the explosion is disabled.
*   **stains\_enabled**: `1` - Enables stains from the explosion.
*   **stains\_radius**: `1` - The radius of the stains.

### SpriteComponent
Defines the visual appearance of the projectile.

*   **_enabled**: `1` - Ensures this component is active.
*   **alpha**: `1` - Full opacity.
*   **image\_file**: `data/projectiles_gfx/fireball_small_magic.xml` - The sprite sheet for the projectile's graphics.
*   **offset\_x**: `2` - Horizontal offset of the sprite.
*   **offset\_y**: `2` - Vertical offset of the sprite.

### LightComponent
Adds a light source to the projectile.

*   **_enabled**: `1` - Ensures this component is active.
*   **radius**: `10` - The radius of the light emitted by the projectile.

### AudioComponent
Handles the sound effects for the projectile.

*   **file**: `data/audio/Desktop/projectiles.bank` - The audio bank containing projectile sounds.
*   **event\_root**: `player_projectiles/buckshot_magic` - The specific sound event for this projectile.

### VariableStorageComponent
Stores custom variables for the entity.

*   **name**: `projectile_file` - The name of the variable.
*   **value\_string**: `data/entities/projectiles/deck/buckshot_player.xml` - The value, pointing to the entity's own file path.