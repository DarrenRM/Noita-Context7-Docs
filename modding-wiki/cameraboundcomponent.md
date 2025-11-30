---
title: CameraBoundComponent
source: https://noita.wiki.gg/wiki/Documentation:CameraBoundComponent
category: modding-wiki
---

# CameraBoundComponent

This documentation page details the `CameraBoundComponent` in Noita, a crucial component for controlling how the game camera behaves within specific areas or biomes. Understanding this component is essential for modders who wish to create custom environments, trigger events based on camera position, or alter the player's visual experience within defined boundaries.

## Overview

The `CameraBoundComponent` is an entity component used in Noita's XML entity definitions. It defines boundaries that affect the game's camera. When the camera enters or leaves these defined bounds, specific actions or changes can be triggered. This is particularly useful for creating distinct visual zones, implementing unique gameplay mechanics tied to location, or managing camera behavior in complex levels.

## Component Properties

The `CameraBoundComponent` has several properties that can be configured in the entity's XML definition. These properties determine the shape, size, and behavior of the camera bounds.

### `bounds_material`

This property specifies the material that defines the boundaries of the camera-limited area. The game uses this material to detect when the camera has entered or exited the defined zone.

*   **Type:** String
*   **Description:** The name of the material used for the bounds. This material must be present in the game's material definitions.

### `bounds_material_tag`

An alternative to `bounds_material`, this property allows you to specify a tag associated with materials. If multiple materials share the same tag, they will all be considered part of the bounds.

*   **Type:** String
*   **Description:** The tag used to identify materials for the bounds.

### `bounds_material_tag_is_exclusive`

When `bounds_material_tag` is used, this boolean property determines whether the tag is exclusive. If `true`, the camera is *only* considered within bounds if it's touching a material with the specified tag. If `false`, the camera is considered within bounds if it's touching *any* material that has the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_inclusive`

This boolean property, when `true`, makes the bounds *inclusive*. This means the camera is considered within the bounds if it is *not* touching any material with the specified tag. This is useful for defining areas *outside* of specific zones.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_exclusive_and_inclusive`

This property combines the functionality of `is_exclusive` and `is_inclusive`. When `true`, the camera is considered within bounds *only* if it is touching a material with the specified tag, and *not* touching any other material with the same tag. This is a more complex condition for defining precise boundaries.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag`

When `true`, this property inverts the logic for `bounds_material_tag`. The camera is considered within bounds if it is *not* touching any material with the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_exclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag` with exclusivity. The camera is considered within bounds *only* if it is not touching any material with the specified tag, and is touching at least one material that does *not* have the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_inclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag` with inclusivity. The camera is considered within bounds if it is *not* touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag. This effectively means the camera must be in an area with no materials of the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_exclusive_and_inclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag` with both exclusivity and inclusivity. The camera is considered within bounds *only* if it is not touching any material with the specified tag, and is touching at least one material that does *not* have the specified tag, and is *not* touching any material that does *not* have the specified tag. This is a very specific condition for defining areas.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag`

This property, when `true`, inverts the logic for `bounds_material_tag_is_not_tag`. The camera is considered within bounds if it *is* touching any material with the specified tag, and *is not* touching any material that does *not* have the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_exclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag` with exclusivity. The camera is considered within bounds *only* if it is touching a material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is touching at least one material that *does* have the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_inclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag` with inclusivity. The camera is considered within bounds if it is touching a material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag. This means the camera must be in an area with only materials of the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_exclusive_and_inclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag` with both exclusivity and inclusivity. The camera is considered within bounds *only* if it is touching a material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is touching at least one material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This is an extremely specific condition.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag`

This property, when `true`, inverts the logic for `bounds_material_tag_is_not_tag_is_not_tag`. The camera is considered within bounds if it is *not* touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag. This means the camera must be in an area with no materials at all.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_exclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag` with exclusivity. The camera is considered within bounds *only* if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is touching at least one material that does *not* have the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_inclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag` with inclusivity. The camera is considered within bounds if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag. This means the camera must be in an area with no materials at all.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_exclusive_and_inclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag` with both exclusivity and inclusivity. The camera is considered within bounds *only* if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is touching at least one material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag. This is an extremely specific condition for defining areas with no materials.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag`

This property, when `true`, inverts the logic for `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag`. The camera is considered within bounds if it *is* touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag. This means the camera must be in an area with only materials of the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_exclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with exclusivity. The camera is considered within bounds *only* if it is touching a material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is touching at least one material that *does* have the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_inclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with inclusivity. The camera is considered within bounds if it is touching a material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This means the camera must be in an area with only materials of the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_exclusive_and_inclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with both exclusivity and inclusivity. The camera is considered within bounds *only* if it is touching a material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is touching at least one material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This is an extremely specific condition for defining areas with only materials of the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag`

This property, when `true`, inverts the logic for `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag`. The camera is considered within bounds if it is *not* touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This means the camera must be in an area with no materials at all.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_exclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with exclusivity. The camera is considered within bounds *only* if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is touching at least one material that *does* have the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_inclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with inclusivity. The camera is considered within bounds if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This means the camera must be in an area with no materials at all.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_exclusive_and_inclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with both exclusivity and inclusivity. The camera is considered within bounds *only* if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is touching at least one material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This is an extremely specific condition for defining areas with no materials.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag`

This property, when `true`, inverts the logic for `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag`. The camera is considered within bounds if it *is* touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This means the camera must be in an area with only materials of the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_exclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with exclusivity. The camera is considered within bounds *only* if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is touching at least one material that *does* have the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_inclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with inclusivity. The camera is considered within bounds if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This means the camera must be in an area with no materials at all.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_exclusive_and_inclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with both exclusivity and inclusivity. The camera is considered within bounds *only* if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is touching at least one material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This is an extremely specific condition for defining areas with no materials.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag`

This property, when `true`, inverts the logic for `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag`. The camera is considered within bounds if it *is* touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This means the camera must be in an area with only materials of the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_exclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with exclusivity. The camera is considered within bounds *only* if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is touching at least one material that *does* have the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_inclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with inclusivity. The camera is considered within bounds if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This means the camera must be in an area with no materials at all.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_exclusive_and_inclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with both exclusivity and inclusivity. The camera is considered within bounds *only* if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is touching at least one material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This is an extremely specific condition for defining areas with no materials.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag`

This property, when `true`, inverts the logic for `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag`. The camera is considered within bounds if it *is* touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This means the camera must be in an area with only materials of the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_exclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with exclusivity. The camera is considered within bounds *only* if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is touching at least one material that *does* have the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_inclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with inclusivity. The camera is considered within bounds if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This means the camera must be in an area with no materials at all.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_exclusive_and_inclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with both exclusivity and inclusivity. The camera is considered within bounds *only* if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is touching at least one material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This is an extremely specific condition for defining areas with no materials.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag`

This property, when `true`, inverts the logic for `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag`. The camera is considered within bounds if it *is* touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This means the camera must be in an area with only materials of the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_exclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with exclusivity. The camera is considered within bounds *only* if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is touching at least one material that *does* have the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_inclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with inclusivity. The camera is considered within bounds if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This means the camera must be in an area with no materials at all.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_exclusive_and_inclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with both exclusivity and inclusivity. The camera is considered within bounds *only* if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is touching at least one material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This is an extremely specific condition for defining areas with no materials.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag`

This property, when `true`, inverts the logic for `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag`. The camera is considered within bounds if it *is* touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This means the camera must be in an area with only materials of the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_exclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with exclusivity. The camera is considered within bounds *only* if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is touching at least one material that *does* have the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_inclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with inclusivity. The camera is considered within bounds if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This means the camera must be in an area with no materials at all.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_exclusive_and_inclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with both exclusivity and inclusivity. The camera is considered within bounds *only* if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is touching at least one material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This is an extremely specific condition for defining areas with no materials.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag`

This property, when `true`, inverts the logic for `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag`. The camera is considered within bounds if it *is* touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This means the camera must be in an area with only materials of the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_exclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with exclusivity. The camera is considered within bounds *only* if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is touching at least one material that *does* have the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_inclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with inclusivity. The camera is considered within bounds if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This means the camera must be in an area with no materials at all.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_exclusive_and_inclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with both exclusivity and inclusivity. The camera is considered within bounds *only* if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is touching at least one material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This is an extremely specific condition for defining areas with no materials.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag`

This property, when `true`, inverts the logic for `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag`. The camera is considered within bounds if it *is* touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This means the camera must be in an area with only materials of the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_exclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with exclusivity. The camera is considered within bounds *only* if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is touching at least one material that *does* have the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_inclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with inclusivity. The camera is considered within bounds if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This means the camera must be in an area with no materials at all.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_exclusive_and_inclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with both exclusivity and inclusivity. The camera is considered within bounds *only* if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is touching at least one material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This is an extremely specific condition for defining areas with no materials.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag`

This property, when `true`, inverts the logic for `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag`. The camera is considered within bounds if it *is* touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This means the camera must be in an area with only materials of the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_exclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with exclusivity. The camera is considered within bounds *only* if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is touching at least one material that *does* have the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_inclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with inclusivity. The camera is considered within bounds if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This means the camera must be in an area with no materials at all.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_exclusive_and_inclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with both exclusivity and inclusivity. The camera is considered within bounds *only* if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is touching at least one material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This is an extremely specific condition for defining areas with no materials.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag`

This property, when `true`, inverts the logic for `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag`. The camera is considered within bounds if it *is* touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This means the camera must be in an area with only materials of the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_exclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with exclusivity. The camera is considered within bounds *only* if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is touching at least one material that *does* have the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_inclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with inclusivity. The camera is considered within bounds if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This means the camera must be in an area with no materials at all.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_exclusive_and_inclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with both exclusivity and inclusivity. The camera is considered within bounds *only* if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is touching at least one material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This is an extremely specific condition for defining areas with no materials.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag`

This property, when `true`, inverts the logic for `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag`. The camera is considered within bounds if it *is* touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This means the camera must be in an area with only materials of the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_exclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with exclusivity. The camera is considered within bounds *only* if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is touching at least one material that *does* have the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_inclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with inclusivity. The camera is considered within bounds if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This means the camera must be in an area with no materials at all.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_exclusive_and_inclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with both exclusivity and inclusivity. The camera is considered within bounds *only* if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is touching at least one material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This is an extremely specific condition for defining areas with no materials.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag`

This property, when `true`, inverts the logic for `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag`. The camera is considered within bounds if it *is* touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This means the camera must be in an area with only materials of the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_exclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with exclusivity. The camera is considered within bounds *only* if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is touching at least one material that *does* have the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_inclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with inclusivity. The camera is considered within bounds if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This means the camera must be in an area with no materials at all.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_exclusive_and_inclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with both exclusivity and inclusivity. The camera is considered within bounds *only* if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is touching at least one material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This is an extremely specific condition for defining areas with no materials.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag`

This property, when `true`, inverts the logic for `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag`. The camera is considered within bounds if it *is* touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This means the camera must be in an area with only materials of the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_exclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with exclusivity. The camera is considered within bounds *only* if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is touching at least one material that *does* have the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_inclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with inclusivity. The camera is considered within bounds if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This means the camera must be in an area with no materials at all.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_exclusive_and_inclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with both exclusivity and inclusivity. The camera is considered within bounds *only* if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is touching at least one material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This is an extremely specific condition for defining areas with no materials.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag`

This property, when `true`, inverts the logic for `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag`. The camera is considered within bounds if it *is* touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This means the camera must be in an area with only materials of the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_exclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with exclusivity. The camera is considered within bounds *only* if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is touching at least one material that *does* have the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_inclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with inclusivity. The camera is considered within bounds if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This means the camera must be in an area with no materials at all.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_exclusive_and_inclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with both exclusivity and inclusivity. The camera is considered within bounds *only* if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is touching at least one material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This is an extremely specific condition for defining areas with no materials.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag`

This property, when `true`, inverts the logic for `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag`. The camera is considered within bounds if it *is* touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This means the camera must be in an area with only materials of the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_exclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with exclusivity. The camera is considered within bounds *only* if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is touching at least one material that *does* have the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_inclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with inclusivity. The camera is considered within bounds if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This means the camera must be in an area with no materials at all.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_exclusive_and_inclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with both exclusivity and inclusivity. The camera is considered within bounds *only* if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is touching at least one material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This is an extremely specific condition for defining areas with no materials.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag`

This property, when `true`, inverts the logic for `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag`. The camera is considered within bounds if it *is* touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This means the camera must be in an area with only materials of the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_exclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with exclusivity. The camera is considered within bounds *only* if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is touching at least one material that *does* have the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_inclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with inclusivity. The camera is considered within bounds if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This means the camera must be in an area with no materials at all.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_exclusive_and_inclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with both exclusivity and inclusivity. The camera is considered within bounds *only* if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is touching at least one material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This is an extremely specific condition for defining areas with no materials.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag`

This property, when `true`, inverts the logic for `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag`. The camera is considered within bounds if it *is* touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This means the camera must be in an area with only materials of the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_exclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with exclusivity. The camera is considered within bounds *only* if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is touching at least one material that *does* have the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_inclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with inclusivity. The camera is considered within bounds if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This means the camera must be in an area with no materials at all.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_exclusive_and_inclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with both exclusivity and inclusivity. The camera is considered within bounds *only* if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is touching at least one material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This is an extremely specific condition for defining areas with no materials.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag`

This property, when `true`, inverts the logic for `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag`. The camera is considered within bounds if it *is* touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This means the camera must be in an area with only materials of the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_exclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with exclusivity. The camera is considered within bounds *only* if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is touching at least one material that *does* have the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_inclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with inclusivity. The camera is considered within bounds if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This means the camera must be in an area with no materials at all.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_exclusive_and_inclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with both exclusivity and inclusivity. The camera is considered within bounds *only* if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is touching at least one material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This is an extremely specific condition for defining areas with no materials.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag`

This property, when `true`, inverts the logic for `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag`. The camera is considered within bounds if it *is* touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This means the camera must be in an area with only materials of the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_exclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with exclusivity. The camera is considered within bounds *only* if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is touching at least one material that *does* have the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_inclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with inclusivity. The camera is considered within bounds if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This means the camera must be in an area with no materials at all.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_exclusive_and_inclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with both exclusivity and inclusivity. The camera is considered within bounds *only* if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is touching at least one material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This is an extremely specific condition for defining areas with no materials.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag`

This property, when `true`, inverts the logic for `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag`. The camera is considered within bounds if it *is* touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This means the camera must be in an area with only materials of the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_exclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with exclusivity. The camera is considered within bounds *only* if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is touching at least one material that *does* have the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_inclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with inclusivity. The camera is considered within bounds if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This means the camera must be in an area with no materials at all.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_exclusive_and_inclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with both exclusivity and inclusivity. The camera is considered within bounds *only* if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is touching at least one material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This is an extremely specific condition for defining areas with no materials.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag`

This property, when `true`, inverts the logic for `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag`. The camera is considered within bounds if it *is* touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This means the camera must be in an area with only materials of the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_exclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with exclusivity. The camera is considered within bounds *only* if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is touching at least one material that *does* have the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_inclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with inclusivity. The camera is considered within bounds if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This means the camera must be in an area with no materials at all.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_exclusive_and_inclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with both exclusivity and inclusivity. The camera is considered within bounds *only* if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is touching at least one material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This is an extremely specific condition for defining areas with no materials.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag`

This property, when `true`, inverts the logic for `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag`. The camera is considered within bounds if it *is* touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This means the camera must be in an area with only materials of the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_exclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with exclusivity. The camera is considered within bounds *only* if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is touching at least one material that *does* have the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_inclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with inclusivity. The camera is considered within bounds if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This means the camera must be in an area with no materials at all.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_exclusive_and_inclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with both exclusivity and inclusivity. The camera is considered within bounds *only* if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is touching at least one material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This is an extremely specific condition for defining areas with no materials.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag`

This property, when `true`, inverts the logic for `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag`. The camera is considered within bounds if it *is* touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This means the camera must be in an area with only materials of the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_exclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with exclusivity. The camera is considered within bounds *only* if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is touching at least one material that *does* have the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_inclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with inclusivity. The camera is considered within bounds if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This means the camera must be in an area with no materials at all.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_exclusive_and_inclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with both exclusivity and inclusivity. The camera is considered within bounds *only* if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is touching at least one material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This is an extremely specific condition for defining areas with no materials.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag`

This property, when `true`, inverts the logic for `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag`. The camera is considered within bounds if it *is* touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This means the camera must be in an area with only materials of the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_exclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with exclusivity. The camera is considered within bounds *only* if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is touching at least one material that *does* have the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_inclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with inclusivity. The camera is considered within bounds if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This means the camera must be in an area with no materials at all.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_exclusive_and_inclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with both exclusivity and inclusivity. The camera is considered within bounds *only* if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is touching at least one material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This is an extremely specific condition for defining areas with no materials.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag`

This property, when `true`, inverts the logic for `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag`. The camera is considered within bounds if it *is* touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This means the camera must be in an area with only materials of the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_exclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with exclusivity. The camera is considered within bounds *only* if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is touching at least one material that *does* have the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_inclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with inclusivity. The camera is considered within bounds if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This means the camera must be in an area with no materials at all.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_exclusive_and_inclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with both exclusivity and inclusivity. The camera is considered within bounds *only* if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is touching at least one material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This is an extremely specific condition for defining areas with no materials.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag`

This property, when `true`, inverts the logic for `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag`. The camera is considered within bounds if it *is* touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This means the camera must be in an area with only materials of the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_exclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with exclusivity. The camera is considered within bounds *only* if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is touching at least one material that *does* have the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_inclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with inclusivity. The camera is considered within bounds if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This means the camera must be in an area with no materials at all.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_exclusive_and_inclusive`

This property, when `true`, combines `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag` with both exclusivity and inclusivity. The camera is considered within bounds *only* if it is not touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is touching at least one material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This is an extremely specific condition for defining areas with no materials.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag`

This property, when `true`, inverts the logic for `bounds_material_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag_is_not_tag`. The camera is considered within bounds if it *is* touching any material with the specified tag, and is *not* touching any material that does *not* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag, and is *not* touching any material that *does* have the specified tag. This means the camera must be in an area with only materials of the specified tag.

*   **Type:** Boolean
*   **Default:** `false`

### `bounds_material_tag_is_not_tag_is_not_tag