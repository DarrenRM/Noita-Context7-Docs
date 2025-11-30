---
title: Orb 04 - Necromancy
category: entities
---

# Orb 04 - Necromancy

This document details the configuration for the Necromancy Orb in Noita, designed for AI-assisted modding.

## Entity Configuration

The core entity defines the orb's properties and its base behavior.

### Key Attributes

| Attribute        | Value                               | Description                                                                 |
| :--------------- | :---------------------------------- | :-------------------------------------------------------------------------- |
| `tags`           | `hittable,teleportable_NOT`         | Allows the orb to be hit and prevents it from being teleported.             |
| `Base file`      | `data/entities/items/orbs/orb_base.xml` | Inherits fundamental orb properties from a shared base configuration.       |

### Orb Component

| Attribute | Value | Description                               |
| :-------- | :---- | :---------------------------------------- |
| `orb_id`  | `4`   | Unique identifier for this specific orb.  |

### Sprite Component

| Attribute     | Value                               | Description                                                               |
| :------------ | :---------------------------------- | :------------------------------------------------------------------------ |
| `image_file`  | `data/items_gfx/orbs/orb_04.xml`    | Specifies the graphical asset used to render the orb.                     |

### Variable Storage Component

| Attribute     | Value        | Description                                                               |
| :------------ | :----------- | :------------------------------------------------------------------------ |
| `name`        | `card_name`  | Stores a variable related to the orb's in-game name or associated card. |
| `value_string`| `NECROMANCY` | The string value assigned to `card_name`, identifying it as Necromancy.   |

## Particle Effects

A nested entity is used to apply particle effects to the orb.

### Inherit Transform Component

| Attribute   | Value | Description                                                               |
| :---------- | :---- | :------------------------------------------------------------------------ |
| `position.x`| `0`   | X-axis offset for the particle effect relative to the orb's center.       |
| `position.y`| `-11` | Y-axis offset for the particle effect relative to the orb's center.       |

### Base File

| Attribute | Value                                   | Description                                                              |
| :-------- | :-------------------------------------- | :----------------------------------------------------------------------- |
| `Base file` | `data/entities/items/orbs/orb_particles_base.xml` | Inherits standard particle effect configurations for orbs.               |