---
title: Sun Seed Item
category: entities
---

# Sun Seed Item

This document details the `sunseed.xml` entity, which represents the Sun Seed item in Noita. This item has unique properties related to its physical interaction, visual representation, and its ability to convert materials.

## Key Attributes

### `Entity` Tags
- `hittable`: The entity can be hit by projectiles or other damaging sources.
- `teleportable_NOT`: The entity cannot be teleported.
- `item_physics`: The entity interacts with the physics engine as an item.
- `item_pickup`: The entity can be picked up by the player.
- `seed_a`: Likely a tag indicating it's a type of seed.

### `PhysicsBodyComponent`
- `uid`: Unique identifier for the physics body.
- `is_bullet`: Indicates it behaves like a projectile in physics.
- `hax_fix_going_through_ground`: A fix to prevent it from falling through the ground.

### `PhysicsImageShapeComponent`
- `image_file`: Specifies the visual asset for the item's physics shape (though overridden by `SpriteComponent` for in-hand/world visuals).
- `material`: The physics material used for collision.

### `PhysicsThrowableComponent`
- `max_throw_speed`: The maximum speed the item can be thrown.
- `throw_force_coeff`: A coefficient affecting the force of throws.

### `GameEffectComponent`
- `effect`: `REMOVE_FOG_OF_WAR`. When held, it clears the fog of war.
- `frames`: `-1` indicates the effect is permanent while held.

### `SpriteComponent` (In Hand)
- `image_file`: `data/items_gfx/sunseed.png`. The primary visual for the Sun Seed when held.

### `SpriteComponent` (In World)
- `image_file`: `data/particles/explosion_flare.xml`. Uses a flare effect for its world presence.
- `fog_of_war_hole`: Creates a visible hole in the fog of war.

### `ItemComponent`
- `item_name`: `$item_sunseed`. Localized name for the item.
- `ui_description`: `$itemdesc_sunseed`. Localized description.
- `ui_sprite`: `data/ui_gfx/items/sunseed.png`. The sprite used in the UI.
- `is_pickable`: `1`. Allows the player to pick it up.
- `is_equipable_forced`: `1`. The item is automatically equipped when picked up.
- `preferred_inventory`: `QUICK`. It will be placed in the quick inventory.

### `AbilityComponent`
- `throw_as_item`: `1`. Allows the item to be thrown.

### `MagicConvertMaterialComponent` (Two instances)
These components define the material conversion ability of the Sun Seed.
- `from_material_tag`: Targets specific material tags like `[sand_ground]` and `[sand_other]`.
- `to_material`: `gunpowder_unstable`. Converts the targeted materials into unstable gunpowder.
- `radius`: `64`. The area of effect for the conversion.
- `loop`: `1`. The conversion effect will repeat.
- `steps_per_frame`: `2`. Controls the speed of the conversion.

### `ParticleEmitterComponent`
- `emitted_material_name`: `spark`. Emits spark particles.
- `count_min`/`count_max`: Controls the number of particles emitted.
- `lifetime_min`/`lifetime_max`: Duration of emitted particles.
- `gravity.y`: `35`. Applies gravity to emitted particles.
- `render_ultrabright`: `1`. Particles are rendered with high brightness.
- `is_emitting`: `1`. The particle emitter is active.

---