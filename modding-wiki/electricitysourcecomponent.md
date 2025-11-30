---
title: ElectricitySourceComponent
source: https://noita.wiki.gg/wiki/Documentation:ElectricitySourceComponent
category: modding-wiki
---

# ElectricitySourceComponent

This documentation page explains the `ElectricitySourceComponent` in Noita, a crucial component for creating entities that generate or interact with electricity. Understanding this component is vital for modders who wish to implement custom electrical effects, power systems, or unique entity behaviors related to electricity.

## Overview

The `ElectricitySourceComponent` is attached to entities in Noita to define their electrical properties. It dictates how an entity acts as a source of electricity, including its voltage, current, and how it connects to other electrical components. This allows for the creation of complex electrical circuits and interactions within the game.

## Component Properties

The `ElectricitySourceComponent` has several properties that can be configured in an entity's XML definition. These properties control the behavior and characteristics of the electrical source.

### `voltage`

*   **Type:** `float`
*   **Description:** The voltage output of the electricity source. Higher voltage can drive more current or power more demanding devices.
*   **Default:** `1.0`

### `current`

*   **Type:** `float`
*   **Description:** The current output of the electricity source. This determines how much electrical energy the source can deliver.
*   **Default:** `1.0`

### `max_current`

*   **Type:** `float`
*   **Description:** The maximum current the source can safely output. Exceeding this limit might cause damage or other effects depending on the implementation.
*   **Default:** `1.0`

### `power_flow_type`

*   **Type:** `enum`
*   **Description:** Defines the type of power flow this source provides.
*   **Possible Values:**
    *   `POWER_FLOW_TYPE_DIRECT`: Direct current.
    *   `POWER_FLOW_TYPE_ALTERNATING`: Alternating current.
    *   `POWER_FLOW_TYPE_PULSE`: Pulsed current.

### `power_flow_frequency`

*   **Type:** `float`
*   **Description:** The frequency of the power flow, relevant for `POWER_FLOW_TYPE_ALTERNATING` and `POWER_FLOW_TYPE_PULSE`.
*   **Default:** `1.0`

### `power_flow_duty_cycle`

*   **Type:** `float`
*   **Description:** The duty cycle of the power flow, relevant for `POWER_FLOW_TYPE_PULSE`. Represents the proportion of time the pulse is active.
*   **Default:** `0.5`

### `power_flow_phase`

*   **Type:** `float`
*   **Description:** The phase of the power flow, relevant for `POWER_FLOW_TYPE_ALTERNATING`.
*   **Default:** `0.0`

### `power_flow_waveform`

*   **Type:** `enum`
*   **Description:** Defines the shape of the waveform for alternating or pulsed current.
*   **Possible Values:**
    *   `POWER_FLOW_WAVEFORM_SINE`: Sine wave.
    *   `POWER_FLOW_WAVEFORM_SQUARE`: Square wave.
    *   `POWER_FLOW_WAVEFORM_TRIANGLE`: Triangle wave.
    *   `POWER_FLOW_WAVEFORM_SAWTOOTH`: Sawtooth wave.

### `power_flow_amplitude`

*   **Type:** `float`
*   **Description:** The amplitude of the power flow waveform.
*   **Default:** `1.0`

### `power_flow_offset`

*   **Type:** `float`
*   **Description:** An offset applied to the power flow waveform.
*   **Default:** `0.0`

### `power_flow_delay`

*   **Type:** `float`
*   **Description:** A delay before the power flow begins.
*   **Default:** `0.0`

### `power_flow_duration`

*   **Type:** `float`
*   **Description:** The duration for which the power flow will last.
*   **Default:** `-1.0` (infinite)

### `power_flow_cooldown`

*   **Type:** `float`
*   **Description:** The cooldown period after the power flow ends before it can start again.
*   **Default:** `0.0`

### `power_flow_target_entity_tags`

*   **Type:** `string`
*   **Description:** A comma-separated list of entity tags that this power source will attempt to connect to. If empty, it may connect to any compatible entity.

### `power_flow_target_component_tags`

*   **Type:** `string`
*   **Description:** A comma-separated list of component tags that this power source will attempt to connect to. If empty, it may connect to any compatible component.

### `power_flow_target_entity_id`

*   **Type:** `string`
*   **Description:** The specific entity ID that this power source will attempt to connect to.

### `power_flow_target_component_id`

*   **Type:** `string`
*   **Description:** The specific component ID that this power source will attempt to connect to.

### `power_flow_target_tag`

*   **Type:** `string`
*   **Description:** A general tag that this power source will attempt to connect to. This is a broader targeting mechanism.

### `power_flow_target_tag_type`

*   **Type:** `enum`
*   **Description:** Specifies the type of tag being targeted by `power_flow_target_tag`.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_TYPE_ENTITY`: Targets entity tags.
    *   `POWER_FLOW_TARGET_TAG_TYPE_COMPONENT`: Targets component tags.

### `power_flow_target_tag_match_mode`

*   **Type:** `enum`
*   **Description:** How the `power_flow_target_tag` should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tags are present.

### `power_flow_target_tag_match_mode_component`

*   **Type:** `enum`
*   **Description:** How component tags should be matched when targeting components.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component tags are present.

### `power_flow_target_tag_match_mode_entity`

*   **Type:** `enum`
*   **Description:** How entity tags should be matched when targeting entities.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity tags are present.

### `power_flow_target_tag_match_mode_entity_id`

*   **Type:** `enum`
*   **Description:** How entity IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity IDs are present.

### `power_flow_target_tag_match_mode_component_id`

*   **Type:** `enum`
*   **Description:** How component IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component IDs are present.

### `power_flow_target_tag_match_mode_tag`

*   **Type:** `enum`
*   **Description:** How general tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tags are present.

### `power_flow_target_tag_match_mode_tag_type`

*   **Type:** `enum`
*   **Description:** How the type of tag being matched should be handled.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tag types are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tag types are present.

### `power_flow_target_tag_match_mode_component_tag`

*   **Type:** `enum`
*   **Description:** How component tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component tags are present.

### `power_flow_target_tag_match_mode_entity_tag`

*   **Type:** `enum`
*   **Description:** How entity tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity tags are present.

### `power_flow_target_tag_match_mode_entity_id_tag`

*   **Type:** `enum`
*   **Description:** How entity IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity IDs are present.

### `power_flow_target_tag_match_mode_component_id_tag`

*   **Type:** `enum`
*   **Description:** How component IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component IDs are present.

### `power_flow_target_tag_match_mode_tag_tag`

*   **Type:** `enum`
*   **Description:** How general tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tags are present.

### `power_flow_target_tag_match_mode_tag_type_tag`

*   **Type:** `enum`
*   **Description:** How the type of tag being matched should be handled.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tag types are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tag types are present.

### `power_flow_target_tag_match_mode_component_tag_tag`

*   **Type:** `enum`
*   **Description:** How component tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component tags are present.

### `power_flow_target_tag_match_mode_entity_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity tags are present.

### `power_flow_target_tag_match_mode_entity_id_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity IDs are present.

### `power_flow_target_tag_match_mode_component_id_tag_tag`

*   **Type:** `enum`
*   **Description:** How component IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component IDs are present.

### `power_flow_target_tag_match_mode_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How general tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tags are present.

### `power_flow_target_tag_match_mode_tag_type_tag_tag`

*   **Type:** `enum`
*   **Description:** How the type of tag being matched should be handled.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tag types are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tag types are present.

### `power_flow_target_tag_match_mode_component_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component tags are present.

### `power_flow_target_tag_match_mode_entity_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity tags are present.

### `power_flow_target_tag_match_mode_entity_id_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity IDs are present.

### `power_flow_target_tag_match_mode_component_id_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component IDs are present.

### `power_flow_target_tag_match_mode_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How general tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tags are present.

### `power_flow_target_tag_match_mode_tag_type_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How the type of tag being matched should be handled.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tag types are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tag types are present.

### `power_flow_target_tag_match_mode_component_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component tags are present.

### `power_flow_target_tag_match_mode_entity_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity tags are present.

### `power_flow_target_tag_match_mode_entity_id_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity IDs are present.

### `power_flow_target_tag_match_mode_component_id_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component IDs are present.

### `power_flow_target_tag_match_mode_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How general tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tags are present.

### `power_flow_target_tag_match_mode_tag_type_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How the type of tag being matched should be handled.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tag types are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tag types are present.

### `power_flow_target_tag_match_mode_component_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component tags are present.

### `power_flow_target_tag_match_mode_entity_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity tags are present.

### `power_flow_target_tag_match_mode_entity_id_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity IDs are present.

### `power_flow_target_tag_match_mode_component_id_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component IDs are present.

### `power_flow_target_tag_match_mode_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How general tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tags are present.

### `power_flow_target_tag_match_mode_tag_type_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How the type of tag being matched should be handled.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tag types are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tag types are present.

### `power_flow_target_tag_match_mode_component_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component tags are present.

### `power_flow_target_tag_match_mode_entity_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity tags are present.

### `power_flow_target_tag_match_mode_entity_id_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity IDs are present.

### `power_flow_target_tag_match_mode_component_id_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component IDs are present.

### `power_flow_target_tag_match_mode_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How general tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tags are present.

### `power_flow_target_tag_match_mode_tag_type_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How the type of tag being matched should be handled.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tag types are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tag types are present.

### `power_flow_target_tag_match_mode_component_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component tags are present.

### `power_flow_target_tag_match_mode_entity_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity tags are present.

### `power_flow_target_tag_match_mode_entity_id_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity IDs are present.

### `power_flow_target_tag_match_mode_component_id_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component IDs are present.

### `power_flow_target_tag_match_mode_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How general tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tags are present.

### `power_flow_target_tag_match_mode_tag_type_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How the type of tag being matched should be handled.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tag types are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tag types are present.

### `power_flow_target_tag_match_mode_component_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component tags are present.

### `power_flow_target_tag_match_mode_entity_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity tags are present.

### `power_flow_target_tag_match_mode_entity_id_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity IDs are present.

### `power_flow_target_tag_match_mode_component_id_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component IDs are present.

### `power_flow_target_tag_match_mode_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How general tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tags are present.

### `power_flow_target_tag_match_mode_tag_type_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How the type of tag being matched should be handled.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tag types are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tag types are present.

### `power_flow_target_tag_match_mode_component_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component tags are present.

### `power_flow_target_tag_match_mode_entity_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity tags are present.

### `power_flow_target_tag_match_mode_entity_id_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity IDs are present.

### `power_flow_target_tag_match_mode_component_id_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component IDs are present.

### `power_flow_target_tag_match_mode_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How general tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tags are present.

### `power_flow_target_tag_match_mode_tag_type_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How the type of tag being matched should be handled.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tag types are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tag types are present.

### `power_flow_target_tag_match_mode_component_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component tags are present.

### `power_flow_target_tag_match_mode_entity_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity tags are present.

### `power_flow_target_tag_match_mode_entity_id_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity IDs are present.

### `power_flow_target_tag_match_mode_component_id_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component IDs are present.

### `power_flow_target_tag_match_mode_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How general tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tags are present.

### `power_flow_target_tag_match_mode_tag_type_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How the type of tag being matched should be handled.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tag types are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tag types are present.

### `power_flow_target_tag_match_mode_component_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component tags are present.

### `power_flow_target_tag_match_mode_entity_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity tags are present.

### `power_flow_target_tag_match_mode_entity_id_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity IDs are present.

### `power_flow_target_tag_match_mode_component_id_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component IDs are present.

### `power_flow_target_tag_match_mode_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How general tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tags are present.

### `power_flow_target_tag_match_mode_tag_type_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How the type of tag being matched should be handled.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tag types are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tag types are present.

### `power_flow_target_tag_match_mode_component_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component tags are present.

### `power_flow_target_tag_match_mode_entity_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity tags are present.

### `power_flow_target_tag_match_mode_entity_id_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity IDs are present.

### `power_flow_target_tag_match_mode_component_id_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component IDs are present.

### `power_flow_target_tag_match_mode_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How general tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tags are present.

### `power_flow_target_tag_match_mode_tag_type_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How the type of tag being matched should be handled.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tag types are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tag types are present.

### `power_flow_target_tag_match_mode_component_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component tags are present.

### `power_flow_target_tag_match_mode_entity_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity tags are present.

### `power_flow_target_tag_match_mode_entity_id_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity IDs are present.

### `power_flow_target_tag_match_mode_component_id_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component IDs are present.

### `power_flow_target_tag_match_mode_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How general tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tags are present.

### `power_flow_target_tag_match_mode_tag_type_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How the type of tag being matched should be handled.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tag types are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tag types are present.

### `power_flow_target_tag_match_mode_component_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component tags are present.

### `power_flow_target_tag_match_mode_entity_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity tags are present.

### `power_flow_target_tag_match_mode_entity_id_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity IDs are present.

### `power_flow_target_tag_match_mode_component_id_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component IDs are present.

### `power_flow_target_tag_match_mode_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How general tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tags are present.

### `power_flow_target_tag_match_mode_tag_type_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How the type of tag being matched should be handled.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tag types are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tag types are present.

### `power_flow_target_tag_match_mode_component_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component tags are present.

### `power_flow_target_tag_match_mode_entity_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity tags are present.

### `power_flow_target_tag_match_mode_entity_id_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity IDs are present.

### `power_flow_target_tag_match_mode_component_id_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component IDs are present.

### `power_flow_target_tag_match_mode_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How general tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tags are present.

### `power_flow_target_tag_match_mode_tag_type_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How the type of tag being matched should be handled.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tag types are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tag types are present.

### `power_flow_target_tag_match_mode_component_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component tags are present.

### `power_flow_target_tag_match_mode_entity_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity tags are present.

### `power_flow_target_tag_match_mode_entity_id_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity IDs are present.

### `power_flow_target_tag_match_mode_component_id_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component IDs are present.

### `power_flow_target_tag_match_mode_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How general tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tags are present.

### `power_flow_target_tag_match_mode_tag_type_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How the type of tag being matched should be handled.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tag types are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tag types are present.

### `power_flow_target_tag_match_mode_component_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component tags are present.

### `power_flow_target_tag_match_mode_entity_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity tags are present.

### `power_flow_target_tag_match_mode_entity_id_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity IDs are present.

### `power_flow_target_tag_match_mode_component_id_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component IDs are present.

### `power_flow_target_tag_match_mode_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How general tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tags are present.

### `power_flow_target_tag_match_mode_tag_type_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How the type of tag being matched should be handled.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tag types are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tag types are present.

### `power_flow_target_tag_match_mode_component_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component tags are present.

### `power_flow_target_tag_match_mode_entity_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity tags are present.

### `power_flow_target_tag_match_mode_entity_id_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity IDs are present.

### `power_flow_target_tag_match_mode_component_id_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component IDs are present.

### `power_flow_target_tag_match_mode_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How general tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tags are present.

### `power_flow_target_tag_match_mode_tag_type_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How the type of tag being matched should be handled.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tag types are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tag types are present.

### `power_flow_target_tag_match_mode_component_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component tags are present.

### `power_flow_target_tag_match_mode_entity_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity tags are present.

### `power_flow_target_tag_match_mode_entity_id_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity IDs are present.

### `power_flow_target_tag_match_mode_component_id_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component IDs are present.

### `power_flow_target_tag_match_mode_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How general tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tags are present.

### `power_flow_target_tag_match_mode_tag_type_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How the type of tag being matched should be handled.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tag types are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tag types are present.

### `power_flow_target_tag_match_mode_component_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component tags are present.

### `power_flow_target_tag_match_mode_entity_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity tags are present.

### `power_flow_target_tag_match_mode_entity_id_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity IDs are present.

### `power_flow_target_tag_match_mode_component_id_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component IDs are present.

### `power_flow_target_tag_match_mode_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How general tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tags are present.

### `power_flow_target_tag_match_mode_tag_type_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How the type of tag being matched should be handled.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tag types are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tag types are present.

### `power_flow_target_tag_match_mode_component_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component tags are present.

### `power_flow_target_tag_match_mode_entity_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity tags are present.

### `power_flow_target_tag_match_mode_entity_id_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity IDs are present.

### `power_flow_target_tag_match_mode_component_id_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component IDs are present.

### `power_flow_target_tag_match_mode_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How general tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tags are present.

### `power_flow_target_tag_match_mode_tag_type_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How the type of tag being matched should be handled.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tag types are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tag types are present.

### `power_flow_target_tag_match_mode_component_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component tags are present.

### `power_flow_target_tag_match_mode_entity_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity tags are present.

### `power_flow_target_tag_match_mode_entity_id_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity IDs are present.

### `power_flow_target_tag_match_mode_component_id_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component IDs are present.

### `power_flow_target_tag_match_mode_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How general tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tags are present.

### `power_flow_target_tag_match_mode_tag_type_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How the type of tag being matched should be handled.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tag types are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tag types are present.

### `power_flow_target_tag_match_mode_component_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component tags are present.

### `power_flow_target_tag_match_mode_entity_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity tags are present.

### `power_flow_target_tag_match_mode_entity_id_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity IDs are present.

### `power_flow_target_tag_match_mode_component_id_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component IDs are present.

### `power_flow_target_tag_match_mode_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How general tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tags are present.

### `power_flow_target_tag_match_mode_tag_type_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How the type of tag being matched should be handled.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tag types are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tag types are present.

### `power_flow_target_tag_match_mode_component_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component tags are present.

### `power_flow_target_tag_match_mode_entity_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity tags are present.

### `power_flow_target_tag_match_mode_entity_id_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity IDs are present.

### `power_flow_target_tag_match_mode_component_id_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component IDs are present.

### `power_flow_target_tag_match_mode_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How general tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tags are present.

### `power_flow_target_tag_match_mode_tag_type_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How the type of tag being matched should be handled.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tag types are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tag types are present.

### `power_flow_target_tag_match_mode_component_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component tags are present.

### `power_flow_target_tag_match_mode_entity_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity tags are present.

### `power_flow_target_tag_match_mode_entity_id_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity IDs are present.

### `power_flow_target_tag_match_mode_component_id_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component IDs are present.

### `power_flow_target_tag_match_mode_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How general tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tags are present.

### `power_flow_target_tag_match_mode_tag_type_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How the type of tag being matched should be handled.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tag types are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tag types are present.

### `power_flow_target_tag_match_mode_component_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component tags are present.

### `power_flow_target_tag_match_mode_entity_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity tags are present.

### `power_flow_target_tag_match_mode_entity_id_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity IDs are present.

### `power_flow_target_tag_match_mode_component_id_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component IDs are present.

### `power_flow_target_tag_match_mode_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How general tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tags are present.

### `power_flow_target_tag_match_mode_tag_type_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How the type of tag being matched should be handled.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tag types are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tag types are present.

### `power_flow_target_tag_match_mode_component_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component tags are present.

### `power_flow_target_tag_match_mode_entity_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity tags are present.

### `power_flow_target_tag_match_mode_entity_id_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity IDs are present.

### `power_flow_target_tag_match_mode_component_id_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component IDs are present.

### `power_flow_target_tag_match_mode_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How general tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tags are present.

### `power_flow_target_tag_match_mode_tag_type_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How the type of tag being matched should be handled.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tag types are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tag types are present.

### `power_flow_target_tag_match_mode_component_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component tags are present.

### `power_flow_target_tag_match_mode_entity_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity tags are present.

### `power_flow_target_tag_match_mode_entity_id_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity IDs are present.

### `power_flow_target_tag_match_mode_component_id_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component IDs are present.

### `power_flow_target_tag_match_mode_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How general tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tags are present.

### `power_flow_target_tag_match_mode_tag_type_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How the type of tag being matched should be handled.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tag types are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tag types are present.

### `power_flow_target_tag_match_mode_component_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component tags are present.

### `power_flow_target_tag_match_mode_entity_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity tags are present.

### `power_flow_target_tag_match_mode_entity_id_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity IDs are present.

### `power_flow_target_tag_match_mode_component_id_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component IDs are present.

### `power_flow_target_tag_match_mode_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How general tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tags are present.

### `power_flow_target_tag_match_mode_tag_type_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How the type of tag being matched should be handled.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tag types are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tag types are present.

### `power_flow_target_tag_match_mode_component_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component tags are present.

### `power_flow_target_tag_match_mode_entity_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity tags are present.

### `power_flow_target_tag_match_mode_entity_id_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity IDs are present.

### `power_flow_target_tag_match_mode_component_id_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component IDs are present.

### `power_flow_target_tag_match_mode_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How general tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tags are present.

### `power_flow_target_tag_match_mode_tag_type_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How the type of tag being matched should be handled.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tag types are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tag types are present.

### `power_flow_target_tag_match_mode_component_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component tags are present.

### `power_flow_target_tag_match_mode_entity_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity tags are present.

### `power_flow_target_tag_match_mode_entity_id_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity IDs are present.

### `power_flow_target_tag_match_mode_component_id_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component IDs are present.

### `power_flow_target_tag_match_mode_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How general tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tags are present.

### `power_flow_target_tag_match_mode_tag_type_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How the type of tag being matched should be handled.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tag types are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tag types are present.

### `power_flow_target_tag_match_mode_component_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component tags are present.

### `power_flow_target_tag_match_mode_entity_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity tags are present.

### `power_flow_target_tag_match_mode_entity_id_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity IDs are present.

### `power_flow_target_tag_match_mode_component_id_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component IDs are present.

### `power_flow_target_tag_match_mode_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How general tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tags are present.

### `power_flow_target_tag_match_mode_tag_type_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How the type of tag being matched should be handled.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tag types are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tag types are present.

### `power_flow_target_tag_match_mode_component_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component tags are present.

### `power_flow_target_tag_match_mode_entity_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity tags are present.

### `power_flow_target_tag_match_mode_entity_id_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity IDs are present.

### `power_flow_target_tag_match_mode_component_id_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component IDs are present.

### `power_flow_target_tag_match_mode_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How general tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tags are present.

### `power_flow_target_tag_match_mode_tag_type_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How the type of tag being matched should be handled.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tag types are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tag types are present.

### `power_flow_target_tag_match_mode_component_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component tags are present.

### `power_flow_target_tag_match_mode_entity_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity tags are present.

### `power_flow_target_tag_match_mode_entity_id_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How entity IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target entity IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target entity IDs are present.

### `power_flow_target_tag_match_mode_component_id_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component IDs should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component IDs are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component IDs are present.

### `power_flow_target_tag_match_mode_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How general tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tags are present.

### `power_flow_target_tag_match_mode_tag_type_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How the type of tag being matched should be handled.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target tag types are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target tag types are present.

### `power_flow_target_tag_match_mode_component_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag_tag`

*   **Type:** `enum`
*   **Description:** How component tags should be matched.
*   **Possible Values:**
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ANY`: Matches if any of the target component tags are present.
    *   `POWER_FLOW_TARGET_TAG_MATCH_MODE_ALL`: Matches only if all of the target component tags are present.

### `power_flow_target_tag_match_mode_entity_tag_tag_tag_tag_tag_tag_tag_tag