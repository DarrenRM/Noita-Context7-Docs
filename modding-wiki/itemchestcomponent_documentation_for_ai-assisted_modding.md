---
title: ItemChestComponent Documentation for AI-Assisted Modding
source: https://noita.wiki.gg/wiki/Documentation:ItemChestComponent
category: modding-wiki
---

# ItemChestComponent Documentation

This documentation covers the `ItemChestComponent` in Noita, a crucial component for defining the contents and behavior of chests. Understanding this component is essential for modders who wish to customize loot tables, create unique chest types, or influence what items players find in the game world.

## Overview of ItemChestComponent

The `ItemChestComponent` is an XML component used within Noita's entity system to manage the items that can be found within a chest. It dictates the probability of certain items appearing, the types of items that can spawn, and how the chest's contents are generated.

## Component Properties

The `ItemChestComponent` has several properties that can be configured to customize chest behavior.

### `chest_contents_file`

This property specifies the path to an XML file that defines the actual loot table for the chest. This file contains the list of items, their spawn probabilities, and any associated conditions.

**Example:**

```xml
<ItemChestComponent chest_contents_file="data/chests/my_custom_chest_loot.xml" />
```

### `random_item_count`

This property defines a range for the number of random items that will be generated from the `chest_contents_file`. The game will pick a random number of items between the minimum and maximum values specified.

**Example:**

```xml
<ItemChestComponent chest_contents_file="data/chests/my_custom_chest_loot.xml" random_item_count="3, 7" />
```

In this example, the chest will spawn between 3 and 7 random items.

### `always_spawn_special_item`

A boolean value (`true` or `false`) that determines if a "special" item from the loot table should always be spawned, regardless of random chance. This is often used to guarantee a certain type of item appears.

**Example:**

```xml
<ItemChestComponent chest_contents_file="data/chests/my_custom_chest_loot.xml" random_item_count="3, 7" always_spawn_special_item="true" />
```

### `special_item_probability`

If `always_spawn_special_item` is `false`, this property defines the probability (as a decimal between 0 and 1) that a special item will spawn.

**Example:**

```xml
<ItemChestComponent chest_contents_file="data/chests/my_custom_chest_loot.xml" random_item_count="3, 7" special_item_probability="0.5" />
```

This means there's a 50% chance for a special item to spawn.

### `item_material_type`

This property can be used to influence the material type of the items spawned in the chest. Common values include:

*   `any`
*   `wood`
*   `stone`
*   `metal`
*   `magic`

**Example:**

```xml
<ItemChestComponent chest_contents_file="data/chests/my_custom_chest_loot.xml" random_item_count="3, 7" item_material_type="magic" />
```

### `item_rarity`

This property can be used to influence the rarity of the items spawned in the chest. Common values include:

*   `any`
*   `common`
*   `uncommon`
*   `rare`
*   `epic`
*   `legendary`

**Example:**

```xml
<ItemChestComponent chest_contents_file="data/chests/my_custom_chest_loot.xml" random_item_count="3, 7" item_rarity="rare" />
```

### `item_tags`

This property allows you to specify a comma-separated list of tags that the spawned items must possess. This is a powerful way to filter loot.

**Example:**

```xml
<ItemChestComponent chest_contents_file="data/chests/my_custom_chest_loot.xml" random_item_count="3, 7" item_tags="wand,fire" />
```

This would attempt to spawn items that are both wands and have the "fire" tag.

## Defining Chest Contents (`chest_contents_file`)

The XML file specified by `chest_contents_file` is where you define the actual items that can be found in a chest. This file typically contains a `<ItemChestContents>` root element.

### `<ItemChestContents>`

This is the main container for loot definitions.

### `<Item`>

Each `<Item>` tag within `<ItemChestContents>` defines a potential item that can spawn.

#### `name`

The `name` attribute specifies the internal ID of the item to spawn.

**Example:**

```xml
<Item name="wand_fire" />
```

#### `prob`

The `prob` attribute defines the probability of this specific item spawning, relative to other items in the same loot table. The probabilities are normalized, meaning they don't need to add up to 1.

**Example:**

```xml
<Item name="wand_fire" prob="1.0" />
<Item name="wand_ice" prob="0.5" />
```

In this case, `wand_fire` is twice as likely to spawn as `wand_ice`.

#### `min_amount` and `max_amount`

These attributes define the minimum and maximum number of this specific item that can spawn if it is chosen.

**Example:**

```xml
<Item name="potion_health" prob="2.0" min_amount="1" max_amount="3" />
```

This would spawn 1 to 3 health potions if the health potion is selected.

#### `tags`

Similar to the `item_tags` property on the component, this allows you to add tags to the spawned item.

**Example:**

```xml
<Item name="wand_fire" prob="1.0" tags="wand,fire,explosive" />
```

#### `material_type`

Specifies the material type for this item.

**Example:**

```xml
<Item name="wand_fire" prob="1.0" material_type="magic" />
```

#### `rarity`

Specifies the rarity for this item.

**Example:**

```xml
<Item name="wand_fire" prob="1.0" rarity="rare" />
```

### Example `chest_contents_file`

```xml
<?xml version="1.0" encoding="utf-8"?>
<ItemChestContents>
    <!-- Common items -->
    <Item name="potion_health" prob="5.0" min_amount="1" max_amount="3" />
    <Item name="potion_mana" prob="3.0" min_amount="1" max_amount="2" />
    <Item name="gold" prob="10.0" min_amount="50" max_amount="200" />

    <!-- Wands -->
    <Item name="wand_fire" prob="2.0" rarity="uncommon" tags="wand,fire" />
    <Item name="wand_ice" prob="1.5" rarity="uncommon" tags="wand,ice" />
    <Item name="wand_lightning" prob="1.0" rarity="rare" tags="wand,lightning" />

    <!-- Special item example -->
    <Item name="cursed_idol" prob="0.2" rarity="epic" tags="cursed" />
</ItemChestContents>
```

## Integrating `ItemChestComponent` into Entities

To use the `ItemChestComponent`, you need to add it to an entity definition in an XML file. This is typically done within the `<Entity>` tag.

**Example Entity Definition:**

```xml
<Entity name="data/entities/world_objects/chests/basic_chest.xml">
    <LuaComponent script_path="data/scripts/world_objects/chest.lua" />
    <ItemChestComponent
        chest_contents_file="data/chests/basic_loot.xml"
        random_item_count="2, 5"
        always_spawn_special_item="false"
        special_item_probability="0.3"
        item_material_type="any"
        item_rarity="any"
        item_tags="any"
    />
    <Sprite sprite_file="data/props/world_objects/chests/basic_chest.png" />
    <HitboxComponent
        _tags="collidable"
        radius="12"
        offset_x="0"
        offset_y="0"
    />
    <DamageComponent
        hp="10"
        knockback_force="1"
    />
    <ExplosionComponent
        explosion_radius="10"
        explosion_damage="5"
        explosion_force="10"
    />
    <ParticleEmitterComponent
        sprite_file="data/particles/spark.png"
        delay="0.1"
        lifetime="0.5"
        emit_speed="20"
        spray_angle="360"
        chunk_size="1"
        chunk_speed="10"
        chunk_radius="3"
        fade_out="true"
        use_random_rotation="true"
        offset_x="0"
        offset_y="0"
    />
</Entity>
```

In this example, `basic_chest.xml` defines a chest that uses `data/chests/basic_loot.xml` for its contents, spawns 2 to 5 items, has a 30% chance of spawning a special item, and has no specific material, rarity, or tag restrictions on the spawned items.

## Important Links

*   [Lua API](https://noita.wiki.gg/wiki/Modding:_Lua_API)
*   [Entity Component System](https://noita.wiki.gg/wiki/Modding:_Entity_Component_System)
*   [Noita Wiki - Chests](https://noita.wiki.gg/wiki/Chests)