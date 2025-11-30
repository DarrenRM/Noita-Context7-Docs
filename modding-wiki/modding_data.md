---
title: Modding: Data.wak - Understanding Noita's Base Assets
source: https://noita.wiki.gg/wiki/Modding:_Data.wak
category: modding-wiki
---

# Modding: Data.wak - Understanding Noita's Base Assets

This documentation explains the `data.wak` file, which contains Noita's base game assets and internal directory structure. Understanding this structure is crucial for modders who need to replace or modify existing game assets, as mods must follow these paths precisely to override default behaviors and content.

## Understanding the Data Directory Structure

The `data.wak` file, often referred to as the "data files," represents the core assets of Noita. When extracted, it reveals a specific directory structure that the game uses internally. Mods that aim to alter or replace these base assets must adhere to this exact pathing.

For instructions on how to extract these data files, refer to the [Modding: Extracting data files](https://noita.wiki.gg/wiki/Modding#Extracting_data_files) guide.

Here is a breakdown of the primary directories within the extracted `data` folder:

```
data/
 ├── biome/
 │   └── All biome definition XMLs, defining the biome metadata (name, scripts, paths, ...)
 │       and generation parameters (topology, vegetation, ...)
 ├── biome_impl/
 │   └── Biome image files that are not Wang tiles; pixel scenes, backgrounds
 ├── buildings_gfx/
 ├── collapse_masks/
 ├── debug/
 ├── enemies_gfx/
 │   └── Enemies, friendlies, the player; all "unit" graphics go here.
 ├── entities/
 │   └── The main beef, most (if not all) of the entity definitions can be found here.
 ├── generated/
 ├── global/
 ├── items_gfx/
 ├── materials_gfx/
 │   └── Image files for materials that have textures in addition to their base color.
 ├── particles/
 ├── procedural_gfx/
 ├── projectiles_gfx/
 ├── props_breakable_gfx/
 ├── props_gfx/
 ├── ragdolls/
 │   └── Ragdoll directories for each enemy/friendly that requires it.
 ├── schemas/
 │   └── XML Schema definitions, when the documentations are lacking, this should be exhaustive. Although probably not so useful.
 ├── scripts/
 │   └── Most of the Lua code, sorted by different types in subdirectories
 │   └── E.g. data/scripts/gun/gun_actions.lua contains some Spell info
 ├── shaders/
 │   └── OpenGL shader files, totally editable. But prefer the new Lua API instead
 ├── temp/
 ├── translations/
 │   └── UI strings: `common.csv` and `common_dev.csv` files
 ├── ui_gfx/
 ├── vegetation/
 ├── wang_tiles/
 │   └── Contains all biome Wang tiles
 └── weather_gfx/
```

## Finding and Interpreting Game Data

Modders often need to find specific information within the game's data files to make their modifications. This section provides guidance on locating and understanding various game elements.

### General Data Interpretation Notes

*   **HP and Damage:** Values for HP and damage in the data files are typically represented as 1/25th of their in-game values. For example, `hp="3.5"` in a data file corresponds to `3.5 * 25 = 87.5` HP in-game.
*   **Time-Based Values:** Any values related to time (recharge time, cast delay, spell lifetime, etc.) are measured in **frames**. Noita generally runs at 60 frames per second (fps). Therefore, to convert frames to seconds, divide by 60. For instance, a spell with a lifetime of 200 frames lasts `200 / 60 = 3.33` seconds.
*   **XML Entity Inheritance:** Entity files in XML format can inherit properties from other entity files. This is indicated by `<Base>..</Base>` tags containing a reference to the base file. The inheriting file adopts all components and properties from the base file and can then override specific parts by defining them within the `<Base>...</Base>` section.

### Locating Specific Game Elements

*   **Spells:**
    *   Lua scripts for spell actions are found in `data/scripts/gun/gun_actions.lua`.
    *   Projectile definitions for spells are located in `data/entities/projectiles/deck/`.
    *   Cast delay for spells is primarily controlled by `c.fire_rate_wait` in `gun_actions.lua`. Both projectiles and modifiers can set or add to this cast delay.

*   **Enemies:**
    *   Enemy entity files are generally found in `data/entities/animals/`.
    *   For information on enemy protections and immunities, consult the [Enemy Immunities](https://noita.wiki.gg/wiki/Enemy_Immunities) page. Key terms to search for within enemy files include "protection," "air," "physics," "ignition," and relevant tags.
    *   The most critical enemy information is typically found within their Entity tags and the `DamageModelComponent`.

*   **Perks:**
    *   The main perk list is in `data/scripts/perks/perk_list.lua`.
    *   Individual perk scripts are located in `data/scripts/perks/`.
    *   Essence-related scripts are in `data/scripts/essences/`.
    *   Perk pickup entities are in `data/entities/items/pickup/`.
    *   Essence entities are in `data/entities/misc/essences/`.

*   **Wands:**
    *   Wand entity definitions are in `data/entities/items/wands/`.
    *   Scripts for procedural wand generation can be found in `data/scripts/gun/procedural/`.

### Biomes: Code-names vs. Game/Wiki-names

This table maps the internal code-names used for biomes to their in-game and wiki-recognized names.

| Code-names       | Game/Wiki-names             |
| :--------------- | :-------------------------- |
| coalmine         | [Mines](https://noita.wiki.gg/wiki/Mines) |
| coalmine\_alt    | [Collapsed Mines](https://noita.wiki.gg/wiki/Collapsed_Mines) |
| boss\_arena      | [The Laboratory](https://noita.wiki.gg/wiki/The_Laboratory) |
| boss\_victoryroom | [The Work (End)](https://noita.wiki.gg/wiki/The_Work_(End)) |
| crypt            | [Temple of the Art](https://noita.wiki.gg/wiki/Temple_of_the_Art) |
| desert           | [Desert](https://noita.wiki.gg/wiki/Desert) |
| dragoncave       | [Dragoncave](https://noita.wiki.gg/wiki/Dragoncave) |
| excavationsite   | [Coal Pits](https://noita.wiki.gg/wiki/Coal_Pits) |
| hills            | [Forest](https://noita.wiki.gg/wiki/Forest) |
| fungicave        | [Fungal Caverns](https://noita.wiki.gg/wiki/Fungal_Caverns) |
| gold             | [The Gold](https://noita.wiki.gg/wiki/The_Gold) |
| lake             | [Lake](https://noita.wiki.gg/wiki/Lake) |
| lava             | [Volcanic Lake](https://noita.wiki.gg/wiki/Volcanic_Lake) |
| lavacave         | Volcanic Cave               |
| magic\_gate      | Sanctuary                   |
| null\_room       | [Nullifying Altar](https://noita.wiki.gg/wiki/Nullifying_Altar) |
| pyramid          | [Pyramid](https://noita.wiki.gg/wiki/Pyramid) |
| rainforest       | [Underground Jungle](https://noita.wiki.gg/wiki/Underground_Jungle) |
| sandcave         | [Sandcave](https://noita.wiki.gg/wiki/Sandcave) |
| secret\_entrance | Mysterious Gate             |
| shop\_room       | [Secret Shop](https://noita.wiki.gg/wiki/Secret_Shop) |
| snowcastle       | [Hiisi Base](https://noita.wiki.gg/wiki/Hiisi_Base) |
| snowcave         | [Snowy Depths](https://noita.wiki.gg/wiki/Snowy_Depths) |
| town\_under      | [Twisty Passages](https://noita.wiki.gg/wiki/Twisty_Passages) |
| vault            | [The Vault](https://noita.wiki.gg/wiki/The_Vault) |
| wandcave         | [Magical Temple](https://noita.wiki.gg/wiki/Magical_Temple) |
| water            | [Water (Biome)](https://noita.wiki.gg/wiki/Water_(Biome)) |
| winter           | [Snowy Wasteland](https://noita.wiki.gg/wiki/Snowy_Wasteland) |
| holymountain     | [Holy Mountain](https://noita.wiki.gg/wiki/Holy_Mountain) |
| tower            | [Tower](https://noita.wiki.gg/wiki/Tower) |
| vault\_frozen    | [Frozen Vault](https://noita.wiki.gg/wiki/Frozen_Vault) |
| clouds           | [Cloudscape](https://noita.wiki.gg/wiki/Cloudscape) |
| liquidcave       | [Ancient Laboratory](https://noita.wiki.gg/wiki/Ancient_Laboratory) |
| secret\_lab      | [Abandoned Alchemy Lab](https://noita.wiki.gg/wiki/Abandoned_Alchemy_Lab) |
| weathercrystal   | Crystal Chamber             |
| greed\_room      | [Hall of Wealth](https://noita.wiki.gg/wiki/Hall_of_Wealth) |
| orbroom          | [Orb Room](https://noita.wiki.gg/wiki/Orb_Room) |
| wizardcave       | [Wizards' Den](https://noita.wiki.gg/wiki/Wizards%27_Den) |
| rainforest\_dark | [Lukki Lair](https://noita.wiki.gg/wiki/Lukki_Lair) |
| mestari\_secret  | [Throne Room](https://noita.wiki.gg/wiki/Throne_Room) |
| ghost\_secret    | [Forgotten Cave](https://noita.wiki.gg/wiki/Forgotten_Cave) |
| winter\_caves    | [Snowy Chasm](https://noita.wiki.gg/wiki/Snowy_Chasm) |
| robobase         | [Power Plant](https://noita.wiki.gg/wiki/Power_Plant) |
| fungiforest      | [Overgrown Cavern](https://noita.wiki.gg/wiki/Overgrown_Cavern) |
| underwater       | Sunken Cavern               |
| the\_end         | [The Work (Hell)](https://noita.wiki.gg/wiki/The_Work_(Hell)) |
| the\_sky         | [The Work (Sky)](https://noita.wiki.gg/wiki/The_Work_(Sky)) |
| potion\_mimics   | [Henkevä Temple](https://noita.wiki.gg/wiki/Henkev%C3%A4_Temple) |
| boss\_sky        | Lohkare Temple              |
| boss\_sky2       | [Kivi Temple](https://noita.wiki.gg/wiki/Kivi_Temple) |
| barren           | [Barren Temple](https://noita.wiki.gg/wiki/Barren_Temple) |
| darkness         | [Ominous Temple](https://noita.wiki.gg/wiki/Ominous_Temple) |
| watchtower       | [Watchtower](https://noita.wiki.gg/wiki/Watchtower) |