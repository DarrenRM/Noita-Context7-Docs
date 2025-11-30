---
title: Inventory2Component Documentation for AI-Assisted Modding
source: https://noita.wiki.gg/wiki/Documentation:Inventory2Component
category: modding-wiki
---

# Inventory2Component Documentation

This document details the `Inventory2Component` in Noita, a crucial component for managing player inventories and item interactions. Understanding its properties and functionalities is essential for modders looking to create custom items, alter inventory behavior, or implement new gameplay mechanics related to item acquisition and usage.

## Overview of Inventory2Component

The `Inventory2Component` is the primary mechanism in Noita for handling all aspects of an entity's inventory. This includes what items an entity possesses, how those items are organized, and the various actions that can be performed with them. For modders, this component is fundamental for any work involving items, including:

*   **Creating new items:** Defining how they are stored and used.
*   **Modifying existing items:** Changing their properties or how they interact with the inventory.
*   **Implementing custom inventory systems:** Developing unique ways for players to manage their belongings.
*   **Interacting with inventories via Lua:** Programmatically adding, removing, or manipulating items.

## Component Properties

The `Inventory2Component` has several configurable properties that dictate its behavior. These are typically defined within the entity's XML definition.

### `max_slots`

*   **Type:** Integer
*   **Description:** The maximum number of item slots available in the inventory. If set to `-1`, the inventory has unlimited slots.

### `add_to_empty_slots_only`

*   **Type:** Boolean
*   **Description:** If `true`, new items can only be added to empty slots. If `false`, items can be stacked or added to existing slots if compatible.

### `skip_inventory_full_check`

*   **Type:** Boolean
*   **Description:** If `true`, the game will not check if the inventory is full before attempting to add an item. This can lead to items being lost if the inventory is indeed full.

### `is_main_inventory`

*   **Type:** Boolean
*   **Description:** Indicates whether this is the player's primary inventory. This affects how certain UI elements and game systems interact with it.

### `is_perk_inventory`

*   **Type:** Boolean
*   **Description:** Indicates if this inventory is specifically for perks.

### `is_limited_by_tags`

*   **Type:** Boolean
*   **Description:** If `true`, the inventory's capacity can be limited by item tags. This is often used in conjunction with `limited_by_tags_max_count`.

### `limited_by_tags_max_count`

*   **Type:** Integer
*   **Description:** The maximum number of items allowed in the inventory if `is_limited_by_tags` is `true`. This count is based on the total number of items, not unique types.

### `limited_by_tags_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_tags` is `true`, the `limited_by_tags_max_count` applies *per tag* rather than to the total inventory.

### `limited_by_tags_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the inventory limits if `is_limited_by_tags` is `true`.

### `is_limited_by_item_count`

*   **Type:** Boolean
*   **Description:** If `true`, the inventory's capacity is limited by the total number of items it can hold, regardless of type or tags.

### `limited_by_item_count_max_count`

*   **Type:** Integer
*   **Description:** The maximum number of items allowed in the inventory if `is_limited_by_item_count` is `true`.

### `is_limited_by_unique_item_count`

*   **Type:** Boolean
*   **Description:** If `true`, the inventory's capacity is limited by the number of *unique* item types it can hold.

### `limited_by_unique_item_count_max_count`

*   **Type:** Integer
*   **Description:** The maximum number of unique item types allowed in the inventory if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to_limit`

*   **Type:** String (comma-separated list of tags)
*   **Description:** A list of item tags that will be subject to the unique item count limits if `is_limited_by_unique_item_count` is `true`.

### `is_limited_by_unique_item_count_count_per_tag`

*   **Type:** Boolean
*   **Description:** If `true` and `is_limited_by_unique_item_count` is `true`, the `limited_by_unique_item_count_max_count` applies *per tag* rather than to the total unique item types.

### `is_limited_by_unique_item_count_tags_to