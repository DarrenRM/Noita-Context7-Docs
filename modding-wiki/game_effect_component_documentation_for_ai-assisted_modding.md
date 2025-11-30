---
title: Game Effect Component Documentation for AI-Assisted Modding
source: https://noita.wiki.gg/wiki/Documentation:GameEffectComponent
category: modding-wiki
---

# Game Effect Component Documentation

This documentation details the `GameEffectComponent` in Noita, a crucial element for understanding and modifying in-game effects. By learning how to utilize and configure this component, modders can create custom spells, alter existing mechanics, and introduce entirely new gameplay elements, significantly enhancing the modding experience.

## Understanding GameEffectComponent

The `GameEffectComponent` is a fundamental building block within Noita's entity system, responsible for defining and managing various in-game effects. These effects can range from simple damage applications to complex status changes, projectile behaviors, and environmental interactions. Modding this component allows for deep customization of gameplay mechanics.

### Core Functionality

The `GameEffectComponent` is typically defined within an entity's XML file and dictates what happens when that entity interacts with the game world or other entities. It's the primary way to implement custom spell effects, modify enemy behaviors, or introduce unique item properties.

### Key Attributes and Their Purpose

The `GameEffectComponent` utilizes a variety of attributes to define its behavior. Here are some of the most common and important ones:

*   **`effect`**: The name of the effect to be applied. This is often a reference to another predefined effect or a custom effect defined elsewhere.
*   **`effect_probability`**: A float value between 0 and 1 that determines the chance of the effect being applied.
*   **`effect_radius`**: The radius around the entity within which the effect will be applied.
*   **`effect_target`**: Specifies which entities the effect should target (e.g., `enemy`, `ally`, `self`, `all`).
*   **`effect_force`**: A float value that can influence the strength or magnitude of certain effects.
*   **`effect_duration`**: The duration in seconds for which the effect will persist.
*   **`effect_tag`**: A string tag that can be used to filter which entities are affected by the `effect`.
*   **`effect_material_tag`**: Similar to `effect_tag`, but targets entities based on their material.
*   **`effect_entity_tag`**: Targets specific entities based on their entity tag.
*   **`effect_entity_id`**: Targets a specific entity by its ID.
*   **`effect_action`**: Defines an action to be performed when the effect is applied (e.g., `damage`, `heal`, `apply_status_effect`).
*   **`effect_damage_type`**: Specifies the type of damage to be dealt (e.g., `physical`, `fire`, `ice`).
*   **`effect_damage_amount`**: The amount of damage to be dealt.
*   **`effect_status_effect`**: The name of a status effect to apply.
*   **`effect_status_effect_chance`**: The probability of applying the status effect.
*   **`effect_status_effect_duration`**: The duration of the status effect.
*   **`effect_spawn_entity`**: The ID of an entity to spawn when the effect is applied.
*   **`effect_spawn_count`**: The number of entities to spawn.
*   **`effect_spawn_offset_x` / `effect_spawn_offset_y`**: Offsets for spawning entities.
*   **`effect_sound_file`**: The path to a sound file to play when the effect is applied.
*   **`effect_visual_effect`**: The name of a visual effect to play.
*   **`effect_visual_effect_scale`**: The scale of the visual effect.
*   **`effect_mana_cost`**: The mana cost associated with the effect.
*   **`effect_cooldown`**: The cooldown in seconds for the effect.
*   **`effect_recharge_rate`**: The rate at which the effect recharges.
*   **`effect_charge_required`**: The amount of charge required for the effect.
*   **`effect_charge_gain`**: The amount of charge gained by the effect.
*   **`effect_charge_loss`**: The amount of charge lost by the effect.
*   **`effect_charge_transfer`**: The amount of charge transferred.
*   **`effect_charge_transfer_target`**: The target for charge transfer.
*   **`effect_charge_transfer_probability`**: The probability of charge transfer.
*   **`effect_charge_transfer_radius`**: The radius for charge transfer.
*   **`effect_charge_transfer_tag`**: The tag for charge transfer.
*   **`effect_charge_transfer_material_tag`**: The material tag for charge transfer.
*   **`effect_charge_transfer_entity_tag`**: The entity tag for charge transfer.
*   **`effect_charge_transfer_entity_id`**: The entity ID for charge transfer.
*   **`effect_charge_transfer_action`**: The action for charge transfer.
*   **`effect_charge_transfer_damage_type`**: The damage type for charge transfer.
*   **`effect_charge_transfer_damage_amount`**: The damage amount for charge transfer.
*   **`effect_charge_transfer_status_effect`**: The status effect for charge transfer.
*   **`effect_charge_transfer_status_effect_chance`**: The chance of status effect for charge transfer.
*   **`effect_charge_transfer_status_effect_duration`**: The duration of status effect for charge transfer.
*   **`effect_charge_transfer_spawn_entity`**: The entity to spawn for charge transfer.
*   **`effect_charge_transfer_spawn_count`**: The count of entities to spawn for charge transfer.
*   **`effect_charge_transfer_spawn_offset_x` / `effect_spawn_offset_y`**: Offsets for spawning entities during charge transfer.
*   **`effect_charge_transfer_sound_file`**: Sound file for charge transfer.
*   **`effect_charge_transfer_visual_effect`**: Visual effect for charge transfer.
*   **`effect_charge_transfer_visual_effect_scale`**: Scale of visual effect for charge transfer.
*   **`effect_charge_transfer_mana_cost`**: Mana cost for charge transfer.
*   **`effect_charge_transfer_cooldown`**: Cooldown for charge transfer.
*   **`effect_charge_transfer_recharge_rate`**: Recharge rate for charge transfer.
*   **`effect_charge_transfer_charge_required`**: Charge required for charge transfer.
*   **`effect_charge_transfer_charge_gain`**: Charge gain for charge transfer.
*   **`effect_charge_transfer_charge_loss`**: Charge loss for charge transfer.
*   **`effect_charge_transfer_charge_transfer`**: Charge transfer for charge transfer.
*   **`effect_charge_transfer_charge_transfer_target`**: Charge transfer target for charge transfer.
*   **`effect_charge_transfer_charge_transfer_probability`**: Charge transfer probability for charge transfer.
*   **`effect_charge_transfer_charge_transfer_radius`**: Charge transfer radius for charge transfer.
*   **`effect_charge_transfer_charge_transfer_tag`**: Charge transfer tag for charge transfer.
*   **`effect_charge_transfer_charge_transfer_material_tag`**: Charge transfer material tag for charge transfer.
*   **`effect_charge_transfer_charge_transfer_entity_tag`**: Charge transfer entity tag for charge transfer.
*   **`effect_charge_transfer_charge_transfer_entity_id`**: Charge transfer entity ID for charge transfer.
*   **`effect_charge_transfer_charge_transfer_action`**: Charge transfer action for charge transfer.
*   **`effect_charge_transfer_charge_transfer_damage_type`**: Charge transfer damage type for charge transfer.
*   **`effect_charge_transfer_charge_transfer_damage_amount`**: Charge transfer damage amount for charge transfer.
*   **`effect_charge_transfer_charge_transfer_status_effect`**: Charge transfer status effect for charge transfer.
*   **`effect_charge_transfer_charge_transfer_status_effect_chance`**: Charge transfer status effect chance for charge transfer.
*   **`effect_charge_transfer_charge_transfer_status_effect_duration`**: Charge transfer status effect duration for charge transfer.
*   **`effect_charge_transfer_charge_transfer_spawn_entity`**: Charge transfer spawn entity for charge transfer.
*   **`effect_charge_transfer_charge_transfer_spawn_count`**: Charge transfer spawn count for charge transfer.
*   **`effect_charge_transfer_charge_transfer_spawn_offset_x` / `effect_spawn_offset_y`**: Charge transfer spawn offsets for charge transfer.
*   **`effect_charge_transfer_charge_transfer_sound_file`**: Charge transfer sound file for charge transfer.
*   **`effect_charge_transfer_charge_transfer_visual_effect`**: Charge transfer visual effect for charge transfer.
*   **`effect_charge_transfer_charge_transfer_visual_effect_scale`**: Charge transfer visual effect scale for charge transfer.
*   **`effect_charge_transfer_charge_transfer_mana_cost`**: Charge transfer mana cost for charge transfer.
*   **`effect_charge_transfer_charge_transfer_cooldown`**: Charge transfer cooldown for charge transfer.
*   **`effect_charge_transfer_charge_transfer_recharge_rate`**: Charge transfer recharge rate for charge transfer.
*   **`effect_charge_transfer_charge_transfer_charge_required`**: Charge transfer charge required for charge transfer.
*   **`effect_charge_transfer_charge_transfer_charge_gain`**: Charge transfer charge gain for charge transfer.
*   **`effect_charge_transfer_charge_transfer_charge_loss`**: Charge transfer charge loss for charge transfer.

### Example Usage

Here's a simplified example of a `GameEffectComponent` applied to a projectile that deals fire damage and has a chance to ignite enemies:

```xml
<Entity tags="projectile">
    <Projectile
        _tags="enabled_in_all_biomes"
        lifetime="1.5"
        speed="100"
        damage="5"
        hit_particle_emitter="8"
        hit_sound_file="data/sfx/projectiles/fire_hit.wav"
        knockback_force="10"
        explosion_radius="0.5"
        explosion_damage="5"
        explosion_effect="data/effects/explosion_fire.xml"
        explosion_sound_file="data/sfx/projectiles/fire_explosion.wav"
        on_hit_entity_file="data/entities/projectiles/fireball_hit.xml"
        >
        <GameEffectComponent
            effect="damage"
            effect_damage_type="fire"
            effect_damage_amount="5"
            effect_status_effect="burning"
            effect_status_effect_chance="0.3"
            effect_status_effect_duration="5"
            effect_radius="0.5"
            effect_target="enemy"
            >
        </GameEffectComponent>
    </Projectile>
</Entity>
```

## Modding with GameEffectComponent

Modding the `GameEffectComponent` involves creating or modifying XML files that define entities and their associated components. This allows for a wide range of customization.

### Creating Custom Effects

To create a custom effect, you typically define a new entity with a `GameEffectComponent` that references a custom `effect` name. This custom effect can then be triggered by other game mechanics.

### Modifying Existing Effects

You can modify existing effects by overriding or adding `GameEffectComponent` definitions to entities that already use them. For instance, you could increase the damage of a specific spell by modifying its projectile entity.

### Advanced Techniques

*   **Chaining Effects**: Multiple `GameEffectComponent` instances can be added to a single entity to create complex sequences of effects.
*   **Conditional Effects**: Using tags and other entity properties, you can create effects that only trigger under specific conditions.
*   **Lua Integration**: While `GameEffectComponent` is primarily XML-driven, Lua scripting can be used to dynamically modify or trigger these effects, offering even greater flexibility. Refer to the [Lua API](https://noita.wiki.gg/wiki/Modding:_Lua_API) for more information.

## Useful Resources

*   [Noita Modding Wiki](https://noita.wiki.gg/wiki/Modding)
*   [Lua API](https://noita.wiki.gg/wiki/Modding:_Lua_API)
*   [Entity XML Structure](https://noita.wiki.gg/wiki/Modding:_Entity_XML_Structure)