---
title: Tentacle 2 Entity
category: guides
---

<Entity name="tentacle_2">
  <Sprite
    filename="data/entities/animals/boss_pit/tentacle.png"
    offset_x="0"
    offset_y="0"
    default_animation="stand"
  >
    <RectAnimation
      name="stand"
      pos_x="4"
      pos_y="0"
      frame_count="1"
      frame_width="4"
      frame_height="11"
      frame_wait="1"
      frames_per_row="8"
      loop="1"
    />
  </Sprite>
  <Hitbox
    _tags="enemy"
    damage_on_touch="1"
    damage_to_player="10"
    is_enemy="1"
    is_wooden="0"
    mass="1"
    offset_x="0"
    offset_y="0"
    radius="3"
    surface_type="wood"
  />
  <DamageModelComponent
    air_resistance="1"
    blood_material="blood"
    blood_particle_name="blood"
    collision_resistance="0"
    damage_to_player="10"
    death_material="death"
    explosion_damage="0"
    explosion_radius="0"
    fire_damage="0"
    is_wooden="0"
    lava_damage="0"
    mass="1"
    poison_damage="0"
    ragdoll_force_multiplier="0"
    ragdoll_on_death="0"
    slowdown_on_hit="0"
    speed_multiplier_on_hit="0"
    water_damage="0"
  />
  <ExplosionComponent
    damage="0"
    radius="0"
  />
  <ParticleEmitterComponent
    emitted_material_name="spark"
    emission_interval="0.05"
    entity_file="data/particles/spark.xml"
    force_emit_at_random_point="1"
    is_emitting="0"
    random_direction="1"
    random_rotation="1"
    rotation_speed="100"
    spawn_position_offset_x="0"
    spawn_position_offset_y="0"
    speed_min="0"
    speed_max="0"
    use_emitter_velocity="1"
  />
  <LuaComponent
    script_path="data/entities/animals/boss_pit/tentacle_2.lua"
  />
</Entity>
```

---
title: Tentacle 2 Entity
category: entities
---

# Tentacle 2 Entity

This document describes the `tentacle_2.xml` entity, a component of the boss pit in Noita. It details its visual representation, hitbox, damage properties, and associated Lua script.

## Sprite

The `Sprite` element defines the visual appearance of the tentacle.

### Key Attributes:

*   **filename**: `data/entities/animals/boss_pit/tentacle.png` - The texture file used for the sprite.
*   **default\_animation**: `"stand"` - The animation to play by default.

#### Animation: `stand`

*   **frame\_count**: `1` - Number of frames in the animation.
*   **frame\_width**: `4` - Width of each frame.
*   **frame\_height**: `11` - Height of each frame.
*   **frame\_wait**: `1` - Delay between frames.
*   **frames\_per\_row**: `8` - Number of frames per row in the sprite sheet.
*   **loop**: `1` - Whether the animation should loop.

## Hitbox

The `Hitbox` element defines the physical collision area of the tentacle.

### Key Attributes:

*   **\_tags**: `"enemy"` - Tags associated with the hitbox, indicating it's an enemy.
*   **damage\_on\_touch**: `1` - Whether touching the hitbox deals damage.
*   **damage\_to\_player**: `10` - The amount of damage dealt to the player on touch.
*   **is\_enemy**: `1` - Marks this as an enemy entity.
*   **mass**: `1` - The mass of the hitbox.
*   **radius**: `3` - The radius of the circular hitbox.

## DamageModelComponent

The `DamageModelComponent` defines how the entity interacts with damage and its physical properties related to damage.

### Key Attributes:

*   **damage\_to\_player**: `10` - The amount of damage this entity deals to the player.
*   **mass**: `1` - The mass of the entity.
*   **blood\_material**: `"blood"` - The material of blood particles spawned on damage.
*   **blood\_particle\_name**: `"blood"` - The name of the blood particle effect.
*   **death\_material**: `"death"` - The material associated with the entity's death.

## ParticleEmitterComponent

This component is configured to emit `spark` particles.

### Key Attributes:

*   **emitted\_material\_name**: `"spark"` - The material of the particles being emitted.
*   **emission\_interval**: `0.05` - The time in seconds between particle emissions.
*   **entity\_file**: `data/particles/spark.xml` - The entity file for the emitted particles.
*   **is\_emitting**: `0` - Currently set to not emit particles by default.

## LuaComponent

The `LuaComponent` links a Lua script to this entity, allowing for custom behavior.

### Key Attributes:

*   **script\_path**: `data/entities/animals/boss_pit/tentacle_2.lua` - The path to the associated Lua script.