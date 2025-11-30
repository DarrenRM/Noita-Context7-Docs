---
title: Wizard Cave Biome Configuration
category: scripts
---

---

# Wizard Cave Biome Configuration

This document details the configuration for the Wizard Cave biome in Noita, focusing on the entities and elements that can spawn within it. This script defines various spawn tables and functions that the game uses to populate the biome with enemies, items, and environmental props.

## Core Biome Setup

The script begins by including essential helper files for game logic and biome generation.

```lua
dofile_once("data/scripts/director_helpers.lua")
dofile_once("data/scripts/director_helpers_design.lua")
dofile_once("data/scripts/biome_scripts.lua")
dofile_once("data/scripts/biome_modifiers.lua")
dofile( "data/scripts/items/generate_shop_item.lua" )
```

Several `RegisterSpawnFunction` calls link specific color codes within the biome's pixel data to corresponding spawning functions. These functions are triggered when the game encounters these colors during level generation.

```lua
RegisterSpawnFunction( 0xffffeedd, "init" ) -- General initialization
RegisterSpawnFunction( 0xff808000, "spawn_statues" ) -- Statues
RegisterSpawnFunction( 0xff00AC33, "load_pixel_scene3" ) -- Pixel scene variant
RegisterSpawnFunction( 0xff00AC64, "load_pixel_scene4" ) -- Pixel scene variant
RegisterSpawnFunction( 0xff97ab00, "load_pixel_scene5" ) -- Pixel scene variant
RegisterSpawnFunction( 0xffc9d959, "load_pixel_scene5b" ) -- Pixel scene variant
RegisterSpawnFunction( 0xffC8C800, "spawn_lamp2" ) -- Specific lamp type
RegisterSpawnFunction( 0xff400080, "spawn_large_enemies" ) -- Larger enemy types
RegisterSpawnFunction( 0xffC8001A, "spawn_ghost_crystal" ) -- Ghost crystal entities
RegisterSpawnFunction( 0xff82FF5A, "spawn_crawlers" ) -- Crawler entities
RegisterSpawnFunction( 0xff647D7D, "spawn_pressureplates" ) -- Pressure plates
RegisterSpawnFunction( 0xff649B7D, "spawn_doors" ) -- Doors
RegisterSpawnFunction( 0xffA07864, "spawn_scavengers" ) -- Scavenger enemies
RegisterSpawnFunction( 0xffFFCD2A, "spawn_scorpions" ) -- Scorpion enemies
RegisterSpawnFunction( 0xff2D1E5A, "spawn_bones" ) -- Bone props
RegisterSpawnFunction( 0xff782060, "load_beam" ) -- Beam effects
RegisterSpawnFunction( 0xff783060, "load_background_scene" ) -- Background elements
RegisterSpawnFunction( 0xff378ec4, "load_small_background_scene" ) -- Smaller background elements
RegisterSpawnFunction( 0xff786460, "load_cavein" ) -- Cave-in events
RegisterSpawnFunction( 0xff80FF5A, "spawn_vines" ) -- Vine props
RegisterSpawnFunction( 0xff535988, "spawn_statue_back" ) -- Back of statues
RegisterSpawnFunction( 0xff33934c, "spawn_shopitem" ) -- Shop items
```

## Entity Spawn Tables

These tables define the probability and types of entities that can spawn in the biome. Each entry includes a `prob` (probability), `min_count`, and `max_count` for the entity.

### Small Enemies (`g_small_enemies`)

This table defines the smaller enemy types that can appear in the Wizard Cave.

| Probability | Min Count | Max Count | Entity                                     |
| :---------- | :-------- | :-------- | :----------------------------------------- |
| 0.4         | 0         | 0         | (No spawn - air)                           |
| 0.2         | 2         | 3         | `data/entities/animals/firemage.xml`       |
| 0.2         | 2         | 3         | `data/entities/animals/thundermage.xml`    |
| 0.05        | 1         | 1         | `data/entities/animals/icemage.xml`        |
| 0.1         | 1         | 1         | `data/entities/animals/wizard_tele.xml`    |
| 0.1         | 1         | 1         | `data/entities/animals/wizard_poly.xml`    |
| 0.1         | 1         | 1         | `data/entities/animals/wizard_dark.xml`    |
| 0.1         | 1         | 1         | `data/entities/animals/wizard_swapper.xml` |
| 0.1         | 1         | 1         | `data/entities/animals/wizard_neutral.xml` |
| 0.1         | 1         | 1         | `data/entities/animals/wizard_returner.xml`|
| 0.1         | 1         | 1         | `data/entities/animals/wizard_hearty.xml`  |
| 0.1         | 1         | 1         | `data/entities/animals/wizard_twitchy.xml` |
| 0.1         | 1         | 1         | `data/entities/animals/wizard_weaken.xml`  |
| 0.1         | 1         | 1         | `data/entities/animals/wizard_homing.xml`  |
| 0.1         | 1         | 1         | `data/entities/animals/barfer.xml`         |
| 0.1         | 1         | 1         | `data/entities/animals/failed_alchemist.xml`|

### Big Enemies (`g_big_enemies`)

This table defines the larger or more significant enemy types. Some entries can spawn multiple entity types.

| Probability | Min Count | Max Count | Entities