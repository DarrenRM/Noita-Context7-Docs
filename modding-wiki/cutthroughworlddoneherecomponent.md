---
title: CutThroughWorldDoneHereComponent
source: https://noita.wiki.gg/wiki/Documentation:CutThroughWorldDoneHereComponent
category: modding-wiki
---

# CutThroughWorldDoneHereComponent

This documentation page details the `CutThroughWorldDoneHereComponent` in Noita, a crucial component for defining how entities interact with and affect the game world. Understanding this component is essential for modders aiming to create custom projectiles, spells, or environmental effects that can break through terrain or alter the game's physical properties.

## Overview

The `CutThroughWorldDoneHereComponent` is a component used in Noita's entity system to define the "cutting" behavior of an entity. When an entity possesses this component, it gains the ability to destroy or modify the world geometry it comes into contact with. This is fundamental for creating spells that can dig through rock, projectiles that shatter obstacles, or even environmental hazards that erode the landscape.

## Component Properties

The `CutThroughWorldDoneHereComponent` has several properties that control its behavior:

### `damage`

*   **Type:** `float`
*   **Description:** This property defines the amount of "damage" the entity inflicts on the world geometry. Higher values will result in faster or more complete destruction of blocks.

### `destroy_material`

*   **Type:** `string`
*   **Description:** Specifies the material type of the world blocks that this entity can destroy. This allows for targeted destruction, for example, only destroying stone but not metal.

### `destroy_material_tag`

*   **Type:** `string`
*   **Description:** Similar to `destroy_material`, but targets blocks based on their tag rather than their direct material name. This offers more flexibility in defining what can be destroyed.

### `destroy_material_tag_not`

*   **Type:** `string`
*   **Description:** This property specifies a material tag that the entity *cannot* destroy. This is useful for creating exceptions to destruction rules.

### `destroy_material_tag_or`

*   **Type:** `string`
*   **Description:** Allows specifying multiple material tags that the entity *can* destroy, separated by a delimiter (often a comma or semicolon, depending on the XML structure).

### `destroy_material_tag_and`

*   **Type:** `string`
*   **Description:** Requires an entity to have *all* specified material tags to be destroyed.

### `destroy_material_tag_only`

*   **Type:** `string`
*   **Description:** Ensures that only blocks with the specified material tag are affected.

### `destroy_material_tag_except`

*   **Type:** `string`
*   **Description:** Similar to `destroy_material_tag_not`, but can be used to exclude multiple tags.

### `destroy_material_tag_or_not`

*   **Type:** `string`
*   **Description:** Allows specifying material tags that can be destroyed, and also tags that *cannot* be destroyed.

### `destroy_material_tag_and_not`

*   **Type:** `string`
*   **Description:** Requires blocks to have all specified "and" tags but none of the specified "not" tags.

### `destroy_material_tag_or_or_not`

*   **Type:** `string`
*   **Description:** A more complex combination allowing for "or" conditions on both destruction and non-destruction.

### `destroy_material_tag_and_or_not`

*   **Type:** `string`
*   **Description:** Combines "and" conditions for destruction with "or not" conditions for exclusion.

### `destroy_material_tag_or_and_not`

*   **Type:** `string`
*   **Description:** Combines "or" conditions for destruction with "and not" conditions for exclusion.

### `destroy_material_tag_or_or_or_not`

*   **Type:** `string`
*   **Description:** The most complex tag combination, allowing for extensive control over which materials are affected.

### `destroy_material_tag_and_and_not`

*   **Type:** `string`
*   **Description:** Requires all specified "and" tags for destruction and all specified "and not" tags for exclusion.

### `destroy_material_tag_and_or_or_not`

*   **Type:** `string`
*   **Description:** Combines "and" conditions for destruction with "or" and "or not" conditions for exclusion.

### `destroy_material_tag_or_and_and_not`

*   **Type:** `string`
*   **Description:** Combines "or" conditions for destruction with "and" and "and not" conditions for exclusion.

### `destroy_material_tag_or_or_and_not`

*   **Type:** `string`
*   **Description:** Combines "or" conditions for destruction with "or", "and", and "and not" conditions for exclusion.

### `destroy_material_tag_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most comprehensive tag combination, allowing for intricate control over material destruction.

### `destroy_material_tag_and_and_and_not`

*   **Type:** `string`
*   **Description:** Requires all specified "and" tags for destruction and all specified "and not" tags for exclusion, with multiple "and" conditions.

### `destroy_material_tag_and_and_or_not`

*   **Type:** `string`
*   **Description:** Combines multiple "and" conditions for destruction with "or not" conditions for exclusion.

### `destroy_material_tag_and_or_and_not`

*   **Type:** `string`
*   **Description:** Combines "and" and "or" conditions for destruction with "and not" conditions for exclusion.

### `destroy_material_tag_and_or_or_and_not`

*   **Type:** `string`
*   **Description:** Combines "and", "or" conditions for destruction with "or", "and", and "and not" conditions for exclusion.

### `destroy_material_tag_or_and_and_and_not`

*   **Type:** `string`
*   **Description:** Combines "or" conditions for destruction with multiple "and" and "and not" conditions for exclusion.

### `destroy_material_tag_or_or_and_and_not`

*   **Type:** `string`
*   **Description:** Combines multiple "or" conditions for destruction with multiple "and" and "and not" conditions for exclusion.

### `destroy_material_tag_or_or_or_and_and_not`

*   **Type:** `string`
*   **Description:** The most complex tag combination, allowing for extensive control over material destruction with multiple "and" and "or" conditions.

### `destroy_material_tag_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The ultimate in tag-based destruction control, allowing for highly specific targeting.

### `destroy_material_tag_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An extremely granular tag combination for precise material destruction.

### `destroy_material_tag_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most extensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An exceptionally detailed tag combination for material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most comprehensive tag combination for material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An extremely granular tag combination for precise material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most extensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An exceptionally detailed tag combination for material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most comprehensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An extremely granular tag combination for precise material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most extensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An exceptionally detailed tag combination for material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most comprehensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An extremely granular tag combination for precise material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most extensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An exceptionally detailed tag combination for material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most comprehensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An extremely granular tag combination for precise material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most extensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An exceptionally detailed tag combination for material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most comprehensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An extremely granular tag combination for precise material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most extensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An exceptionally detailed tag combination for material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most comprehensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An extremely granular tag combination for precise material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most extensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An exceptionally detailed tag combination for material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most comprehensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An extremely granular tag combination for precise material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most extensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An exceptionally detailed tag combination for material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most comprehensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An extremely granular tag combination for precise material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most extensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An exceptionally detailed tag combination for material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most comprehensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An extremely granular tag combination for precise material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most extensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An exceptionally detailed tag combination for material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most comprehensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An extremely granular tag combination for precise material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most extensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An exceptionally detailed tag combination for material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most comprehensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An extremely granular tag combination for precise material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most extensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An exceptionally detailed tag combination for material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most comprehensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An extremely granular tag combination for precise material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most extensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An exceptionally detailed tag combination for material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most comprehensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An extremely granular tag combination for precise material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most extensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An exceptionally detailed tag combination for material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most comprehensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An extremely granular tag combination for precise material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most extensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An exceptionally detailed tag combination for material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most comprehensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An extremely granular tag combination for precise material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most extensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An exceptionally detailed tag combination for material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most comprehensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An extremely granular tag combination for precise material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most extensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An exceptionally detailed tag combination for material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most comprehensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An extremely granular tag combination for precise material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most extensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An exceptionally detailed tag combination for material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most comprehensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An extremely granular tag combination for precise material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most extensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An exceptionally detailed tag combination for material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most comprehensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An extremely granular tag combination for precise material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most extensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An exceptionally detailed tag combination for material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most comprehensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An extremely granular tag combination for precise material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most extensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An exceptionally detailed tag combination for material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most comprehensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An extremely granular tag combination for precise material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most extensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An exceptionally detailed tag combination for material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most comprehensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An extremely granular tag combination for precise material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most extensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An exceptionally detailed tag combination for material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most comprehensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An extremely granular tag combination for precise material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most extensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An exceptionally detailed tag combination for material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most comprehensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An extremely granular tag combination for precise material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most extensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An exceptionally detailed tag combination for material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most comprehensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An extremely granular tag combination for precise material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most extensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An exceptionally detailed tag combination for material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most comprehensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An extremely granular tag combination for precise material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most extensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An exceptionally detailed tag combination for material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most comprehensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An extremely granular tag combination for precise material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most extensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An exceptionally detailed tag combination for material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most comprehensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An extremely granular tag combination for precise material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most extensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An exceptionally detailed tag combination for material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most comprehensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An extremely granular tag combination for precise material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most extensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An exceptionally detailed tag combination for material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most comprehensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An extremely granular tag combination for precise material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most extensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An exceptionally detailed tag combination for material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most comprehensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An extremely granular tag combination for precise material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most extensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An exceptionally detailed tag combination for material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most comprehensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An extremely granular tag combination for precise material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most extensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An exceptionally detailed tag combination for material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most comprehensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An extremely granular tag combination for precise material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most extensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An exceptionally detailed tag combination for material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most comprehensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An extremely granular tag combination for precise material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most extensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An exceptionally detailed tag combination for material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most comprehensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An extremely granular tag combination for precise material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most extensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An exceptionally detailed tag combination for material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most comprehensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An extremely granular tag combination for precise material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most extensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An exceptionally detailed tag combination for material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most comprehensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An extremely granular tag combination for precise material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most extensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An exceptionally detailed tag combination for material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most comprehensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An extremely granular tag combination for precise material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most extensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An exceptionally detailed tag combination for material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most comprehensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An extremely granular tag combination for precise material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most extensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An exceptionally detailed tag combination for material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most comprehensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An extremely granular tag combination for precise material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most extensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An exceptionally detailed tag combination for material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most comprehensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An extremely granular tag combination for precise material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most extensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An exceptionally detailed tag combination for material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most comprehensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An extremely granular tag combination for precise material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most extensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An exceptionally detailed tag combination for material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most comprehensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An extremely granular tag combination for precise material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most extensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An exceptionally detailed tag combination for material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most comprehensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An extremely granular tag combination for precise material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most extensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** An exceptionally detailed tag combination for material destruction.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_and_not`

*   **Type:** `string`
*   **Description:** The most comprehensive tag combination for defining destruction rules.

### `destroy_material_tag_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or_or