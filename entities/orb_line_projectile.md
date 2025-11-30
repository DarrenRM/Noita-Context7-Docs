---
title: Orb Line Projectile
category: entities
---

# Orb Line Projectile

This entity defines a projectile that emits various particles and has a specific lifetime. It's designed to be a visual effect rather than a damaging projectile.

## Base Entity

Inherits from `base_projectile.xml`.

### Velocity Component

*   **gravity\_y**: `180` - Applies downward gravity.
*   **air\_friction**: `0.6` - Resistance to movement in the air.
*   **mass**: `0.07` - The mass of the projectile.

## Projectile Component

This component defines the projectile's behavior.

*   **_enabled**: `1` - Enables the projectile.
*   **speed\_min**: `0` - Minimum projectile speed.
*   **speed\_max**: `0` - Maximum projectile speed.
*   **die\_on\_low\_velocity**: `0` - Does not die when velocity is low.
*   **on\_death\_explode**: `0` - Does not explode on death.
*   **on\_death\_gfx\_leave\_sprite**: `0` - Does not leave a sprite on death.
*   **on\_lifetime\_out\_explode**: `1` - Explodes when lifetime runs out.
*   **on\_collision\_die**: `0` - Does not die on collision.
*   **collide\_with\_entities**: `0` - Does not collide with entities.
*   **collide\_with\_world**: `0` - Does not collide with the world.
*   **damage**: `0` - Deals no damage.
*   **lifetime**: `30` - The projectile exists for 30 frames.

### Config Explosion

This section defines the explosion properties when the projectile's lifetime ends.

*   **never\_cache**: `1` - Prevents caching of this explosion.
*   **damage**: `0` - Explosion deals no damage.
*   **camera\_shake**: `0` - No camera shake on explosion.
*   **explosion\_radius**: `0` - No explosion radius.
*   **explosion\_sprite**: `""` - No explosion sprite.
*   **create\_cell\_material**: `""` - Does not create any material cells.
*   **particle\_effect**: `0` - No particle effect on explosion.
*   **damage\_mortals**: `0` - Does not damage mortals.
*   **physics\_explosion\_power.max**: `0` - No physics-based explosion force.
*   **sparks\_enabled**: `0` - No sparks on explosion.
*   **stains\_enabled**: `0` - No stains on explosion.

## Particle Emitters

This entity utilizes multiple `ParticleEmitterComponent`s to create visual effects.

### Emitter 1: Confusion Particles

*   **emitted\_material\_name**: `material_confusion` - Emits confusion particles.
*   **gravity.y**: `0.0` - No gravity for these particles.
*   **lifetime\_min**: `0.5` - Minimum particle lifetime.
*   **lifetime\_max**: `1.5` - Maximum particle lifetime.
*   **count\_min**: `5` - Minimum particles emitted per interval.
*   **count\_max**: `15` - Maximum particles emitted per interval.
*   **fade\_based\_on\_lifetime**: `1` - Particles fade as their lifetime decreases.
*   **airflow\_force**: `1.0`
*   **airflow\_time**: `1.9`
*   **airflow\_scale**: `0.15`
*   **emission\_interval\_min\_frames**: `1`
*   **emission\_interval\_max\_frames**: `1`
*   **emit\_cosmetic\_particles**: `1` - Emits cosmetic particles.
*   **collide\_with\_grid**: `0` - Particles do not collide with the grid.
*   **cosmetic\_force\_create**: `1` - Forces cosmetic particles to be created.
*   **x\_vel\_min**: `-20`
*   **x\_vel\_max**: `80`
*   **y\_vel\_min**: `-10`
*   **y\_vel\_max**: `10`
*   **is\_emitting**: `1` - The emitter is active.

### Emitter 2: Fire Particles

*   **emitted\_material\_name**: `fire` - Emits fire particles.
*   **gravity.y**: `0.0` - No gravity for these particles.
*   **count\_min**: `15` - Minimum particles emitted per interval.
*   **count\_max**: `25` - Maximum particles emitted per interval.
*   **lifetime\_min**: `100` - Minimum particle lifetime.
*   **lifetime\_max**: `150` - Maximum particle lifetime.
*   **emission\_interval\_min\_frames**: `1`
*   **emission\_interval\_max\_frames**: `1`
*   **create\_real\_particles**: `1` - Creates real particles.
*   **emit\_real\_particles**: `1` - Emits real particles.
*   **emit\_cosmetic\_particles**: `0` - Does not emit cosmetic particles.
*   **is\_emitting**: `1` - The emitter is active.

### Emitter 3: Smoke Particles

*   **\_tags**: `enabled_in_world,fire` - Activated when in the world and associated with fire.
*   **emitted\_material\_name**: `smoke` - Emits smoke particles.
*   **offset.y**: `-2` - Offset from the entity's origin.
*   **x\_vel\_min**: `-10`
*   **x\_vel\_max**: `10`
*   **y\_vel\_min**: `-10`
*   **y\_vel\_max**: `10`
*   **count\_min**: `5`
*   **count\_max**: `5`
*   **lifetime\_min**: `0.1`
*   **lifetime\_max**: `0.3`
*   **create\_real\_particles**: `1` - Creates real particles.
*   **emit\_cosmetic\_particles**: `0` - Does not emit cosmetic particles.
*   **emission\_interval\_min\_frames**: `60`
*   **emission\_interval\_max\_frames**: `250`
*   **is\_emitting**: `1` - The emitter is active.

### Emitter 4: Spark Particles

*   **\_tags**: `enabled_in_world,fire` - Activated when in the world and associated with fire.
*   **emitted\_material\_name**: `spark` - Emits spark particles.
*   **offset.y**: `-2` - Offset from the entity's origin.
*   **x\_pos\_offset\_min**: `-1`
*   **x\_pos\_offset\_max**: `0`
*   **y\_pos\_offset\_min**: `-2`
*   **y\_pos\_offset\_max**: `1`
*   **x\_vel\_min**: `-2`
*   **x\_vel\_max**: `2`
*   **y\_vel\_min**: `-20`
*   **y\_vel\_max**: `-10`
*   **count\_min**: `1`
*   **count\_max**: `2`
*   **lifetime\_min**: `0.3`
*   **lifetime\_max**: `0.4`
*   **create\_real\_particles**: `1` - Creates real particles.
*   **emit\_cosmetic\_particles**: `0` - Does not emit cosmetic particles.
*   **emission\_interval\_min\_frames**: `2`
*   **emission\_interval\_max\_frames**: `6`
*   **is\_emitting**: `1` - The emitter is active.

### Emitter 5: Fire Cells

*   **\_tags**: `enabled_in_world,fire` - Activated when in the world and associated with fire.
*   **emitted\_material\_name**: `fire` - Emits fire particles.
*   **offset.y**: `-2` - Offset from the entity's origin.
*   **x\_pos\_offset\_min**: `-1`
*   **x\_pos\_offset\_max**: `1`
*   **y\_pos\_offset\_min**: `-1`
*   **y\_pos\_offset\_max**: `1`
*   **x\_vel\_min**: `-2`
*   **x\_vel\_max**: `2`
*   **y\_vel\_min**: `-20`
*   **y\_vel\_max**: `-10`
*   **count\_min**: `1`
*   **count\_max**: `2`
*   **lifetime\_min**: `0.3`
*   **lifetime\_max**: `0.4`
*   **create\_real\_particles**: `1` - Creates real particles.
*   **emit\_cosmetic\_particles**: `0` - Does not emit cosmetic particles.
*   **emission\_interval\_min\_frames**: `2`
*   **emission\_interval\_max\_frames**: `6`
*   **fire\_cells\_dont\_ignite\_damagemodel**: `1` - Fire cells do not ignite damage models.

## Audio Component

*   **file**: `data/audio/Desktop/misc.bank` - Specifies the audio bank.
*   **event\_root**: `misc/orb_powder` - The root event for the audio.