---
title: Barrel Entity Configuration
category: entities
---

# Barrel Entity Configuration

This document details the configuration of a basic barrel entity in Noita, focusing on its damage, explosion, hitbox, and physics properties.

## Entity: Barrel

The root `<Entity>` tag defines a generic object with the `hittable` tag, indicating it can be interacted with by damage.

### Key Components:

*   **`<DamageModelComponent>`**: Manages how the entity takes damage and its health.
    *   `hp`: Current health points (2).
    *   `max_hp`: Maximum health points (2).
    *   `falling_damage_damage_max`: Maximum damage from falling (1.2).
    *   `falling_damage_damage_min`: Minimum damage from falling (0.1).
    *   `falling_damage_height_max`: Maximum height for falling damage (250).
    *   `falling_damage_height_min`: Minimum height for falling damage (70).
    *   `falling_damages`: Enables falling damage (1).
    *   `fire_damage_amount`: Amount of damage from fire (0.2).
    *   `air_in_lungs`: Simulates air in lungs for damage calculation (5).
    *   `air_needed`: Air required to avoid damage (0).
    *   `materials_that_damage`: Materials that can damage this entity (e.g., "acid").
    *   `materials_how_much_damage`: How much damage materials inflict (0.1).

*   **`<ExplodeOnDamageComponent>`**: Defines behavior when the entity is damaged or destroyed.
    *   `explode_on_death_percent`: Trigger explosion upon death (1, meaning 100%).
    *   **`<config_explosion>`**: Detailed explosion parameters.
        *   `damage`: Damage dealt by the explosion (4).
        *   `damage_mortals`: Damage dealt to living entities (1).
        *   `explosion_radius`: Radius of the explosion (40).
        *   `explosion_sprite`: Visual effect for the explosion.
        *   `create_cell_material`: Material created by the explosion (e.g., "fire").
        *   `create_cell_probability`: Chance to create explosion cells (50).
        *   `camera_shake`: Intensity of camera shake (40).
        *   `hole_enabled`: Whether the explosion creates holes (1).
        *   `hole_image`: Image used for the explosion hole.
        *   `light_enabled`: Whether the explosion creates light (1).
        *   `light_r`, `light_g`, `light_b`: RGB values for the explosion light.
        *   `physics_explosion_power.max`: Maximum physics force applied by the explosion (5).
        *   `sparks_enabled`: Whether sparks are generated (1).
        *   `sparks_count_min`, `sparks_count_max`: Range for spark count.

*   **`<HitboxComponent>`**: Defines the physical collision area of the entity.
    *   `aabb_min_x`, `aabb_max_x`, `aabb_min_y`, `aabb_max_y`: Axis-aligned bounding box coordinates.
    *   `is_enemy`, `is_item`, `is_player`: Flags indicating the entity's role (all set to 0, meaning it's a generic object).

*   **`<MaterialInventoryComponent>`**: Manages the materials contained within the entity.
    *   `drop_as_item`: Whether the materials drop as an item on destruction (0).
    *   `count_per_material_type`: This section lists material counts. In this specific configuration, all material counts are set to 0, indicating the barrel is empty of any specific materials.

*   **`<PhysicsBodyComponent>`**: Defines the physical properties of the entity for the physics engine.
    *   `allow_sleep`: Allows the body to sleep when inactive (1).
    *   `linear_damping`, `angular_damping`: Damping forces (0).
    *   `fixed_rotation`: Prevents rotation (0).
    *   `is_static`: Whether the body is static (0).

*   **`<PhysicsImageShapeComponent>`**: Links a visual sprite to the physics body.
    *   `image_file`: The sprite used for the barrel's appearance.
    *   `material`: The physics material assigned to the shape (e.g., "plastic").
    *   `centered`: Whether the image is centered (1).

```xml
<Entity 
  name="" 
  tags="hittable" >

  <DamageModelComponent 
    _enabled="1" 
    air_in_lungs="5" 
    air_in_lungs_max="5" 
    air_lack_of_damage="0.2" 
    air_needed="0" 
    blood_material="oil" 
    drop_items_on_death="0" 
    falling_damage_damage_max="1.2" 
    falling_damage_damage_min="0.1" 
    falling_damage_height_max="250" 
    falling_damage_height_min="70" 
    falling_damages="1" 
    fire_damage_amount="0.2" 
    fire_probability_of_ignition="0" 
    hp="2" 
    is_on_fire="0" 
    materials_create_messages="0" 
    materials_damage="0" 
    materials_how_much_damage="0.1" 
    materials_that_create_messages="meat" 
    materials_that_damage="acid" 
    max_hp="2" 
    ragdoll_filenames_file="" 
    ragdoll_material="" 
    ragdoll_offset_y="0" >
  </DamageModelComponent>

  <ExplodeOnDamageComponent 
    _enabled="1" 
    explode_on_damage_percent="0" 
    explode_on_death_percent="1" >
    <config_explosion 
      camera_shake="40" 
      create_cell_material="fire" 
      create_cell_probability="50" 
      damage="4" 
      damage_mortals="1" 
      explosion_radius="40" 
      explosion_sprite="data/particles/explosion_032.xml" 
      explosion_sprite_lifetime="10" 
      gore_particle_count="1" 
      hole_destroy_liquid="0" 
      hole_enabled="1" 
      hole_image="data/temp/explosion_hole.png" 
      light_b="180" 
      light_enabled="1" 
      light_fade_time="0.08" 
      light_g="217" 
      light_r="255" 
      max_durability_to_destroy="10" 
      particle_effect="1" 
      physics_explosion_power.max="5" 
      physics_multiplier_ragdoll_force="1" 
      physics_throw_enabled="1" 
      ray_energy="180000" 
      shake_vegetation="1" 
      sparks_count_max="20" 
      sparks_count_min="7" 
      sparks_enabled="1" 
      stains_enabled="1" 
      stains_image="data/temp/explosion_stain.png" 
      stains_radius="0" >
    </config_explosion>
  </ExplodeOnDamageComponent>

  <HitboxComponent 
    _enabled="1" 
    aabb_max_x="4" 
    aabb_max_y="5.5" 
    aabb_min_x="-4" 
    aabb_min_y="-5.5" 
    is_enemy="0" 
    is_item="0" 
    is_player="0" >
  </HitboxComponent>

  <MaterialInventoryComponent 
    _enabled="1" 
    drop_as_item="0" >
    <count_per_material_type>
      <!-- All material counts are 0 in this configuration -->
      <E i="0"><e>0</e></E>
      <E i="1"><e>0</e></E>
      <E i="2"><e>0</e></E>
      <E i="3"><e>0</e></E>
      <E i="4"><e>0</e></E>
      <E i="5"><e>0</e></E>
      <E i="6"><e>0</e></E>
      <E i="7"><e>0</e></E>
      <E i="8"><e>0</e></E>
      <E i="9"><e>0</e></E>
      <E i="10"><e>0</e></E>
      <E i="11"><e>0</e></E>
      <E i="12"><e>0</e></E>
      <E i="13"><e>0</e></E>
      <E i="14"><e>0</e></E>
      <E i="15"><e>0</e></E>
      <E i="16"><e>0</e></E>
      <E i="17"><e>0</e></E>
      <E i="18"><e>0</e></E>
      <E i="19"><e>0</e></E>
      <E i="20"><e>0</e></E>
      <E i="21"><e>0</e></E>
      <E i="22"><e>0</e></E>
      <E i="23"><e>0</e></E>
      <E i="24"><e>0</e></E>
      <E i="25"><e>0</e></E>
      <E i="26"><e>0</e></E>
      <E i="27"><e>0</e></E>
      <E i="28"><e>0</e></E>
      <E i="29"><e>0</e></E>
      <E i="30"><e>0</e></E>
      <E i="31"><e>0</e></E>
      <E i="32"><e>0</e></E>
      <E i="33"><e>0</e></E>
      <E i="34"><e>0</e></E>
      <E i="35"><e>0</e></E>
      <E i="36"><e>0</e></E>
      <E i="37"><e>0</e></e>
      <E i="38"><e>0</e></e>
      <E i="39"><e>0</e></e>
      <E i="40"><e>0</e></e>
      <E i="41"><e>0</e></e>
      <E i="42"><e>0</e></e>
      <E i="43"><e>0</e></e>
      <E i="44"><e>0</e></e>
      <E i="45"><e>0</e></e>
      <E i="46"><e>0</e></e>
      <E i="47"><e>0</e></e>
      <E i="48"><e>0</e></e>
      <E i="49"><e>0</e></e>
      <E i="50"><e>0</e></e>
      <E i="51"><e>0</e></e>
      <E i="52"><e>0</e></e>
      <E i="53"><e>0</e></e>
      <E i="54"><e>0</e></e>
      <E i="55"><e>0</e></e>
      <E i="56"><e>0</e></e>
      <E i="57"><e>0</e></e>
      <E i="58"><e>0</e></e>
      <E i="59"><e>0</e></e>
      <E i="60"><e>0</e></e>
      <E i="61"><e>0</e></e>
      <E i="62"><e>0</e></e>
      <E i="63"><e>0</e></e>
      <E i="64"><e>0</e></e>
      <E i="65"><e>0</e></e>
      <E i="66"><e>0</e></e>
      <E i="67"><e>0</e></e>
      <E i="68"><e>0</e></e>
      <E i="69"><e>0</e></e>
      <E i="70"><e>0</e></e>
      <E i="71"><e>0</e></e>
      <E i="72"><e>0</e></e>
      <E i="73"><e>0</e></e>
      <E i="74"><e>0</e></e>
      <E i="75"><e>0</e></e>
      <E i="76"><e>0</e></e>
      <E i="77"><e>0</e></e>
      <E i="78"><e>0</e></e>
      <E i="79"><e>0</e></e>
      <E i="80"><e>0</e></e>
      <E i="81"><e>0</e></e>
      <E i="82"><e>0</e></e>
      <E i="83"><e>0</e></e>
      <E i="84"><e>0</e></e>
      <E i="85"><e>0</e></e>
      <E i="86"><e>0</e></e>
    </count_per_material_type>
  </MaterialInventoryComponent>

  <PhysicsBodyComponent 
    _enabled="1" 
    allow_sleep="1" 
    angular_damping="0" 
    fixed_rotation="0" 
    is_bullet="0" 
    is_character="0" 
    is_enabled="1" 
    is_static="0" 
    linear_damping="0" 
    uid="0" >
  </PhysicsBodyComponent>

  <PhysicsImageShapeComponent 
    _enabled="1" 
    body_id="0" 
    centered="1" 
    image_file="data/items_gfx/barrel.png" 
    is_circle="0" 
    material="plastic" >
  </PhysicsImageShapeComponent>
</Entity>
```