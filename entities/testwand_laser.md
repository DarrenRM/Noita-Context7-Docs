---
title: testwand_laser
category: entities
source: https://github.com/NathanSnail/noitadata/tree/main/data/entities/_debug/testwand_laser.xml
---

# testwand_laser

This file, `testwand_laser.xml`, defines a specific type of entity within the game Noita. Based on its name and the sampled content, it appears to be a debug or test wand designed to fire laser-like projectiles. Entities in Noita are the fundamental building blocks of the game world, encompassing everything from player characters and enemies to items, projectiles, and environmental objects. This particular file likely serves as a template or configuration for a wand that has unique properties related to its laser-based attack, potentially for testing or development purposes.

## File Structure

The file is structured using XML, a hierarchical markup language. The root element is typically an `<Entity>` tag, which encapsulates all the properties and components of the entity.

*   **`<Entity>`**: This is the main tag for defining an entity.
    *   `name`: An attribute that can be used to name the entity (though it's empty in the sample).
    *   `serialize`: A boolean attribute (e.g., "1" for true) indicating if the entity should be saved and loaded.
    *   `tags`: A space-separated string of tags that categorize the entity and influence its behavior and interactions within the game. The sample shows `"teleportable_NOT,wand"`, indicating it's a wand and cannot be teleported.

*   **Child Components**: Within the `<Entity>` tag, various child tags represent different components that define the entity's behavior, appearance, and physics. These components often have numerous attributes that fine-tune their functionality.

    *   **`<_Transform>`**: This component likely handles the entity's spatial properties.
        *   `position.x`, `position.y`: Coordinates of the entity.
        *   `rotation`: The entity's rotation.
        *   `scale.x`, `scale.y`: The entity's scaling factors.

    *   **`<AbilityComponent>`**: This component seems to manage the entity's core abilities, particularly its function as a weapon or item.
        *   `ui_name`: The name displayed in the user interface.
        *   `sprite_file`: The graphical asset used for the item.
        *   `mana`, `mana_max`, `mana_charge_speed`: Attributes related to mana management.
        *   `charge_wait_frames`, `cooldown_frames`: Timing parameters for abilities.
        *   `gun_config`: A nested tag that further configures the "gun" aspect of the wand.
            *   `actions_per_round`: How many actions are performed per shot.
            *   `deck_capacity`: The number of spells the wand can hold.
            *   `reload_time`: Time taken to reload.
        *   `gunaction_config`: A nested tag that defines the properties of the projectile or action fired by the wand.
            *   `action_type`: The type of action (e.g., projectile, spell).
            *   `action_mana_drain`: Mana cost per action.
            *   `damage_projectile_add`: Base damage added to projectiles.
            *   `fire_rate_wait`: Delay between firing actions.
            *   `gravity`: The effect of gravity on the projectile.
            *   `knockback_force`: The force applied to the target upon impact.

    *   **`<AudioLoopComponent>`**: Manages audio playback associated with the entity.

    *   **`<HitboxComponent>`**: Defines the collision area of the entity.
        *   `aabb_min_x`, `aabb_max_x`, `aabb_min_y`, `aabb_max_y`: Defines the bounding box for collision detection.

    *   **`<HotspotComponent>`**: Specifies points on the entity for specific game logic, such as where projectiles originate.
        *   `offset.x`, `offset.y`: Offset from the entity's origin.

    *   **`<ItemAIKnowledgeComponent>`**: Provides information to the game's AI about the item's properties.
        *   `is_ranged_weapon`, `is_weapon`: Flags indicating its combat role.

    *   **`<SpriteComponent>`**: Defines visual elements and animations for the entity.
        *   `sprite_file`: The texture file for the sprite.
        *   `z_index`: Controls the rendering order.

    *   **`<SpriteOffsetAnimatorComponent>`**: A component that animates the offset of a sprite over time, often used for visual effects.
        *   `y_speed`, `x_speed`: Controls the speed of animation along axes.
        *   `y_amount`, `x_amount`: Controls the magnitude of the animation.

## Key Patterns

*   **Component-Based Architecture**: The file heavily relies on a component-based system, where different functionalities (rendering, physics, abilities, audio) are modularized into distinct components attached to the main `<Entity>` tag.
*   **Hierarchical Configuration**: Nested tags like `<gun_config>` and `<gunaction_config>` allow for detailed configuration of specific aspects of the entity's behavior.
*   **Attribute-Driven Behavior**: The behavior of components is extensively controlled by their attributes, allowing for fine-tuning of parameters like damage, speed, mana cost, and visual properties.
*   **Debug/Test Focus**: The presence of `_debug` in the file path and the name `testwand_laser` suggest that this entity is primarily for development and testing, likely featuring parameters that might be adjusted for gameplay balance in a final release.
*   **Sprite Animation**: The repeated use of `<SpriteOffsetAnimatorComponent>` indicates a focus on visual effects and animations for the wand and its projectiles.

## Sample Entries

**1. `AbilityComponent` (from first 100 lines):**

```xml
  <AbilityComponent 
    _enabled="0" 
    add_these_child_actions="" 
    amount_in_inventory="1" 
    base_item_file="data/entities/base_item.xml" 
    charge_wait_frames="10" 
    cooldown_frames="0" 
    current_slot_durability="100" 
    drop_as_item_on_death="1" 
    entity_count="1" 
    entity_file="" 
    fast_projectile="0" 
    is_petris_gun="0" 
    item_recoil_max="1" 
    item_recoil_offset_coeff="1" 
    item_recoil_recovery_speed="15" 
    item_recoil_rotation_coeff="5" 
    mChargeCount="0" 
    mIsInitialized="1" 
    mana="1020" 
    mana_charge_speed="400" 
    mana_max="1020" 
    max_amount_in_inventory="1" 
    max_charged_actions="0" 
    never_reload="0" 
    reload_time_frames="1" 
    rotate_hand_amount="0.7" 
    rotate_in_hand="1" 
    rotate_in_hand_amount="1" 
    shooting_reduces_amount_in_inventory="0" 
    simulate_throw_as_item="0" 
    slot_consumption_function="_get_gun_slot_durability_default" 
    sprite_file="data/items_gfx/wands/wand_0654.png" 
    swim_propel_amount="0" 
    throw_as_item="0" 
    ui_name="Lethal Rapid bolt wand" 
    use_entity_file_as_projectile_info_proxy="0" 
    use_gun_script="1" >

    <gun_config 
      actions_per_round="1" 
      deck_capacity="6" 
      reload_time="1" 
      shuffle_deck_when_empty="1" >

    </gun_config>

    <gunaction_config 
      action_description="" 
      action_draw_many_count="0" 
      action_id="" 
      action_is_dangerous_blast="0" 
      action_mana_drain="10" 
      action_max_uses="-1" 
      action_name="" 
      action_spawn_level="" 
      action_spawn_probability="" 
      action_spawn_requires_flag="" 
      action_sprite_filename="" 
      action_type="0" 
      action_unidentified_sprite_filename="data/ui_gfx/gun_actions/unidentified.png" 
      blood_count_multiplier="1" 
      bounces="0" 
      child_speed_multiplier="1" 
      custom_xml_file="" 
      damage_critical_chance="0" 
      damage_critical_multiplier="0" 
      damage_electricity_add="0" 
      damage_explosion_add="0" 
      damage_fire_add="0" 
      damage_melee_add="0" 
      damage_projectile_add="0" 
      dampening="1" 
      explosion_damage_to_materials="0" 
      explosion_radius="0" 
      extra_entities="" 
      fire_rate_wait="5" 
      friendly_fire="0" 
      game_effect_entities="" 
      gore_particles="0" 
      gravity="0" 
      knockback_force="0" 
      light="0" 
      lightning_count="0" 
      material="" 
      material_amount="0" 
      ... >
    </gunaction_config>
  </AbilityComponent>
```
This sample defines the core properties of the wand. It has a high mana capacity (`mana="1020"`, `mana_max="1020"`), a fast reload time (`reload_time_frames="1"`), and a UI name "Lethal Rapid bolt wand". The `gun_config` indicates a deck capacity of 6 spells and that the deck shuffles when empty. The `gunaction_config` shows a mana drain of 10 per action and a fire rate wait of 5 frames. The `action_type="0"` likely signifies a basic projectile or beam.

**2. `SpriteOffsetAnimatorComponent` (from lines 576-626):**

```xml
    <SpriteOffsetAnimatorComponent 
      _enabled="0" 
      _tags="enabled_in_world" 
      offset_original.x="0" 
      offset_original.y="0" 
      sprite_id="0" 
      x_amount="0" 
      x_phase="16" 
      x_phase_offset="3.94375" 
      x_speed="0" 
      y_amount="1" 
      y_speed="2.5" >

    </SpriteOffsetAnimatorComponent>
```
This component is used to animate a sprite's offset. In this case, it's configured to animate the `y` offset with a speed of `2.5` and an amount of `1`, while the `x` offset remains static. This could be used to create a subtle bobbing or pulsating effect for a visual element of the wand or its projectile. The `sprite_id="0"` suggests it targets the first sprite associated with the entity.

**3. `HitboxComponent` (from lines 181-231):**

```xml
  <HitboxComponent 
    _enabled="1" 
    _tags="enabled_in_world" 
    aabb_max_x="4" 
    aabb_max_y="4" 
    aabb_min_x="-4" 
    aabb_min_y="-4" 
    damage_multiplier="1" 
    is_enemy="0" 
    is_item="0" 
    is_player="0" 
    offset.x="0" 
    offset.y="0" >

  </HitboxComponent>
```
This component defines the physical boundaries for collision detection. The `aabb_min` and `aabb_max` attributes define a small square hitbox (from -4 to 4 on both X and Y axes) centered on the entity's origin. The flags `is_enemy`, `is_item`, and `is_player` are all set to "0", indicating this hitbox is not for a character or a collectible item in itself, but rather for the wand entity's physical presence.

## Reference

This file contains 1867 lines. For complete data, see the [full source](https://github.com/NathanSnail/noitadata/tree/main/data/entities/_debug/testwand_laser.xml).

---