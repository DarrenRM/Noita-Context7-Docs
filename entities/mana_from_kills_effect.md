---
title: Mana From Kills Effect
category: entities
---

# Mana From Kills Effect

This entity defines the visual and functional components for the "Mana From Kills" perk effect in Noita. When a player gains this perk, this entity is applied to them, granting mana regeneration and a visual indicator.

## Key Components

### ParticleEmitterComponent

This component handles the visual effect of mana regeneration, emitting particles that resemble magical liquid.

| Attribute                 | Description                                                              |
| :------------------------ | :----------------------------------------------------------------------- |
| `emitted_material_name`   | The material of the particles to be emitted (`magic_liquid_mana_regeneration`). |
| `lifetime_min`, `lifetime_max` | The minimum and maximum duration (in seconds) for each emitted particle. |
| `count_min`, `count_max`  | The minimum and maximum number of particles emitted per emission cycle.  |
| `area_circle_radius.max`  | The maximum radius of the circular area from which particles are emitted. |
| `x_vel_min`, `x_vel_max`  | The minimum and maximum horizontal velocity of emitted particles.        |
| `y_vel_min`, `y_vel_max`  | The minimum and maximum vertical velocity of emitted particles.          |
| `is_emitting`             | Controls whether the particle emitter is active (`1` for active).        |

### GameEffectComponent

This component applies the actual game effect of mana regeneration to the player.

| Attribute | Description                                     |
| :-------- | :---------------------------------------------- |
| `effect`  | The type of game effect to apply (`MANA_REGENERATION`). |
| `frames`  | The duration (in frames) for which the effect lasts. |

### UIIconComponent

This component defines how the perk's status effect is displayed in the game's user interface.

| Attribute           | Description                                                              |
| :------------------ | :----------------------------------------------------------------------- |
| `name`              | The internal name for the UI element (`$perk_mana_from_kills`).          |
| `description`       | The localized description text for the status effect (`$statusdesc_mana_regeneration`). |
| `icon_sprite_file`  | The path to the sprite file used for the icon (`data/ui_gfx/status_indicators/mana_regeneration.png`). |
| `display_in_hud`    | Controls whether the icon is displayed in the Heads-Up Display (`1` for displayed). |

---