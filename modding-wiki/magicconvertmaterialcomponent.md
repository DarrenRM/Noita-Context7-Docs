---
title: MagicConvertMaterialComponent
source: https://noita.wiki.gg/wiki/Documentation:MagicConvertMaterialComponent
category: modding-wiki
---

# MagicConvertMaterialComponent

This documentation page details the `MagicConvertMaterialComponent` in Noita, a crucial component for modders looking to implement magical effects that transform one material into another. Understanding this component allows for the creation of dynamic and interactive spells that alter the game world's physical properties.

## Overview

The `MagicConvertMaterialComponent` is attached to magical entities (like projectiles or spell effects) and dictates their ability to convert one type of material into another upon impact or interaction. This is fundamental for creating spells that can, for example, turn water into lava, ice into stone, or even more exotic transformations.

## Component Properties

The `MagicConvertMaterialComponent` has several properties that can be configured within an entity's XML definition to control its behavior.

### `target_material`

*   **Type:** String
*   **Description:** The material that the entity will attempt to convert *to*. This should be a valid material ID.

### `convert_probability`

*   **Type:** Float
*   **Description:** A value between 0.0 and 1.0 representing the chance that the conversion will occur. A value of 1.0 means the conversion is guaranteed.

### `radius`

*   **Type:** Float
*   **Description:** The radius around the point of impact or entity's origin within which the material conversion will take place.

### `material_to_convert`

*   **Type:** String
*   **Description:** The specific material ID that this component will target for conversion. If this is left empty or not specified, the component will attempt to convert *any* material it hits within the radius.

### `convert_only_on_hit`

*   **Type:** Boolean
*   **Description:** If `true`, the conversion will only happen when the entity hits a solid surface. If `false`, it can convert materials in the air or water.

### `convert_only_on_damage`

*   **Type:** Boolean
*   **Description:** If `true`, the conversion will only occur if the entity deals damage to the target.

### `convert_only_on_death`

*   **Type:** Boolean
*   **Description:** If `true`, the conversion will only occur if the entity kills the target.

### `convert_only_on_explosion`

*   **Type:** Boolean
*   **Description:** If `true`, the conversion will only occur if the entity causes an explosion.

### `convert_only_on_material`

*   **Type:** String
*   **Description:** A specific material ID. If set, conversion will only happen if the entity hits or interacts with this particular material.

### `convert_only_on_material_tag`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will only happen if the entity hits or interacts with a material that has this tag.

### `convert_only_on_material_tag_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will *not* happen if the entity hits or interacts with a material that has this tag.

### `convert_only_on_material_tag_and`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will only happen if the entity hits or interacts with a material that has this tag *and* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_or`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *or* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_xor`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *xor* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_nand`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *nand* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_nor`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *nor* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_xnor`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *xnor* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_and`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_and* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_and`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_and* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_or`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_or* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_or`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_or* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_xor`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_xor* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_xor`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_xor* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_nand`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_nand* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_nand`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_nand* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_nor`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_nor* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_nor`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_nor* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_xnor`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_xnor* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_xnor`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_xnor* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_nimpl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_nimpl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_nimpl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_nimpl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_nimpl_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_nimpl_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_impl_reverse_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_impl_reverse_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_nimpl_reverse_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_nimpl_reverse_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_nimpl_reverse_nimpl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_nimpl_reverse_nimpl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_impl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_impl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_nimpl_reverse_nimpl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_nimpl_reverse_nimpl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_impl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_impl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_impl_reverse_nimpl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_impl_reverse_nimpl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_impl_reverse_nimpl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_impl_reverse_nimpl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_impl_reverse_nimpl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_impl_reverse_nimpl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_impl_reverse_nimpl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_impl_reverse_nimpl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_impl_reverse_nimpl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_impl_reverse_nimpl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_impl_reverse_nimpl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_impl_reverse_nimpl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_impl_reverse_nimpl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_impl_reverse_nimpl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_impl_reverse_nimpl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_impl_reverse_nimpl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_impl_reverse_nimpl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_impl_reverse_nimpl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_impl_reverse_nimpl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_impl_reverse_nimpl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_impl_reverse_nimpl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_impl_reverse_nimpl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_impl_reverse_nimpl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_impl_reverse_nimpl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_impl_reverse_nimpl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_impl_reverse_nimpl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_impl_reverse_nimpl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_impl_reverse_nimpl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_impl_reverse_nimpl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_impl_reverse_nimpl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_nimpl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_nimpl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_nimpl_reverse_impl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_reverse_nimpl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_impl_reverse_nimpl_reverse_impl_not`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_impl_reverse_nimpl_reverse_impl_not* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl`

*   **Type:** String
*   **Description:** A material tag. If set, conversion will happen if the entity hits or interacts with a material that has this tag *reverse_nimpl_reverse_impl_reverse_nimpl_reverse_nimpl_impl* the `convert_only_on_material_tag` (if specified).

### `convert_only_on_material_tag_reverse_impl_reverse_nimpl_reverse_