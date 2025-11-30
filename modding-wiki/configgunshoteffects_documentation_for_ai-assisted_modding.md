---
title: ConfigGunShotEffects Documentation for AI-Assisted Modding
source: https://noita.wiki.gg/wiki/Documentation:ConfigGunShotEffects
category: modding-wiki
---

# ConfigGunShotEffects Documentation

This document details the `ConfigGunShotEffects` component in Noita, which is crucial for defining the visual and auditory feedback associated with projectile impacts. Understanding and modifying this component allows modders to create unique and immersive combat experiences by customizing how different projectiles interact with the environment and entities.

## Understanding ConfigGunShotEffects

The `ConfigGunShotEffects` component is an XML-based configuration that dictates what happens when a projectile fired from a gun hits something. This includes spawning particles, playing sounds, and triggering other visual effects.

### Core Functionality

The primary purpose of `ConfigGunShotEffects` is to link specific projectile types to a set of predefined visual and auditory effects. This is achieved through a mapping system that associates projectile IDs with effect configurations.

### File Location

These configurations are typically found within the game's data files, often in directories related to projectile or gun effects.

## Structure of ConfigGunShotEffects

The `ConfigGunShotEffects` component is defined within an XML file. The main element is `<ConfigGunShotEffects>`, which contains mappings for different projectile types.

### Projectile Mappings

Each projectile is represented by a `<Projectile>` element, which has a `name` attribute corresponding to the projectile's internal ID. Inside the `<Projectile>` element, you define the effects to be triggered.

#### Effect Types

The following effect types can be specified:

*   **`ParticleEmitter`**: Spawns a particle effect.
*   **`Sound`**: Plays a sound effect.
*   **`DamageArea`**: Creates a damage area upon impact.
*   **`SpawnEntity`**: Spawns an entity upon impact.

#### Attributes for Effects

Each effect type has specific attributes to control its behavior:

*   **`ParticleEmitter`**:
    *   `particle_effect`: The name of the particle effect to spawn (e.g., `muzzle_flash`).
    *   `offset_x`, `offset_y`: Offsets from the impact point.
    *   `scale_x`, `scale_y`: Scaling factors for the particle effect.
    *   `random_rotation`: If `1`, the particle effect will have a random rotation.
    *   `speed_min`, `speed_max`: Minimum and maximum speed for spawned particles.
    *   `lifetime_min`, `lifetime_max`: Minimum and maximum lifetime for spawned particles.
    *   `count_min`, `count_max`: Minimum and maximum number of particles to spawn.
    *   `spawn_on_ground`: If `1`, the effect only spawns on ground impacts.
    *   `spawn_on_wall`: If `1`, the effect only spawns on wall impacts.
    *   `spawn_on_entity`: If `1`, the effect only spawns on entity impacts.
    *   `spawn_on_liquid`: If `1`, the effect only spawns on liquid impacts.
    *   `spawn_on_explosion`: If `1`, the effect only spawns on explosion impacts.
    *   `spawn_on_material`: Specifies a material to spawn on (e.g., `material="dirt"`).
    *   `spawn_on_biome`: Specifies a biome to spawn in (e.g., `biome="forest"`).

*   **`Sound`**:
    *   `name`: The name of the sound effect to play (e.g., `impact_metal`).
    *   `volume`: The volume of the sound.
    *   `pitch`: The pitch of the sound.
    *   `random_volume`: If `1`, the volume will be randomized within a range.
    *   `random_pitch`: If `1`, the pitch will be randomized within a range.

*   **`DamageArea`**:
    *   `damage`: The amount of damage to deal.
    *   `radius`: The radius of the damage area.
    *   `damage_type`: The type of damage (e.g., `damage_type="explosion"`).
    *   `knockback`: The amount of knockback applied.
    *   `lifetime`: The duration of the damage area.

*   **`SpawnEntity`**:
    *   `entity_name`: The name of the entity to spawn.
    *   `offset_x`, `offset_y`: Offsets from the impact point.
    *   `spawn_on_ground`: If `1`, the entity only spawns on ground impacts.
    *   `spawn_on_wall`: If `1`, the entity only spawns on wall impacts.
    *   `spawn_on_entity`: If `1`, the entity only spawns on entity impacts.
    *   `spawn_on_liquid`: If `1`, the entity only spawns on liquid impacts.
    *   `spawn_on_explosion`: If `1`, the entity only spawns on explosion impacts.
    *   `spawn_on_material`: Specifies a material to spawn on.
    *   `spawn_on_biome`: Specifies a biome to spawn in.

### Example XML Structure

```xml
<ConfigGunShotEffects>
    <Projectile name="PROJECTILE_BULLET">
        <ParticleEmitter particle_effect="muzzle_flash" spawn_on_wall="1" spawn_on_ground="1" />
        <Sound name="impact_metal" volume="0.8" />
    </Projectile>
    <Projectile name="PROJECTILE_EXPLOSIVE">
        <ParticleEmitter particle_effect="explosion_small" spawn_on_wall="1" spawn_on_ground="1" spawn_on_entity="1" />
        <Sound name="explosion_impact" volume="1.0" />
        <DamageArea damage="50" radius="20" damage_type="explosion" knockback="100" />
    </Projectile>
</ConfigGunShotEffects>
```

## Modifying ConfigGunShotEffects

Modifying these files allows for extensive customization of projectile behavior.

### Steps for Modding

1.  **Locate the relevant XML file**: This might be within the game's `data/projectiles` or `data/gun_effects` directories. Modding often involves creating your own files and overriding or adding to existing configurations.
2.  **Identify the projectile name**: You need the exact internal name of the projectile you want to modify. This can often be found by inspecting other configuration files or using modding tools.
3.  **Add or modify `<Projectile>` entries**:
    *   To add effects to an existing projectile, find its `<Projectile>` entry and add new effect elements.
    *   To create effects for a new projectile (defined in your own mod), create a new `<Projectile>` entry with your projectile's name.
    *   To remove default effects, you might need to override the entire configuration or find a way to disable specific effects (though direct removal is less common than adding or replacing).
4.  **Choose and configure effects**: Select the desired effect types (`ParticleEmitter`, `Sound`, `DamageArea`, `SpawnEntity`) and set their attributes according to your desired outcome.
5.  **Test your changes**: Launch Noita with your mod enabled and test the projectiles to ensure the effects are as expected.

### Important Considerations

*   **Projectile Names**: Ensure you are using the correct internal projectile names. Incorrect names will result in no effects being applied.
*   **Effect Names**: Particle and sound effect names must correspond to existing assets in the game or your mod.
*   **Attribute Values**: Experiment with different attribute values to fine-tune the intensity, duration, and appearance of effects.
*   **Mod Conflicts**: Be mindful of other mods that might modify the same `ConfigGunShotEffects` files. Modding best practices often involve creating separate files for your mod and using Lua scripting to merge or override configurations.

## Useful Resources

*   [Lua API](https://noita.wiki.gg/wiki/Modding:_Lua_API) - For scripting more complex behaviors.
*   [Particle Editor](https://noita.wiki.gg/wiki/Modding:_Particle_Editor) - To create or understand particle effects.
*   [Sound Editor](https://noita.wiki.gg/wiki/Modding:_Sound_Editor) - To understand sound assets.