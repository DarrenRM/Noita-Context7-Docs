---
title: Dark Long Verlet Vine
category: entities
---

# Dark Long Verlet Vine

This entity defines a long, dark-colored vine that uses the Verlet physics system for its movement and behavior. It's composed of multiple segments, creating a flexible and dynamic chain.

## Key Components

### VerletPhysicsComponent

This component governs the physics simulation of the vine.

| Attribute             | Description                                                                 |
| :-------------------- | :-------------------------------------------------------------------------- |
| `num_points`          | The number of points (segments) that make up the Verlet chain.              |
| `stiffness`           | Controls how rigid the vine is. Higher values mean less bending.            |
| `velocity_dampening`  | Reduces the velocity of the vine's points over time, causing it to settle.  |
| `resting_distance`    | The ideal distance between adjacent points when the vine is not under stress. |
| `pixelate_sprite_transforms` | Enables pixelation effects on the sprite as it transforms.                  |
| `follow_entity_transform` | If set to 1, the vine will follow the transform of another entity.          |
| `simulate_wind`       | Enables wind simulation for the vine.                                       |
| `wind_change_speed`   | Controls how quickly the wind's direction and intensity change.             |
| `simulate_gravity`    | Enables gravity simulation for the vine.                                    |

### Base Components

The vine is constructed from multiple `vine_dark_verlet_b_X.xml` files, which define the visual appearance and individual segments of the vine. These are appended to form the complete chain.

```xml
<Base file="data/entities/verlet_chains/vines/vine_parts/vine_dark_verlet_b_1.xml" />
<Base file="data/entities/verlet_chains/vines/vine_parts/vine_dark_verlet_b_2.xml" />
<Base file="data/entities/verlet_chains/vines/vine_parts/vine_dark_verlet_b_3.xml" />
<Base file="data/entities/verlet_chains/vines/vine_parts/vine_dark_verlet_b_4.xml" />
<Base file="data/entities/verlet_chains/vines/vine_parts/vine_dark_verlet_b_5.xml" />
<Base file="data/entities/verlet_chains/vines/vine_parts/vine_dark_verlet_b_6.xml" />
<Base file="data/entities/verlet_chains/vines/vine_parts/vine_dark_verlet_b_7.xml" />
<Base file="data/entities/verlet_chains/vines/vine_parts/vine_dark_verlet_b_4.xml" />
<Base file="data/entities/verlet_chains/vines/vine_parts/vine_dark_verlet_b_8.xml" />
<Base file="data/entities/verlet_chains/vines/vine_parts/vine_dark_verlet_b_6.xml" />
<Base file="data/entities/verlet_chains/vines/vine_parts/vine_dark_verlet_b_7.xml" />
<Base file="data/entities/verlet_chains/vines/vine_parts/vine_dark_verlet_b_8.xml" />
<Base file="data/entities/verlet_chains/vines/vine_parts/vine_dark_verlet_b_1.xml" />
<Base file="data/entities/verlet_chains/vines/vine_parts/vine_dark_verlet_b_2.xml" />
<Base file="data/entities/verlet_chains/vines/vine_parts/vine_dark_verlet_b_3.xml" />
<Base file="data/entities/verlet_chains/vines/vine_parts/vine_dark_verlet_b_4.xml" />
```

### MoveToSurfaceOnCreateComponent

This component ensures that when the vine is created, it attaches itself to the nearest surface.

| Attribute                  | Description                                                                                             |
| :------------------------- | :------------------------------------------------------------------------------------------------------ |
| `lookup_radius`            | The radius around the vine's creation point to search for a surface.                                    |
| `verlet_min_joint_distance` | The minimum distance between joints on the Verlet chain that must be maintained when attaching to a surface. |
| `type`                     | Specifies the type of attachment, in this case, `VERLET_ROPE_TWO_JOINTS`, indicating a rope-like behavior. |

### AudioComponent

This component handles the sound effects associated with the vine.

| Attribute   | Description                                     |
| :---------- | :---------------------------------------------- |
| `file`      | The audio bank file containing the sound events. |
| `event_root` | The root event name for vine-related sounds.    |