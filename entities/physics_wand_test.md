---
title: physics_wand_test
category: entities
source: https://github.com/NathanSnail/noitadata/tree/main/data/entities/_debug/physics_wand_test.xml
---

# physics_wand_test

This file, `physics_wand_test.xml`, is part of Noita's data files and defines various entities, primarily focusing on different types of wands and their associated properties. These definitions are crucial for the game's mechanics, dictating how wands behave, what projectiles they fire, their visual appearance, and their statistical attributes like mana capacity, charge speed, and recoil. This file appears to be a testing or debugging file, indicated by its name and location within the `_debug` folder, suggesting it contains a comprehensive collection of wand configurations for development and testing purposes.

## File Structure

The file is structured using XML, a hierarchical markup language. The primary elements are `<Entity>` tags, each representing a distinct game object. These `<Entity>` tags contain various child tags that define specific components and properties of the entity.

Key structural elements observed:

*   **`<Entity>`**: The root element for each defined object. It often includes attributes like `name` (though often empty in samples), `serialize` (indicating if the entity should be saved), and `tags` (for categorization and game logic).
*   **`<_Transform>`**: Defines the spatial properties of an entity, including its `position` (x, y) and `rotation`.
*   **`<AbilityComponent>`**: A core component for entities that possess abilities, particularly wands. It holds numerous attributes related to the wand's functionality, such as `mana`, `mana_max`, `mana_charge_speed`, `charge_wait_frames`, `item_recoil_max`, and `sprite_file`.
*   **`<gun_config>`**: Nested within `<AbilityComponent>`, this tag specifies parameters related to the wand's firing mechanism, like `actions_per_round`, `deck_capacity`, and `reload_time`.
*   **`<gunaction_config>`**: Also within `<AbilityComponent>`, this tag details the properties of individual actions or projectiles fired by the wand, including `action_mana_drain`, `damage_projectile_add`, `gravity`, and `knockback_force`.
*   **`<SpriteComponent>`**: Defines the visual representation of an entity, including its `sprite_file`, `offset_x`, `offset_y`, and `z_index`.
*   **`<SpriteParticleEmitterComponent>`**: Used to define particle effects associated with an entity, such as emission properties, color, lifetime, and velocity.
*   **`<SpriteOffsetAnimatorComponent>`**: Controls animated offsets for sprites, often used for visual effects or subtle movements.

Attributes within these tags are used to fine-tune specific behaviors and appearances. For example, within `<AbilityComponent>`, `ui_name` provides the in-game name of the wand.

## Key Patterns

Several patterns are evident in the sampled content:

*   **Wand Definitions**: The file is heavily populated with `<Entity>` definitions that have the `wand` tag. These entities are characterized by the presence of `<AbilityComponent>` with `use_gun_script="1"`.
*   **Component-Based Design**: Entities are built by combining various components (e.g., `_Transform`, `AbilityComponent`, `SpriteComponent`). This modular approach allows for flexible entity creation.
*   **Attribute-Driven Behavior**: The behavior and appearance of entities are largely controlled by the attributes assigned to their components. For instance, `mana_charge_speed` directly impacts how quickly a wand can be recharged.
*   **Visual and Functional Separation**: Sprite components (`SpriteComponent`, `SpriteParticleEmitterComponent`) handle visual aspects, while components like `AbilityComponent` and `gun_config` manage gameplay mechanics.
*   **Debugging/Testing Focus**: The presence of numerous, often uniquely named wands (e.g., "Efficient Rapid bolt wand") suggests this file is used for testing various wand combinations and their effects. The `_debug` folder location further supports this.
*   **Particle Effects**: Many entities include `<SpriteParticleEmitterComponent>` to add visual flair and feedback, such as muzzle flashes, projectile trails, or impact effects.
*   **Sprite Animation**: `<SpriteOffsetAnimatorComponent>` is used to create subtle animations for sprites, likely for visual polish or to indicate certain states.

## Sample Entries

Here are a few representative examples from the sampled content:

1.  **Efficient Rapid bolt wand**:
    ```xml
    <Entity 
      name="" 
      serialize="1" 
      tags="teleportable_NOT,wand" >

      <_Transform 
        position.x="-162" 
        position.y="60" 
        rotation="-2.83815" 
        scale.x="1" 
        scale.y="-1" >
      </_Transform>

      <AbilityComponent 
        _enabled="0" 
        add_these_child_actions="" 
        amount_in_inventory="1" 
        base_item_file="data/entities/base_item.xml" 
        charge_wait_frames="10" 
        cooldown_frames="0" 
        current_slot_durability="40" 
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
        mana="930" 
        mana_charge_speed="318" 
        mana_max="930" 
        max_amount_in_inventory="1" 
        max_charged_actions="0" 
        never_reload="0" 
        reload_time_frames="0" 
        rotate_hand_amount="0.7" 
        rotate_in_hand="1" 
        rotate_in_hand_amount="1" 
        shooting_reduces_amount_in_inventory="0" 
        simulate_throw_as_item="0" 
        slot_consumption_function="_get_gun_slot_durability_default" 
        sprite_file="data/items_gfx/wands/wand_0737.png" 
        swim_propel_amount="0" 
        throw_as_item="0" 
        ui_name="Efficient Rapid bolt wand" 
        use_entity_file_as_projectile_info_proxy="0" 
        use_gun_script="1" >

        <gun_config 
          actions_per_round="1" 
          deck_capacity="26" 
          reload_time="25" 
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
          fire_rate_wait="18" 
          friendly_fire="0" 
          game_effect_entities="" 
          gore_particles="0" 
          gravity="0" 
          knockback_force="0" 
          light="0" 
          lightning_count="0" 
          material="" 
          material_amount="0" 
          pattern_degrees="0" >
        </gunaction_config>
      </AbilityComponent>
    </Entity>
    ```
    This entry defines a wand with the UI name "Efficient Rapid bolt wand". It has a high mana capacity (`mana="930"`, `mana_max="930"`) and a fast mana charge speed (`mana_charge_speed="318"`). The `gun_config` indicates a deck capacity of 26 and a reload time of 25 frames. The `gunaction_config` shows a mana drain of 10 per action and a fire rate wait of 18 frames, suggesting it fires relatively quickly.

2.  **Sprite Particle Emitter Example**:
    ```xml
    <SpriteParticleEmitterComponent 
      _enabled="0" 
      additive="1" 
      angular_velocity="0" 
      camera_bound="1" 
      camera_distance="75" 
      color.a="0.5" 
      color.b="1" 
      color.g="1" 
      color.r="1" 
      color_change.a="-0.5" 
      color_change.b="0" 
      color_change.g="0" 
      color_change.r="0" 
      count_max="1" 
      count_min="1" 
      delay="0" 
      emission_interval_max_frames="6" 
      emission_interval_min_frames="3" 
      emissive="1" 
      entity_file="" 
      entity_velocity_multiplier="0" 
      expand_randomize_position.x="0" 
      expand_randomize_position.y="0" 
      gravity.x="0" 
      gravity.y="0" 
      is_emitting="1" 
      lifetime="1.5" 
      randomize_alpha.max="0" 
      randomize_alpha.min="0" 
      randomize_angular_velocity.max="0" 
      randomize_angular_velocity.min="0" 
      randomize_animation_speed_coeff.max="0" 
      randomize_animation_speed_coeff.min="0" 
      randomize_lifetime.max="0" 
      randomize_lifetime.min="0" 
      randomize_position.max_x="5" 
      randomize_position.max_y="5" 
      randomize_position.min_x="-5" 
      randomize_position.min_y="-5" 
      randomize_position_inside_hitbox="0" 
      randomize_rotation.max="0" 
      randomize_rotation.min="0" 
      randomize_scale.max_x="0" 
      randomize_scale.max_y="0" 
      randomize_scale.min_x="0" 
      randomize_scale.min_y="0" 
      randomize_velocity.max_x="30" 
      randomize_velocity.max_y="30" >
    </SpriteParticleEmitterComponent>
    ```
    This snippet shows a `<SpriteParticleEmitterComponent>` configured to emit particles. It has a lifetime of 1.5 seconds, emits 1-1 particles per interval, and has randomized velocity up to 30 units in both x and y directions. The `color.a="0.5"` and `color_change.a="-0.5"` suggest fading particles. This component is likely attached to a wand or projectile to create visual effects.

3.  **Sprite Component with Unidentified Icon**:
    ```xml
    <SpriteComponent 
      _enabled="0" 
      _tags="enabled_in_world,item_unidentified" 
      additive="0" 
      alpha="1" 
      emissive="0" 
      fog_of_war_hole="0" 
      has_special_scale="0" 
      image_file="data/ui_gfx/gun_actions/unidentified.png" 
      is_text_sprite="0" 
      kill_entity_after_finished="0" 
      never_ragdollify_on_death="0" 
      next_rect_animation="" 
      offset_x="8" 
      offset_y="17" 
      rect_animation="" 
      smooth_filtering="0" 
      special_scale_x="1" 
      special_scale_y="1" 
      text="" 
      transform_offset.x="0" 
      transform_offset.y="0" 
      ui_is_parent="0" 
      update_transform="1" 
      update_transform_rotation="1" 
      visible="1" 
      z_index="0.595" >
    </SpriteComponent>
    ```
    This `<SpriteComponent>` defines a visual element using the `data/ui_gfx/gun_actions/unidentified.png` image. The `_tags="enabled_in_world,item_unidentified"` suggest this sprite is used to represent an unidentified item or action within the game world. The `offset_x` and `offset_y` values position it relative to its parent entity.

## Reference

This file contains 6829 lines. For complete data, see the [full source](https://github.com/NathanSnail/noitadata/tree/main/data/entities/_debug/physics_wand_test.xml).

---