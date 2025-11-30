---
title: Cloud Trap Entity
category: entities
---

# Cloud Trap Entity

This document details the `cloud_trap.xml` entity, which functions as a trap that emits radioactive clouds and liquid.

## Key Components

### ParticleEmitterComponent (Radioactive Cloud)

This component is responsible for emitting the radioactive cloud particles.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `emitted_material_name`   | `cloud_radioactive` - Specifies the material to be emitted.                 |
| `count_min`, `count_max`  | `1` - Emits a single particle per emission.                                 |
| `emission_interval_min_frames`, `emission_interval_max_frames` | `3` - Emits a particle every 3 frames.                                      |
| `image_animation_file`    | `data/particles/image_emitters/cloud_circle.png` - The visual sprite for the particle. |
| `create_real_particles`   | `1` - Creates actual game particles.                                        |

### ParticleEmitterComponent (Radioactive Liquid)

This component emits radioactive liquid particles, creating a more substantial hazardous area.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `emitted_material_name`   | `radioactive_liquid` - Specifies the material to be emitted.                |
| `area_circle_radius.max`  | `28` - The maximum radius of the area where liquid particles can be emitted. |
| `emit_cosmetic_particles` | `1` - Emits particles that are primarily visual.                              |
| `create_real_particles`   | `0` - Does not create actual game particles for the liquid.                 |
| `lifetime_min`, `lifetime_max` | `8.5` to `15.5` - The duration each liquid particle exists.                 |
| `fade_based_on_lifetime`  | `1` - Particles fade out as their lifetime decreases.                       |
| `gravity.y`               | `0.0` - The liquid particles are not affected by gravity.                   |

### AudioComponent

Handles the sound effects associated with the cloud trap.

| Attribute     | Description                                     |
| :------------ | :---------------------------------------------- |
| `file`        | `data/audio/Desktop/projectiles.bank`           |
| `event_root`  | `player_projectiles/cloud` - The sound event group. |

### CameraBoundComponent

Manages how the entity interacts with the camera's view.

| Attribute     | Description                                                                 |
| :------------ | :-------------------------------------------------------------------------- |
| `max_count`   | `30` - The maximum number of these entities that can be active within camera range. |
| `distance`    | `160000` - The maximum distance from the camera for the entity to be considered. |

### LightComponent

Adds a light source to the entity.

| Attribute | Description                                     |
| :-------- | :---------------------------------------------- |
| `radius`  | `80` - The radius of the light.                 |
| `r`, `g`, `b` | `90`, `180`, `30` - The RGB color of the light (greenish). |
| `fade_out_time` | `0.5` - How long it takes for the light to fade out. |