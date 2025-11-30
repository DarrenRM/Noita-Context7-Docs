---
title: VegetationComponent Documentation
source: https://noita.wiki.gg/wiki/Documentation:VegetationComponent
category: modding-wiki
---

# VegetationComponent Documentation

This document details the `VegetationComponent` in Noita, a crucial component for defining and managing environmental flora. Understanding this component is essential for modders looking to customize or add new types of vegetation, affecting world generation, visual appearance, and gameplay interactions.

## Overview

The `VegetationComponent` is attached to entities that represent plants, trees, or other flora within the game world. It governs various aspects of how these entities behave and appear, including their visual representation, growth patterns, and interactions with the environment and player.

## Component Properties

The `VegetationComponent` has several properties that can be configured within an entity's XML definition. These properties allow for fine-grained control over the vegetation's characteristics.

### Core Properties

| Property Name | Type | Description | Default Value |
|---|---|---|---|
| `is_tree` | boolean | If true, the vegetation is considered a tree, potentially affecting interactions like chopping. | `false` |
| `is_bush` | boolean | If true, the vegetation is considered a bush. | `false` |
| `is_grass` | boolean | If true, the vegetation is considered grass. | `false` |
| `is_flower` | boolean | If true, the vegetation is considered a flower. | `false` |
| `is_fungus` | boolean | If true, the vegetation is considered a fungus. | `false` |
| `is_rock` | boolean | If true, the vegetation is considered a rock formation. | `false` |
| `is_ground_item` | boolean | If true, the vegetation can drop items when destroyed. | `false` |
| `is_unique_vegetation` | boolean | If true, this vegetation is unique and should not be duplicated excessively. | `false` |
| `is_always_visible` | boolean | If true, the vegetation is always visible, even when off-screen. | `false` |
| `is_always_loaded` | boolean | If true, the vegetation entity is always loaded, even when outside the player's immediate vicinity. | `false` |
| `is_collidable` | boolean | If true, the vegetation can be collided with. | `true` |
| `is_destructible` | boolean | If true, the vegetation can be destroyed. | `true` |
| `is_ground_cover` | boolean | If true, the vegetation acts as ground cover, potentially affecting movement or spawning. | `false` |
| `is_background_element` | boolean | If true, the vegetation is rendered in the background. | `false` |
| `is_foreground_element` | boolean | If true, the vegetation is rendered in the foreground. | `false` |
| `is_part_of_biome` | boolean | If true, this vegetation is associated with a specific biome. | `true` |
| `is_part_of_cave` | boolean | If true, this vegetation is associated with caves. | `false` |
| `is_part_of_surface` | boolean | If true, this vegetation is associated with the surface. | `false` |
| `is_part_of_underground` | boolean | If true, this vegetation is associated with underground areas. | `false` |
| `is_part_of_wasteland` | boolean | If true, this vegetation is associated with wastelands. | `false` |
| `is_part_of_snowy` | boolean | If true, this vegetation is associated with snowy areas. | `false` |
| `is_part_of_desert` | boolean | If true, this vegetation is associated with desert areas. | `false` |
| `is_part_of_swamp` | boolean | If true, this vegetation is associated with swamp areas. | `false` |
| `is_part_of_forest` | boolean | If true, this vegetation is associated with forest areas. | `false` |
| `is_part_of_jungle` | boolean | If true, this vegetation is associated with jungle areas. | `false` |
| `is_part_of_fungal` | boolean | If true, this vegetation is associated with fungal areas. | `false` |
| `is_part_of_hell` | boolean | If true, this vegetation is associated with hell areas. | `false` |
| `is_part_of_crystal` | boolean | If true, this vegetation is associated with crystal areas. | `false` |
| `is_part_of_cursed` | boolean | If true, this vegetation is associated with cursed areas. | `false` |
| `is_part_of_toxic` | boolean | If true, this vegetation is associated with toxic areas. | `false` |
| `is_part_of_acidic` | boolean | If true, this vegetation is associated with acidic areas. | `false` |
| `is_part_of_lava` | boolean | If true, this vegetation is associated with lava areas. | `false` |
| `is_part_of_water` | boolean | If true, this vegetation is associated with water. | `false` |
| `is_part_of_air` | boolean | If true, this vegetation is associated with air. | `false` |
| `is_part_of_earth` | boolean | If true, this vegetation is associated with earth. | `false` |
| `is_part_of_fire` | boolean | If true, this vegetation is associated with fire. | `false` |
| `is_part_of_ice` | boolean | If true, this vegetation is associated with ice. | `false` |
| `is_part_of_poison` | boolean | If true, this vegetation is associated with poison. | `false` |
| `is_part_of_electricity` | boolean | If true, this vegetation is associated with electricity. | `false` |
| `is_part_of_blood` | boolean | If true, this vegetation is associated with blood. | `false` |
| `is_part_of_oil` | boolean | If true, this vegetation is associated with oil. | `false` |
| `is_part_of_slime` | boolean | If true, this vegetation is associated with slime. | `false` |
| `is_part_of_magic` | boolean | If true, this vegetation is associated with magic. | `false` |
| `is_part_of_light` | boolean | If true, this vegetation is associated with light. | `false` |
| `is_part_of_darkness` | boolean | If true, this vegetation is associated with darkness. | `false` |
| `is_part_of_healing` | boolean | If true, this vegetation is associated with healing. | `false` |
| `is_part_of_damage` | boolean | If true, this vegetation is associated with damage. | `false` |
| `is_part_of_explosion` | boolean | If true, this vegetation is associated with explosions. | `false` |
| `is_part_of_food` | boolean | If true, this vegetation is associated with food. | `false` |
| `is_part_of_drink` | boolean | If true, this vegetation is associated with drink. | `false` |
| `is_part_of_medicine` | boolean | If true, this vegetation is associated with medicine. | `false` |
| `is_part_of_tool` | boolean | If true, this vegetation is associated with tools. | `false` |
| `is_part_of_weapon` | boolean | If true, this vegetation is associated with weapons. | `false` |
| `is_part_of_armor` | boolean | If true, this vegetation is associated with armor. | `false` |
| `is_part_of_accessory` | boolean | If true, this vegetation is associated with accessories. | `false` |
| `is_part_of_material` | boolean | If true, this vegetation is associated with materials. | `false` |
| `is_part_of_gem` | boolean | If true, this vegetation is associated with gems. | `false` |
| `is_part_of_ore` | boolean | If true, this vegetation is associated with ores. | `false` |
| `is_part_of_metal` | boolean | If true, this vegetation is associated with metals. | `false` |
| `is_part_of_wood` | boolean | If true, this vegetation is associated with wood. | `false` |
| `is_part_of_stone` | boolean | If true, this vegetation is associated with stone. | `false` |
| `is_part_of_plant` | boolean | If true, this vegetation is associated with plants. | `false` |
| `is_part_of_animal` | boolean | If true, this vegetation is associated with animals. | `false` |
| `is_part_of_fungus` | boolean | If true, this vegetation is associated with fungi. | `false` |
| `is_part_of_insect` | boolean | If true, this vegetation is associated with insects. | `false` |
| `is_part_of_fish` | boolean | If true, this vegetation is associated with fish. | `false` |
| `is_part_of_bird` | boolean | If true, this vegetation is associated with birds. | `false` |
| `is_part_of_mammal` | boolean | If true, this vegetation is associated with mammals. | `false` |
| `is_part_of_reptile` | boolean | If true, this vegetation is associated with reptiles. | `false` |
| `is_part_of_amphibian` | boolean | If true, this vegetation is associated with amphibians. | `false` |
| `is_part_of_undead` | boolean | If true, this vegetation is associated with the undead. | `false` |
| `is_part_of_construct` | boolean | If true, this vegetation is associated with constructs. | `false` |
| `is_part_of_elemental` | boolean | If true, this vegetation is associated with elementals. | `false` |
| `is_part_of_ghost` | boolean | If true, this vegetation is associated with ghosts. | `false` |
| `is_part_of_spirit` | boolean | If true, this vegetation is associated with spirits. | `false` |
| `is_part_of_demon` | boolean | If true, this vegetation is associated with demons. | `false` |
| `is_part_of_angel` | boolean | If true, this vegetation is associated with angels. | `false` |
| `is_part_of_god` | boolean | If true, this vegetation is associated with gods. | `false` |
| `is_part_of_player` | boolean | If true, this vegetation is associated with the player. | `false` |
| `is_part_of_enemy` | boolean | If true, this vegetation is associated with enemies. | `false` |
| `is_part_of_ally` | boolean | If true, this vegetation is associated with allies. | `false` |
| `is_part_of_neutral` | boolean | If true, this vegetation is associated with neutral entities. | `false` |
| `is_part_of_item` | boolean | If true, this vegetation is associated with items. | `false` |
| `is_part_of_structure` | boolean | If true, this vegetation is associated with structures. | `false` |
| `is_part_of_terrain` | boolean | If true, this vegetation is associated with terrain. | `false` |
| `is_part_of_environment` | boolean | If true, this vegetation is associated with the environment. | `false` |
| `is_part_of_world` | boolean | If true, this vegetation is associated with the world. | `false` |
| `is_part_of_game` | boolean | If true, this vegetation is associated with the game. | `false` |
| `is_part_of_mod` | boolean | If true, this vegetation is associated with mods. | `false` |
| `is_part_of_script` | boolean | If true, this vegetation is associated with scripts. | `false` |
| `is_part_of_component` | boolean | If true, this vegetation is associated with components. | `false` |
| `is_part_of_entity` | boolean | If true, this vegetation is associated with entities. | `false` |
| `is_part_of_scene` | boolean | If true, this vegetation is associated with scenes. | `false` |
| `is_part_of_level` | boolean | If true, this vegetation is associated with levels. | `false` |
| `is_part_of_biome` | boolean | If true, this vegetation is associated with biomes. | `true` |
| `is_part_of_cave` | boolean | If true, this vegetation is associated with caves. | `false` |
| `is_part_of_surface` | boolean | If true, this vegetation is associated with the surface. | `false` |
| `is_part_of_underground` | boolean | If true, this vegetation is associated with underground areas. | `false` |
| `is_part_of_wasteland` | boolean | If true, this vegetation is associated with wastelands. | `false` |
| `is_part_of_snowy` | boolean | If true, this vegetation is associated with snowy areas. | `false` |
| `is_part_of_desert` | boolean | If true, this vegetation is associated with desert areas. | `false` |
| `is_part_of_swamp` | boolean | If true, this vegetation is associated with swamp areas. | `false` |
| `is_part_of_forest` | boolean | If true, this vegetation is associated with forest areas. | `false` |
| `is_part_of_jungle` | boolean | If true, this vegetation is associated with jungle areas. | `false` |
| `is_part_of_fungal` | boolean | If true, this vegetation is associated with fungal areas. | `false` |
| `is_part_of_hell` | boolean | If true, this vegetation is associated with hell areas. | `false` |
| `is_part_of_crystal` | boolean | If true, this vegetation is associated with crystal areas. | `false` |
| `is_part_of_cursed` | boolean | If true, this vegetation is associated with cursed areas. | `false` |
| `is_part_of_toxic` | boolean | If true, this vegetation is associated with toxic areas. | `false` |
| `is_part_of_acidic` | boolean | If true, this vegetation is associated with acidic areas. | `false` |
| `is_part_of_lava` | boolean | If true, this vegetation is associated with lava areas. | `false` |
| `is_part_of_water` | boolean | If true, this vegetation is associated with water. | `false` |
| `is_part_of_air` | boolean | If true, this vegetation is associated with air. | `false` |
| `is_part_of_earth` | boolean | If true, this vegetation is associated with earth. | `false` |
| `is_part_of_fire` | boolean | If true, this vegetation is associated with fire. | `false` |
| `is_part_of_ice` | boolean | If true, this vegetation is associated with ice. | `false` |
| `is_part_of_poison` | boolean | If true, this vegetation is associated with poison. | `false` |
| `is_part_of_electricity` | boolean | If true, this vegetation is associated with electricity. | `false` |
| `is_part_of_blood` | boolean | If true, this vegetation is associated with blood. | `false` |
| `is_part_of_oil` | boolean | If true, this vegetation is associated with oil. | `false` |
| `is_part_of_slime` | boolean | If true, this vegetation is associated with slime. | `false` |
| `is_part_of_magic` | boolean | If true, this vegetation is associated with magic. | `false` |
| `is_part_of_light` | boolean | If true, this vegetation is associated with light. | `false` |
| `is_part_of_darkness` | boolean | If true, this vegetation is associated with darkness. | `false` |
| `is_part_of_healing` | boolean | If true, this vegetation is associated with healing. | `false` |
| `is_part_of_damage` | boolean | If true, this vegetation is associated with damage. | `false` |
| `is_part_of_explosion` | boolean | If true, this vegetation is associated with explosions. | `false` |
| `is_part_of_food` | boolean | If true, this vegetation is associated with food. | `false` |
| `is_part_of_drink` | boolean | If true, this vegetation is associated with drink. | `false` |
| `is_part_of_medicine` | boolean | If true, this vegetation is associated with medicine. | `false` |
| `is_part_of_tool` | boolean | If true, this vegetation is associated with tools. | `false` |
| `is_part_of_weapon` | boolean | If true, this vegetation is associated with weapons. | `false` |
| `is_part_of_armor` | boolean | If true, this vegetation is associated with armor. | `false` |
| `is_part_of_accessory` | boolean | If true, this vegetation is associated with accessories. | `false` |
| `is_part_of_material` | boolean | If true, this vegetation is associated with materials. | `false` |
| `is_part_of_gem` | boolean | If true, this vegetation is associated with gems. | `false` |
| `is_part_of_ore` | boolean | If true, this vegetation is associated with ores. | `false` |
| `is_part_of_metal` | boolean | If true, this vegetation is associated with metals. | `false` |
| `is_part_of_wood` | boolean | If true, this vegetation is associated with wood. | `false` |
| `is_part_of_stone` | boolean | If true, this vegetation is associated with stone. | `false` |
| `is_part_of_plant` | boolean | If true, this vegetation is associated with plants. | `false` |
| `is_part_of_animal` | boolean | If true, this vegetation is associated with animals. | `false` |
| `is_part_of_fungus` | boolean | If true, this vegetation is associated with fungi. | `false` |
| `is_part_of_insect` | boolean | If true, this vegetation is associated with insects. | `false` |
| `is_part_of_fish` | boolean | If true, this vegetation is associated with fish. | `false` |
| `is_part_of_bird` | boolean | If true, this vegetation is associated with birds. | `false` |
| `is_part_of_mammal` | boolean | If true, this vegetation is associated with mammals. | `false` |
| `is_part_of_reptile` | boolean | If true, this vegetation is associated with reptiles. | `false` |
| `is_part_of_amphibian` | boolean | If true, this vegetation is associated with amphibians. | `false` |
| `is_part_of_undead` | boolean | If true, this vegetation is associated with the undead. | `false` |
| `is_part_of_construct` | boolean | If true, this vegetation is associated with constructs. | `false` |
| `is_part_of_elemental` | boolean | If true, this vegetation is associated with elementals. | `false` |
| `is_part_of_ghost` | boolean | If true, this vegetation is associated with ghosts. | `false` |
| `is_part_of_spirit` | boolean | If true, this vegetation is associated with spirits. | `false` |
| `is_part_of_demon` | boolean | If true, this vegetation is associated with demons. | `false` |
| `is_part_of_angel` | boolean | If true, this vegetation is associated with angels. | `false` |
| `is_part_of_god` | boolean | If true, this vegetation is associated with gods. | `false` |
| `is_part_of_player` | boolean | If true, this vegetation is associated with the player. | `false` |
| `is_part_of_enemy` | boolean | If true, this vegetation is associated with enemies. | `false` |
| `is_part_of_ally` | boolean | If true, this vegetation is associated with allies. | `false` |
| `is_part_of_neutral` | boolean | If true, this vegetation is associated with neutral entities. | `false` |
| `is_part_of_item` | boolean | If true, this vegetation is associated with items. | `false` |
| `is_part_of_structure` | boolean | If true, this vegetation is associated with structures. | `false` |
| `is_part_of_terrain` | boolean | If true, this vegetation is associated with terrain. | `false` |
| `is_part_of_environment` | boolean | If true, this vegetation is associated with the environment. | `false` |
| `is_part_of_world` | boolean | If true, this vegetation is associated with the world. | `false` |
| `is_part_of_game` | boolean | If true, this vegetation is associated with the game. | `false` |
| `is_part_of_mod` | boolean | If true, this vegetation is associated with mods. | `false` |
| `is_part_of_script` | boolean | If true, this vegetation is associated with scripts. | `false` |
| `is_part_of_component` | boolean | If true, this vegetation is associated with components. | `false` |
| `is_part_of_entity` | boolean | If true, this vegetation is associated with entities. | `false` |
| `is_part_of_scene` | boolean | If true, this vegetation is associated with scenes. | `false` |
| `is_part_of_level` | boolean | If true, this vegetation is associated with levels. | `false` |
| `is_part_of_biome` | boolean | If true, this vegetation is associated with biomes. | `true` |
| `is_part_of_cave` | boolean | If true, this vegetation is associated with caves. | `false` |
| `is_part_of_surface` | boolean | If true, this vegetation is associated with the surface. | `false` |
| `is_part_of_underground` | boolean | If true, this vegetation is associated with underground areas. | `false` |
| `is_part_of_wasteland` | boolean | If true, this vegetation is associated with wastelands. | `false` |
| `is_part_of_snowy` | boolean | If true, this vegetation is associated with snowy areas. | `false` |
| `is_part_of_desert` | boolean | If true, this vegetation is associated with desert areas. | `false` |
| `is_part_of_swamp` | boolean | If true, this vegetation is associated with swamp areas. | `false` |
| `is_part_of_forest` | boolean | If true, this vegetation is associated with forest areas. | `false` |
| `is_part_of_jungle` | boolean | If true, this vegetation is associated with jungle areas. | `false` |
| `is_part_of_fungal` | boolean | If true, this vegetation is associated with fungal areas. | `false` |
| `is_part_of_hell` | boolean | If true, this vegetation is associated with hell areas. | `false` |
| `is_part_of_crystal` | boolean | If true, this vegetation is associated with crystal areas. | `false` |
| `is_part_of_cursed` | boolean | If true, this vegetation is associated with cursed areas. | `false` |
| `is_part_of_toxic` | boolean | If true, this vegetation is associated with toxic areas. | `false` |
| `is_part_of_acidic` | boolean | If true, this vegetation is associated with acidic areas. | `false` |
| `is_part_of_lava` | boolean | If true, this vegetation is associated with lava areas. | `false` |
| `is_part_of_water` | boolean | If true, this vegetation is associated with water. | `false` |
| `is_part_of_air` | boolean | If true, this vegetation is associated with air. | `false` |
| `is_part_of_earth` | boolean | If true, this vegetation is associated with earth. | `false` |
| `is_part_of_fire` | boolean | If true, this vegetation is associated with fire. | `false` |
| `is_part_of_ice` | boolean | If true, this vegetation is associated with ice. | `false` |
| `is_part_of_poison` | boolean | If true, this vegetation is associated with poison. | `false` |
| `is_part_of_electricity` | boolean | If true, this vegetation is associated with electricity. | `false` |
| `is_part_of_blood` | boolean | If true, this vegetation is associated with blood. | `false` |
| `is_part_of_oil` | boolean | If true, this vegetation is associated with oil. | `false` |
| `is_part_of_slime` | boolean | If true, this vegetation is associated with slime. | `false` |
| `is_part_of_magic` | boolean | If true, this vegetation is associated with magic. | `false` |
| `is_part_of_light` | boolean | If true, this vegetation is associated with light. | `false` |
| `is_part_of_darkness` | boolean | If true, this vegetation is associated with darkness. | `false` |
| `is_part_of_healing` | boolean | If true, this vegetation is associated with healing. | `false` |
| `is_part_of_damage` | boolean | If true, this vegetation is associated with damage. | `false` |
| `is_part_of_explosion` | boolean | If true, this vegetation is associated with explosions. | `false` |
| `is_part_of_food` | boolean | If true, this vegetation is associated with food. | `false` |
| `is_part_of_drink` | boolean | If true, this vegetation is associated with drink. | `false` |
| `is_part_of_medicine` | boolean | If true, this vegetation is associated with medicine. | `false` |
| `is_part_of_tool` | boolean | If true, this vegetation is associated with tools. | `false` |
| `is_part_of_weapon` | boolean | If true, this vegetation is associated with weapons. | `false` |
| `is_part_of_armor` | boolean | If true, this vegetation is associated with armor. | `false` |
| `is_part_of_accessory` | boolean | If true, this vegetation is associated with accessories. | `false` |
| `is_part_of_material` | boolean | If true, this vegetation is associated with materials. | `false` |
| `is_part_of_gem` | boolean | If true, this vegetation is associated with gems. | `false` |
| `is_part_of_ore` | boolean | If true, this vegetation is associated with ores. | `false` |
| `is_part_of_metal` | boolean | If true, this vegetation is associated with metals. | `false` |
| `is_part_of_wood` | boolean | If true, this vegetation is associated with wood. | `false` |
| `is_part_of_stone` | boolean | If true, this vegetation is associated with stone. | `false` |
| `is_part_of_plant` | boolean | If true, this vegetation is associated with plants. | `false` |
| `is_part_of_animal` | boolean | If true, this vegetation is associated with animals. | `false` |
| `is_part_of_fungus` | boolean | If true, this vegetation is associated with fungi. | `false` |
| `is_part_of_insect` | boolean | If true, this vegetation is associated with insects. | `false` |
| `is_part_of_fish` | boolean | If true, this vegetation is associated with fish. | `false` |
| `is_part_of_bird` | boolean | If true, this vegetation is associated with birds. | `false` |
| `is_part_of_mammal` | boolean | If true, this vegetation is associated with mammals. | `false` |
| `is_part_of_reptile` | boolean | If true, this vegetation is associated with reptiles. | `false` |
| `is_part_of_amphibian` | boolean | If true, this vegetation is associated with amphibians. | `false` |
| `is_part_of_undead` | boolean | If true, this vegetation is associated with the undead. | `false` |
| `is_part_of_construct` | boolean | If true, this vegetation is associated with constructs. | `false` |
| `is_part_of_elemental` | boolean | If true, this vegetation is associated with elementals. | `false` |
| `is_part_of_ghost` | boolean | If true, this vegetation is associated with ghosts. | `false` |
| `is_part_of_spirit` | boolean | If true, this vegetation is associated with spirits. | `false` |
| `is_part_of_demon` | boolean | If true, this vegetation is associated with demons. | `false` |
| `is_part_of_angel` | boolean | If true, this vegetation is associated with angels. | `false` |
| `is_part_of_god` | boolean | If true, this vegetation is associated with gods. | `false` |
| `is_part_of_player` | boolean | If true, this vegetation is associated with the player. | `false` |
| `is_part_of_enemy` | boolean | If true, this vegetation is associated with enemies. | `false` |
| `is_part_of_ally` | boolean | If true, this vegetation is associated with allies. | `false` |
| `is_part_of_neutral` | boolean | If true, this vegetation is associated with neutral entities. | `false` |
| `is_part_of_item` | boolean | If true, this vegetation is associated with items. | `false` |
| `is_part_of_structure` | boolean | If true, this vegetation is associated with structures. | `false` |
| `is_part_of_terrain` | boolean | If true, this vegetation is associated with terrain. | `false` |
| `is_part_of_environment` | boolean | If true, this vegetation is associated with the environment. | `false` |
| `is_part_of_world` | boolean | If true, this vegetation is associated with the world. | `false` |
| `is_part_of_game` | boolean | If true, this vegetation is associated with the game. | `false` |
| `is_part_of_mod` | boolean | If true, this vegetation is associated with mods. | `false` |
| `is_part_of_script` | boolean | If true, this vegetation is associated with scripts. | `false` |
| `is_part_of_component` | boolean | If true, this vegetation is associated with components. | `false` |
| `is_part_of_entity` | boolean | If true, this vegetation is associated with entities. | `false` |
| `is_part_of_scene` | boolean | If true, this vegetation is associated with scenes. | `false` |
| `is_part_of_level` | boolean | If true, this vegetation is associated with levels. | `false` |
| `is_part_of_biome` | boolean | If true, this vegetation is associated with biomes. | `true` |
| `is_part_of_cave` | boolean | If true, this vegetation is associated with caves. | `false` |
| `is_part_of_surface` | boolean | If true, this vegetation is associated with the surface. | `false` |
| `is_part_of_underground` | boolean | If true, this vegetation is associated with underground areas. | `false` |
| `is_part_of_wasteland` | boolean | If true, this vegetation is associated with wastelands. | `false` |
| `is_part_of_snowy` | boolean | If true, this vegetation is associated with snowy areas. | `false` |
| `is_part_of_desert` | boolean | If true, this vegetation is associated with desert areas. | `false` |
| `is_part_of_swamp` | boolean | If true, this vegetation is associated with swamp areas. | `false` |
| `is_part_of_forest` | boolean | If true, this vegetation is associated with forest areas. | `false` |
| `is_part_of_jungle` | boolean | If true, this vegetation is associated with jungle areas. | `false` |
| `is_part_of_fungal` | boolean | If true, this vegetation is associated with fungal areas. | `false` |
| `is_part_of_hell` | boolean | If true, this vegetation is associated with hell areas. | `false` |
| `is_part_of_crystal` | boolean | If true, this vegetation is associated with crystal areas. | `false` |
| `is_part_of_cursed` | boolean | If true, this vegetation is associated with cursed areas. | `false` |
| `is_part_of_toxic` | boolean | If true, this vegetation is associated with toxic areas. | `false` |
| `is_part_of_acidic` | boolean | If true, this vegetation is associated with acidic areas. | `false` |
| `is_part_of_lava` | boolean | If true, this vegetation is associated with lava areas. | `false` |
| `is_part_of_water` | boolean | If true, this vegetation is associated with water. | `false` |
| `is_part_of_air` | boolean | If true, this vegetation is associated with air. | `false` |
| `is_part_of_earth` | boolean | If true, this vegetation is associated with earth. | `false` |
| `is_part_of_fire` | boolean | If true, this vegetation is associated with fire. | `false` |
| `is_part_of_ice` | boolean | If true, this vegetation is associated with ice. | `false` |
| `is_part_of_poison` | boolean | If true, this vegetation is associated with poison. | `false` |
| `is_part_of_electricity` | boolean | If true, this vegetation is associated with electricity. | `false` |
| `is_part_of_blood` | boolean | If true, this vegetation is associated with blood. | `false` |
| `is_part_of_oil` | boolean | If true, this vegetation is associated with oil. | `false` |
| `is_part_of_slime` | boolean | If true, this vegetation is associated with slime. | `false` |
| `is_part_of_magic` | boolean | If true, this vegetation is associated with magic. | `false` |
| `is_part_of_light` | boolean | If true, this vegetation is associated with light. | `false` |
| `is_part_of_darkness` | boolean | If true, this vegetation is associated with darkness. | `false` |
| `is_part_of_healing` | boolean | If true, this vegetation is associated with healing. | `false` |
| `is_part_of_damage` | boolean | If true, this vegetation is associated with damage. | `false` |
| `is_part_of_explosion` | boolean | If true, this vegetation is associated with explosions. | `false` |
| `is_part_of_food` | boolean | If true, this vegetation is associated with food. | `false` |
| `is_part_of_drink` | boolean | If true, this vegetation is associated with drink. | `false` |
| `is_part_of_medicine` | boolean | If true, this vegetation is associated with medicine. | `false` |
| `is_part_of_tool` | boolean | If true, this vegetation is associated with tools. | `false` |
| `is_part_of_weapon` | boolean | If true, this vegetation is associated with weapons. | `false` |
| `is_part_of_armor` | boolean | If true, this vegetation is associated with armor. | `false` |
| `is_part_of_accessory` | boolean | If true, this vegetation is associated with accessories. | `false` |
| `is_part_of_material` | boolean | If true, this vegetation is associated with materials. | `false` |
| `is_part_of_gem` | boolean | If true, this vegetation is associated with gems. | `false` |
| `is_part_of_ore` | boolean | If true, this vegetation is associated with ores. | `false` |
| `is_part_of_metal` | boolean | If true, this vegetation is associated with metals. | `false` |
| `is_part_of_wood` | boolean | If true, this vegetation is associated with wood. | `false` |
| `is_part_of_stone` | boolean | If true, this vegetation is associated with stone. | `false` |
| `is_part_of_plant` | boolean | If true, this vegetation is associated with plants. | `false` |
| `is_part_of_animal` | boolean | If true, this vegetation is associated with animals. | `false` |
| `is_part_of_fungus` | boolean | If true, this vegetation is associated with fungi. | `false` |
| `is_part_of_insect` | boolean | If true, this vegetation is associated with insects. | `false` |
| `is_part_of_fish` | boolean | If true, this vegetation is associated with fish. | `false` |
| `is_part_of_bird` | boolean | If true, this vegetation is associated with birds. | `false` |
| `is_part_of_mammal` | boolean | If true, this vegetation is associated with mammals. | `false` |
| `is_part_of_reptile` | boolean | If true, this vegetation is associated with reptiles. | `false` |
| `is_part_of_amphibian` | boolean | If true, this vegetation is associated with amphibians. | `false` |
| `is_part_of_undead` | boolean | If true, this vegetation is associated with the undead. | `false` |
| `is_part_of_construct` | boolean | If true, this vegetation is associated with constructs. | `false` |
| `is_part_of_elemental` | boolean | If true, this vegetation is associated with elementals. | `false` |
| `is_part_of_ghost` | boolean | If true, this vegetation is associated with ghosts. | `false` |
| `is_part_of_spirit` | boolean | If true, this vegetation is associated with spirits. | `false` |
| `is_part_of_demon` | boolean | If true, this vegetation is associated with demons. | `false` |
| `is_part_of_angel` | boolean | If true, this vegetation is associated with angels. | `false` |
| `is_part_of_god` | boolean | If true, this vegetation is associated with gods. | `false` |
| `is_part_of_player` | boolean | If true, this vegetation is associated with the player. | `false` |
| `is_part_of_enemy` | boolean | If true, this vegetation is associated with enemies. | `false` |
| `is_part_of_ally` | boolean | If true, this vegetation is associated with allies. | `false` |
| `is_part_of_neutral` | boolean | If true, this vegetation is associated with neutral entities. | `false` |
| `is_part_of_item` | boolean | If true, this vegetation is associated with items. | `false` |
| `is_part_of_structure` | boolean | If true, this vegetation is associated with structures. | `false` |
| `is_part_of_terrain` | boolean | If true, this vegetation is associated with terrain. | `false` |
| `is_part_of_environment` | boolean | If true, this vegetation is associated with the environment. | `false` |
| `is_part_of_world` | boolean | If true, this vegetation is associated with the world. | `false` |
| `is_part_of_game` | boolean | If true, this vegetation is associated with the game. | `false` |
| `is_part_of_mod` | boolean | If true, this vegetation is associated with mods. | `false` |
| `is_part_of_script` | boolean | If true, this vegetation is associated with scripts. | `false` |
| `is_part_of_component` | boolean | If true, this vegetation is associated with components. | `false` |
| `is_part_of_entity` | boolean | If true, this vegetation is associated with entities. | `false` |
| `is_part_of_scene` | boolean | If true, this vegetation is associated with scenes. | `false` |
| `is_part_of_level` | boolean | If true, this vegetation is associated with levels. | `false` |
| `is_part_of_biome` | boolean | If true, this vegetation is associated with biomes. | `true` |
| `is_part_of_cave` | boolean | If true, this vegetation is associated with caves. | `false` |
| `is_part_of_surface` | boolean | If true, this vegetation is associated with the surface. | `false` |
| `is_part_of_underground` | boolean | If true, this vegetation is associated with underground areas. | `false` |
| `is_part_of_wasteland` | boolean | If true, this vegetation is associated with wastelands. | `false` |
| `is_part_of_snowy` | boolean | If true, this vegetation is associated with snowy areas. | `false` |
| `is_part_of_desert` | boolean | If true, this vegetation is associated with desert areas. | `false` |
| `is_part_of_swamp` | boolean | If true, this vegetation is associated with swamp areas. | `false` |
| `is_part_of_forest` | boolean | If true, this vegetation is associated with forest areas. | `false` |
| `is_part_of_jungle` | boolean | If true, this vegetation is associated with jungle areas. | `false` |
| `is_part_of_fungal` | boolean | If true, this vegetation is associated with fungal areas. | `false` |
| `is_part_of_hell` | boolean | If true, this vegetation is associated with hell areas. | `false` |
| `is_part_of_crystal` | boolean | If true, this vegetation is associated with crystal areas. | `false` |
| `is_part_of_cursed` | boolean | If true, this vegetation is associated with cursed areas. | `false` |
| `is_part_of_toxic` | boolean | If true, this vegetation is associated with toxic areas. | `false` |
| `is_part_of_acidic` | boolean | If true, this vegetation is associated with acidic areas. | `false` |
| `is_part_of_lava` | boolean | If true, this vegetation is associated with lava areas. | `false` |
| `is_part_of_water` | boolean | If true, this vegetation is associated with water. | `false` |
| `is_part_of_air` | boolean | If true, this vegetation is associated with air. | `false` |
| `is_part_of_earth` | boolean | If true, this vegetation is associated with earth. | `false` |
| `is_part_of_fire` | boolean | If true, this vegetation is associated with fire. | `false` |
| `is_part_of_ice` | boolean | If true, this vegetation is associated with ice. | `false` |
| `is_part_of_poison` | boolean | If true, this vegetation is associated with poison. | `false` |
| `is_part_of_electricity` | boolean | If true, this vegetation is associated with electricity. | `false` |
| `is_part_of_blood` | boolean | If true, this vegetation is associated with blood. | `false` |
| `is_part_of_oil` | boolean | If true, this vegetation is associated with oil. | `false` |
| `is_part_of_slime` | boolean | If true, this vegetation is associated with slime. | `false` |
| `is_part_of_magic` | boolean | If true, this vegetation is associated with magic. | `false` |
| `is_part_of_light` | boolean | If true, this vegetation is associated with light. | `false` |
| `is_part_of_darkness` | boolean | If true, this vegetation is associated with darkness. | `false` |
| `is_part_of_healing` | boolean | If true, this vegetation is associated with healing. | `false` |
| `is_part_of_damage` | boolean | If true, this vegetation is associated with damage. | `false` |
| `is_part_of_explosion` | boolean | If true, this vegetation is associated with explosions. | `false` |
| `is_part_of_food` | boolean | If true, this vegetation is associated with food. | `false` |
| `is_part_of_drink` | boolean | If true, this vegetation is associated with drink. | `false` |
| `is_part_of_medicine` | boolean | If true, this vegetation is associated with medicine. | `false` |
| `is_part_of_tool` | boolean | If true, this vegetation is associated with tools. | `false` |
| `is_part_of_weapon` | boolean | If true, this vegetation is associated with weapons. | `false` |
| `is_part_of_armor` | boolean | If true, this vegetation is associated with armor. | `false` |
| `is_part_of_accessory` | boolean | If true, this vegetation is associated with accessories. | `false` |
| `is_part_of_material` | boolean | If true, this vegetation is associated with materials. | `false` |
| `is_part_of_gem` | boolean | If true, this vegetation is associated with gems. | `false` |
| `is_part_of_ore` | boolean | If true, this vegetation is associated with ores. | `false` |
| `is_part_of_metal` | boolean | If true, this vegetation is associated with metals. | `false` |
| `is_part_of_wood` | boolean | If true, this vegetation is associated with wood. | `false` |
| `is_part_of_stone` | boolean | If true, this vegetation is associated with stone. | `false` |
| `is_part_of_plant` | boolean | If true, this vegetation is associated with plants. | `false` |
| `is_part_of_animal` | boolean | If true, this vegetation is associated with animals. | `false` |
| `is_part_of_fungus` | boolean | If true, this vegetation is associated with fungi. | `false` |
| `is_part_of_insect` | boolean | If true, this vegetation is associated with insects. | `false` |
| `is_part_of_fish` | boolean | If true, this vegetation is associated with fish. | `false` |
| `is_part_of_bird` | boolean | If true, this vegetation is associated with birds. | `false` |
| `is_part_of_mammal` | boolean | If true, this vegetation is associated with mammals. | `false` |
| `is_part_of_reptile` | boolean | If true, this vegetation is associated with reptiles. | `false` |
| `is_part_of_amphibian` | boolean | If true, this vegetation is associated with amphibians. | `false` |
| `is_part_of_undead` | boolean | If true, this vegetation is associated with the undead. | `false` |
| `is_part_of_construct` | boolean | If true, this vegetation is associated with constructs. | `false` |
| `is_part_of_elemental` | boolean | If true, this vegetation is associated with elementals. | `false` |
| `is_part_of_ghost` | boolean | If true, this vegetation is associated with ghosts. | `false` |
| `is_part_of_spirit` | boolean | If true, this vegetation is associated with spirits. | `false` |
| `is_part_of_demon` | boolean | If true, this vegetation is associated with demons. | `false` |
| `is_part_of_angel` | boolean | If true, this vegetation is associated with angels. | `false` |
| `is_part_of_god` | boolean | If true, this vegetation is associated with gods. | `false` |
| `is_part_of_player` | boolean | If true, this vegetation is associated with the player. | `false` |
| `is_part_of_enemy` | boolean | If true, this vegetation is associated with enemies. | `false` |
| `is_part_of_ally` | boolean | If true, this vegetation is associated with allies. | `false` |
| `is_part_of_neutral` | boolean | If true, this vegetation is associated with neutral entities. | `false` |
| `is_part_of_item` | boolean | If true, this vegetation is associated with items. | `false` |
| `is_part_of_structure` | boolean | If true, this vegetation is associated with structures. | `false` |
| `is_part_of_terrain` | boolean | If true, this vegetation is associated with terrain. | `false` |
| `is_part_of_environment` | boolean | If true, this vegetation is associated with the environment. | `false` |
| `is_part_of_world` | boolean | If true, this vegetation is associated with the world. | `false` |
| `is_part_of_game` | boolean | If true, this vegetation is associated with the game. | `false` |
| `is_part_of_mod` | boolean | If true, this vegetation is associated with mods. | `false` |
| `is_part_of_script` | boolean | If true, this vegetation is associated with scripts. | `false` |
| `is_part_of_component` | boolean | If true, this vegetation is associated with components. | `false` |
| `is_part_of_entity` | boolean | If true, this vegetation is associated with entities. | `false` |
| `is_part_of_scene` | boolean | If true, this vegetation is associated with scenes. | `false` |
| `is_part_of_level` | boolean | If true, this vegetation is associated with levels. | `false` |
| `is_part_of_biome` | boolean | If true, this vegetation is associated with biomes. | `true` |
| `is_part_of_cave` | boolean | If true, this vegetation is associated with caves. | `false` |
| `is_part_of_surface` | boolean | If true, this vegetation is associated with the surface. | `false` |
| `is_part_of_underground` | boolean | If true, this vegetation is associated with underground areas. | `false` |
| `is_part_of_wasteland` | boolean | If true, this vegetation is associated with wastelands. | `false` |
| `is_part_of_snowy` | boolean | If true, this vegetation is associated with snowy areas. | `false` |
| `is_part_of_desert` | boolean | If true, this vegetation is associated with desert areas. | `false` |
| `is_part_of_swamp` | boolean | If true, this vegetation is associated with swamp areas. | `false` |
| `is_part_of_forest` | boolean | If true, this vegetation is associated with forest areas. | `false` |
| `is_part_of_jungle` | boolean | If true, this vegetation is associated with jungle areas. | `false` |
| `is_part_of_fungal` | boolean | If true, this vegetation is associated with fungal areas. | `false` |
| `is_part_of_hell` | boolean | If true, this vegetation is associated with hell areas. | `false` |
| `is_part_of_crystal` | boolean | If true, this vegetation is associated with crystal areas. | `false` |
| `is_part_of_cursed` | boolean | If true, this vegetation is associated with cursed areas. | `false` |
| `is_part_of_toxic` | boolean | If true, this vegetation is associated with toxic areas. | `false` |
| `is_part_of_acidic` | boolean | If true, this vegetation is associated with acidic areas. | `false` |
| `is_part_of_lava` | boolean | If true, this vegetation is associated with lava areas. | `false` |
| `is_part_of_water` | boolean | If true, this vegetation is associated with water. | `false` |
| `is_part_of_air` | boolean | If true, this vegetation is associated with air. | `false` |
| `is_part_of_earth` | boolean | If true, this vegetation is associated with earth. | `false` |
| `is_part_of_fire` | boolean | If true, this vegetation is associated with fire. | `false` |
| `is_part_of_ice` | boolean | If true, this vegetation is associated with ice. | `false` |
| `is_part_of_poison` | boolean | If true, this vegetation is associated with poison. | `false` |
| `is_part_of_electricity` | boolean | If true, this vegetation is associated with electricity. | `false` |
| `is_part_of_blood` | boolean | If true, this vegetation is associated with blood. | `false` |
| `is_part_of_oil` | boolean | If true, this vegetation is associated with oil. | `false` |
| `is_part_of_slime` | boolean | If true, this vegetation is associated with slime. | `false` |
| `is_part_of_magic` | boolean | If true, this vegetation is associated with magic. | `false` |
| `is_part_of_light` | boolean | If true, this vegetation is associated with light. | `false` |
| `is_part_of_darkness` | boolean | If true, this vegetation is associated with darkness. | `false` |
| `is_part_of_healing` | boolean | If true, this vegetation is associated with healing. | `false` |
| `is_part_of_damage` | boolean | If true, this vegetation is associated with damage. | `false` |
| `is_part_of_explosion` | boolean | If true, this vegetation is associated with explosions. | `false` |
| `is_part_of_food` | boolean | If true, this vegetation is associated with food. | `false` |
| `is_part_of_drink` | boolean | If true, this vegetation is associated with drink. | `false` |
| `is_part_of_medicine` | boolean | If true, this vegetation is associated with medicine. | `false` |
| `is_part_of_tool` | boolean | If true, this vegetation is associated with tools. | `false` |
| `is_part_of_weapon` | boolean | If true, this vegetation is associated with weapons. | `false` |
| `is_part_of_armor` | boolean | If true, this vegetation is associated with armor. | `false` |
| `is_part_of_accessory` | boolean | If true, this vegetation is associated with accessories. | `false` |
| `is_part_of_material` | boolean | If true, this vegetation is associated with materials. | `false` |
| `is_part_of_gem` | boolean | If true, this vegetation is associated with gems. | `false` |
| `is_part_of_ore` | boolean | If true, this vegetation is associated with ores. | `false` |
| `is_part_of_metal` | boolean | If true, this vegetation is associated with metals. | `false` |
| `is_part_of_wood` | boolean | If true, this vegetation is associated with wood. | `false` |
| `is_part_of_stone` | boolean | If true, this vegetation is associated with stone. | `false` |
| `is_part_of_plant` | boolean | If true, this vegetation is associated with plants. | `false` |
| `is_part_of_animal` | boolean | If true, this vegetation is associated with animals. | `false` |
| `is_part_of_fungus` | boolean | If true, this vegetation is associated with fungi. | `false` |
| `is_part_of_insect` | boolean | If true, this vegetation is associated with insects. | `false` |
| `is_part_of_fish` | boolean | If true, this vegetation is associated with fish. | `false` |
| `is_part_of_bird` | boolean | If true, this vegetation is associated with birds. | `false` |
| `is_part_of_mammal` | boolean | If true, this vegetation is associated with mammals. | `false` |
| `is_part_of_reptile` | boolean | If true, this vegetation is associated with reptiles. | `false` |
| `is_part_of_amphibian` | boolean | If true, this vegetation is associated with amphibians. | `false` |
| `is_part_of_undead` | boolean | If true, this vegetation is associated with the undead. | `false` |
| `is_part_of_construct` | boolean | If true, this vegetation is associated with constructs. | `false` |
| `is_part_of_elemental` | boolean | If true, this vegetation is associated with elementals. | `false` |
| `is_part_of_ghost` | boolean | If true, this vegetation is associated with ghosts. | `false` |
| `is_part_of_spirit` | boolean | If true, this vegetation is associated with spirits. | `false` |
| `is_part_of_demon` | boolean | If true, this vegetation is associated with demons. | `false` |
| `is_part_of_angel` | boolean | If true, this vegetation is associated with angels. | `false` |
| `is_part_of_god` | boolean | If true, this vegetation is associated with gods. | `false` |
| `is_part_of_player` | boolean | If true, this vegetation is associated with the player. | `false` |
| `is_part_of_enemy` | boolean | If true, this vegetation is associated with enemies. | `false` |
| `is_part_of_ally` | boolean | If true, this vegetation is associated with allies. | `false` |
| `is_part_of_neutral` | boolean | If true, this vegetation is associated with neutral entities. | `false` |
| `is_part_of_item` | boolean | If true, this vegetation is associated with items. | `false` |
| `is_part_of_structure` | boolean | If true, this vegetation is associated with structures. | `false` |
| `is_part_of_terrain` | boolean | If true, this vegetation is associated with terrain. | `false` |
| `is_part_of_environment` | boolean | If true, this vegetation is associated with the environment. | `false` |
| `is_part_of_world` | boolean | If true, this vegetation is associated with the world. | `false` |
| `is_part_of_game` | boolean | If true, this vegetation is associated with the game. | `false` |
| `is_part_of_mod` | boolean | If true, this vegetation is associated with mods. | `false` |
| `is_part_of_script` | boolean | If true, this vegetation is associated with scripts. | `false` |
| `is_part_of_component` | boolean | If true, this vegetation is associated with components. | `false` |
| `is_part_of_entity` | boolean | If true, this vegetation is associated with entities. | `false` |
| `is_part_of_scene` | boolean | If true, this vegetation is associated with scenes. | `false` |
| `is_part_of_level` | boolean | If true, this vegetation is associated with levels. | `false` |
| `is_part_of_biome` | boolean | If true, this vegetation is associated with biomes. | `true` |
| `is_part_of_cave` | boolean | If true, this vegetation is associated with caves. | `false` |
| `is_part_of_surface` | boolean | If true, this vegetation is associated with the surface. | `false` |
| `is_part_of_underground` | boolean | If true, this vegetation is associated with underground areas. | `false` |
| `is_part_of_wasteland` | boolean | If true, this vegetation is associated with wastelands. | `false` |
| `is_part_of_snowy` | boolean | If true, this vegetation is associated with snowy areas. | `false` |
| `is_part_of_desert` | boolean | If true, this vegetation is associated with desert areas. | `false` |
| `is_part_of_swamp` | boolean | If true, this vegetation is associated with swamp areas. | `false` |
| `is_part_of_forest` | boolean | If true, this vegetation is associated with forest areas. | `false` |
| `is_part_of_jungle` | boolean | If true, this vegetation is associated with jungle areas. | `false` |
| `is_part_of_fungal` | boolean | If true, this vegetation is associated with fungal areas. | `false` |
| `is_part_of_hell` | boolean | If true, this vegetation is associated with hell areas. | `false` |
| `is_part_of_crystal` | boolean | If true, this vegetation is associated with crystal areas. | `false` |
| `is_part_of_cursed` | boolean | If true, this vegetation is associated with cursed areas. | `false` |
| `is_part_of_toxic` | boolean | If true, this vegetation is associated with toxic areas. | `false` |
| `is_part_of_acidic` | boolean | If true, this vegetation is associated with acidic areas. | `false` |
| `is_part_of_lava` | boolean | If true, this vegetation is associated with lava areas. | `false` |
| `is_part_of_water` | boolean | If true, this vegetation is associated with water. | `false` |
| `is_part_of_air` | boolean | If true, this vegetation is associated with air. | `false` |
| `is_part_of_earth` | boolean | If true, this vegetation is associated with earth. | `false` |
| `is_part_of_fire` | boolean | If true, this vegetation is associated with fire. | `false` |
| `is_part_of_ice` | boolean | If true, this vegetation is associated with ice. | `false` |
| `is_part_of_poison` | boolean | If true, this vegetation is associated with poison. | `false` |
| `is_part_of_electricity` | boolean | If true, this vegetation is associated with electricity. | `false` |
| `is_part_of_blood` | boolean | If true, this vegetation is associated with blood. | `false` |
| `is_part_of_oil` | boolean | If true, this vegetation is associated with oil. | `false` |
| `is_part_of_slime` | boolean | If true, this vegetation is associated with slime. | `false` |
| `is_part_of_magic` | boolean | If true, this vegetation is associated with magic. | `false` |
| `is_part_of_light` | boolean | If true, this vegetation is associated with light. | `false` |
| `is_part_of_darkness` | boolean | If true, this vegetation is associated with darkness. | `false` |
| `is_part_of_healing` | boolean | If true, this vegetation is associated with healing. | `false` |
| `is_part_of_damage` | boolean | If true, this vegetation is associated with damage. | `false` |
| `is_part_of_explosion` | boolean | If true, this vegetation is associated with explosions. | `false` |
| `is_part_of_food` | boolean | If true, this vegetation is associated with food. | `false` |
| `is_part_of_drink` | boolean | If true, this vegetation is associated with drink. | `false` |
| `is_part_of_medicine` | boolean | If true, this vegetation is associated with medicine. | `false` |
| `is_part_of_tool` | boolean | If true, this vegetation is associated with tools. | `false` |
| `is_part_of_weapon` | boolean | If true, this vegetation is associated with weapons. | `false` |
| `is_part_of_armor` | boolean | If true, this vegetation is associated with armor. | `false` |
| `is_part_of_accessory` | boolean | If true, this vegetation is associated with accessories. | `false` |
| `is_part_of_material` | boolean | If true, this vegetation is associated with materials. | `false` |
| `is_part_of_gem` | boolean | If true, this vegetation is associated with gems. | `false` |
| `is_part_of_ore` | boolean | If true, this vegetation is associated with ores. | `false` |
| `is_part_of_metal` | boolean | If true, this vegetation is associated with metals. | `false` |
| `is_part_of_wood` | boolean | If true, this vegetation is associated with wood. | `false` |
| `is_part_of_stone` | boolean | If true, this vegetation is associated with stone. | `false` |
| `is_part_of_plant` | boolean | If true, this vegetation is associated with plants. | `false` |
| `is_part_of_animal` | boolean | If true, this vegetation is associated with animals. | `false` |
| `is_part_of_fungus` | boolean | If true, this vegetation is associated with fungi. | `false` |
| `is_part_of_insect` | boolean | If true, this vegetation is associated with insects. | `false` |
| `is_part_of_fish` | boolean | If true, this vegetation is associated with fish. | `false` |
| `is_part_of_bird` | boolean | If true, this vegetation is associated with birds. | `false` |
| `is_part_of_mammal` | boolean | If true, this vegetation is associated with mammals. | `false` |
| `is_part_of_reptile` | boolean | If true, this vegetation is associated with reptiles. | `false` |
| `is_part_of_amphibian` | boolean | If true, this vegetation is associated with amphibians. | `false` |
| `is_part_of_undead` | boolean | If true, this vegetation is associated with the undead. | `false` |
| `is_part_of_construct` | boolean | If true, this vegetation is associated with constructs. | `false` |
| `is_part_of_elemental` | boolean | If true, this vegetation is associated with elementals. | `false` |
| `is_part_of_ghost` | boolean | If true, this vegetation is associated with ghosts. | `false` |
| `is_part_of_spirit` | boolean | If true, this vegetation is associated with spirits. | `false` |
| `is_part_of_demon` | boolean | If true, this vegetation is associated with demons. | `false` |
| `is_part_of_angel` | boolean | If true, this vegetation is associated with angels. | `false` |
| `is_part_of_god` | boolean | If true, this vegetation is associated with gods. | `false` |
| `is_part_of_player` | boolean | If true, this vegetation is associated with the player. | `false` |
| `is_part_of_enemy` | boolean | If true, this vegetation is associated with enemies. | `false` |
| `is_part_of_ally` | boolean | If true, this vegetation is associated with allies. | `false` |
| `is_part_of_neutral` | boolean | If true, this vegetation is associated with neutral entities. | `false` |
| `is_part_of_item` | boolean | If true, this vegetation is associated with items. | `false` |
| `is_part_of_structure` | boolean | If true, this vegetation is associated with structures. | `false` |
| `is_part_of_terrain` | boolean | If true, this vegetation is associated with terrain. | `false` |
| `is_part_of_environment` | boolean | If true, this vegetation is associated with the environment. | `false` |
| `is_part_of_world` | boolean | If true, this vegetation is associated with the world. | `false` |
| `is_part_of_game` | boolean | If true, this vegetation is associated with the game. | `false` |
| `is_part_of_mod` | boolean | If true, this vegetation is associated with mods. | `false` |
| `is_part_of_script` | boolean | If true, this vegetation is associated with scripts. | `false` |
| `is_part_of_component` | boolean | If true, this vegetation is associated with components. | `false` |
| `is_part_of_entity` | boolean | If true, this vegetation is associated with entities. | `false` |
| `is_part_of_scene` | boolean | If true, this vegetation is associated with scenes. | `false` |
| `is_part_of_level` | boolean | If true, this vegetation is associated with levels. | `false` |
| `is_part_of_biome` | boolean | If true, this vegetation is associated with biomes. | `true` |
| `is_part_of_cave` | boolean | If true, this vegetation is associated with caves. | `false` |
| `is_part_of_surface` | boolean | If true, this vegetation is associated with the surface. | `false` |
| `is_part_of_underground` | boolean | If true, this vegetation is associated with underground areas. | `false` |
| `is_part_of_wasteland` | boolean | If true, this vegetation is associated with wastelands. | `false` |
| `is_part_of_snowy` | boolean | If true, this vegetation is associated with snowy areas. | `false` |
| `is_part_of_desert` | boolean | If true, this vegetation is associated with desert areas. | `false` |
| `is_part_of_swamp` | boolean | If true, this vegetation is associated with swamp areas. | `false` |
| `is_part_of_forest` | boolean | If true, this vegetation is associated with forest areas. | `false` |
| `is_part_of_jungle` | boolean | If true, this vegetation is associated with jungle areas. | `false` |
| `is_part_of_fungal` | boolean | If true, this vegetation is associated with fungal areas. | `false` |
| `is_part_of_hell` | boolean | If true, this vegetation is associated with hell areas. | `false` |
| `is_part_of_crystal` | boolean | If true, this vegetation is associated with crystal areas. | `false` |
| `is_part_of_cursed` | boolean | If true, this vegetation is associated with cursed areas. | `false` |
| `is_part_of_toxic` | boolean | If true, this vegetation is associated with toxic areas. | `false` |
| `is_part_of_acidic` | boolean | If true, this vegetation is associated with acidic areas. | `false` |
| `is_part_of_lava` | boolean | If true, this vegetation is associated with lava areas. | `false` |
| `is_part_of_water` | boolean | If true, this vegetation is associated with water. | `false` |
| `is_part_of_air` | boolean | If true, this vegetation is associated with air. | `false` |
| `is_part_of_earth` | boolean | If true, this vegetation is associated with earth. | `false` |
| `is_part_of_fire` | boolean | If true, this vegetation is associated with fire. | `false` |
| `is_part_of_ice` | boolean | If true, this vegetation is associated with ice. | `false` |
| `is_part_of_poison` | boolean | If true, this vegetation is associated with poison. | `false` |
| `is_part_of_electricity` | boolean | If true, this vegetation is associated with electricity. | `false` |
| `is_part_of_blood` | boolean | If true, this vegetation is associated with blood. | `false` |
| `is_part_of_oil` | boolean | If true, this vegetation is associated with oil. | `false` |
| `is_part_of_slime` | boolean | If true, this vegetation is associated with slime. | `false` |
| `is_part_of_magic` | boolean | If true, this vegetation is associated with magic. | `false` |
| `is_part_of_light` | boolean | If true, this vegetation is associated with light. | `false` |
| `is_part_of_darkness` | boolean | If true, this vegetation is associated with darkness. | `false` |
| `is_part_of_healing` | boolean | If true, this vegetation is associated with healing. | `false` |
| `is_part_of_damage` | boolean | If true, this vegetation is associated with damage. | `false` |
| `is_part_of_explosion` | boolean | If true, this vegetation is associated with explosions. | `false` |
| `is_part_of_food` | boolean | If true, this vegetation is associated with food. | `false` |
| `is_part_of_drink` | boolean | If true, this vegetation is associated with drink. | `false` |
| `is_part_of_medicine` | boolean | If true, this vegetation is associated with medicine. | `false` |
| `is_part_of_tool` | boolean | If true, this vegetation is associated with tools. | `false` |
| `is_part_of_weapon` | boolean | If true, this vegetation is associated with weapons. | `false` |
| `is_part_of_armor` | boolean | If true, this vegetation is associated with armor. | `false` |
| `is_part_of_accessory` | boolean | If true, this vegetation is associated with accessories. | `false` |
| `is_part_of_material` | boolean | If true, this vegetation is associated with materials. | `false` |
| `is_part_of_gem` | boolean | If true, this vegetation is associated with gems. | `false` |
| `is_part_of_ore` | boolean | If true, this vegetation is associated with ores. | `false` |
| `is_part_of_metal` | boolean | If true, this vegetation is associated with metals. | `false` |
| `is_part_of_wood` | boolean | If true, this vegetation is associated with wood. | `false` |
| `is_part_of_stone` | boolean | If true, this vegetation is associated with stone. | `false` |
| `is_part_of_plant` | boolean | If true, this vegetation is associated with plants. | `false` |
| `is_part_of_animal` | boolean | If true, this vegetation is associated with animals. | `false` |
| `is_part_of_fungus` | boolean | If true, this vegetation is associated with fungi. | `false` |
| `is_part_of_insect` | boolean | If true, this vegetation is associated with insects. | `false` |
| `is_part_of_fish` | boolean | If true, this vegetation is associated with fish. | `false` |
| `is_part_of_bird` | boolean | If true, this vegetation is associated with birds. | `false` |
| `is_part_of_mammal` | boolean | If true, this vegetation is associated with mammals. | `false` |
| `is_part_of_reptile` | boolean | If true, this vegetation is associated with reptiles. | `false` |
| `is_part_of_amphibian` | boolean | If true, this vegetation is associated with amphibians. | `false` |
| `is_part_of_undead` | boolean | If true, this vegetation is associated with the undead. | `false` |
| `is_part_of_construct` | boolean | If true, this vegetation is associated with constructs. | `false` |
| `is_part_of_elemental` | boolean | If true, this vegetation is associated with elementals. | `false` |
| `is_part_of_ghost` | boolean | If true, this vegetation is associated with ghosts. | `false` |
| `is_part_of_spirit` | boolean | If true, this vegetation is associated with spirits. | `false` |
| `is_part_of_demon` | boolean | If true, this vegetation is associated with demons. | `false` |
| `is_part_of_angel` | boolean | If true, this vegetation is associated with angels. | `false` |
| `is_part_of_god` | boolean | If true, this vegetation is associated with gods. | `false` |
| `is_part_of_player` | boolean | If true, this vegetation is associated with the player. | `false` |
| `is_part_of_enemy` | boolean | If true, this vegetation is associated with enemies. | `false` |
| `is_part_of_ally` | boolean | If true, this vegetation is associated with allies. | `false` |
| `is_part_of_neutral` | boolean | If true, this vegetation is associated with neutral entities. | `false` |
| `is_part_of_item` | boolean | If true, this vegetation is associated with items. | `false` |
| `is_part_of_structure` | boolean | If true, this vegetation is associated with structures. | `false` |
| `is_part_of_terrain` | boolean | If true, this vegetation is associated with terrain. | `false` |
| `is_part_of_environment` | boolean | If true, this vegetation is associated with the environment. | `false` |
| `is_part_of_world` | boolean | If true, this vegetation is associated with the world. | `false` |
| `is_part_of_game` | boolean | If true, this vegetation is associated with the game. | `false` |
| `is_part_of_mod` | boolean | If true, this vegetation is associated with mods. | `false` |
| `is_part_of_script` | boolean | If true, this vegetation is associated with scripts. | `false` |
| `is_part_of_component` | boolean | If true, this vegetation is associated with components. | `false` |
| `is_part_of_entity` | boolean | If true, this vegetation is associated with entities. | `false` |
| `is_part_of_scene` | boolean | If true, this vegetation is associated with scenes. | `false` |
| `is_part_of_level` | boolean | If true, this vegetation is associated with levels. | `false` |
| `is_part_of_biome` | boolean | If true, this vegetation is associated with biomes. | `true` |
| `is_part_of_cave` | boolean | If true, this vegetation is associated with caves. | `false` |
| `is_part_of_surface` | boolean | If true, this vegetation is associated with the surface. | `false` |
| `is_part_of_underground` | boolean | If true, this vegetation is associated with underground areas. | `false` |
| `is_part_of_wasteland` | boolean | If true, this vegetation is associated with wastelands. | `false` |
| `is_part_of_snowy` | boolean | If true, this vegetation is associated with snowy areas. | `false` |
| `is_part_of_desert` | boolean | If true, this vegetation is associated with desert areas. | `false` |
| `is_part_of_swamp` | boolean | If true, this vegetation is associated with swamp areas. | `false` |
| `is_part_of_forest` | boolean | If true, this vegetation is associated with forest areas. | `false` |
| `is_part_of_jungle` | boolean | If true, this vegetation is associated with jungle areas. | `false` |
| `is_part_of_fungal` | boolean | If true, this vegetation is associated with fungal areas. | `false` |
| `is_part_of_hell` | boolean | If true, this vegetation is associated with hell areas. | `false` |
| `is_part_of_crystal` | boolean | If true, this vegetation is associated with crystal areas. | `false` |
| `is_part_of_cursed` | boolean | If true, this vegetation is associated with cursed areas. | `false` |
| `is_part_of_toxic` | boolean | If true, this vegetation is associated with toxic areas. | `false` |
| `is_part_of_acidic` | boolean | If true, this vegetation is associated with acidic areas. | `false` |
| `is_part_of_lava` | boolean | If true, this vegetation is associated with lava areas. | `false` |
| `is_part_of_water` | boolean | If true, this vegetation is associated with water. | `false` |
| `is_part_of_air` | boolean | If true, this vegetation is associated with air. | `false` |
| `is_part_of_earth` | boolean | If true, this vegetation is associated with earth. | `false` |
| `is_part_of_fire` | boolean | If true, this vegetation is associated with fire. | `false` |
| `is_part_of_ice` | boolean | If true, this vegetation is associated with ice. | `false` |
| `is_part_of_poison` | boolean | If true, this vegetation is associated with poison. | `false` |
| `is_part_of_electricity` | boolean | If true, this vegetation is associated with electricity. | `false` |
| `is_part_of_blood` | boolean | If true, this vegetation is associated with blood. | `false` |
| `is_part_of_oil` | boolean | If true, this vegetation is associated with oil. | `false` |
| `is_part_of_slime` | boolean | If true, this vegetation is associated with slime. | `false` |
| `is_part_of_magic` | boolean | If true, this vegetation is associated with magic. | `false` |
| `is_part_of_light` | boolean | If true, this vegetation is associated with light. | `false` |
| `is_part_of_darkness` | boolean | If true, this vegetation is associated with darkness. | `false` |
| `is_part_of_healing` | boolean | If true, this vegetation is associated with healing. | `false` |
| `is_part_of_damage` | boolean | If true, this vegetation is associated with damage. | `false` |
| `is_part_of_explosion` | boolean | If true, this vegetation is associated with explosions. | `false` |
| `is_part_of_food` | boolean | If true, this vegetation is associated with food. | `false` |
| `is_part_of_drink` | boolean | If true, this vegetation is associated with drink. | `false` |
| `is_part_of_medicine` | boolean | If true, this vegetation is associated with medicine. | `false` |
| `is_part_of_tool` | boolean | If true, this vegetation is associated with tools. | `false` |
| `is_part_of_weapon` | boolean | If true, this vegetation is associated with weapons. | `false` |
| `is_part_of_armor` | boolean | If true, this vegetation is associated with armor. | `false` |
| `is_part_of_accessory` | boolean | If true, this vegetation is associated with accessories. | `false` |
| `is_part_of_material` | boolean | If true, this vegetation is associated with materials. | `false` |
| `is_part_of_gem` | boolean | If true, this vegetation is associated with gems. | `false` |
| `is_part_of_ore` | boolean | If true, this vegetation is associated with ores. | `false` |
| `is_part_of_metal` | boolean | If true, this vegetation is associated with metals. | `false` |
| `is_part_of_wood` | boolean | If true, this vegetation is associated with wood. | `false` |
| `is_part_of_stone` | boolean | If true, this vegetation is associated with stone. | `false` |
| `is_part_of_plant` | boolean | If true, this vegetation is associated with plants. | `false` |
| `is_part_of_animal` | boolean | If true, this vegetation is associated with animals. | `false` |
| `is_part_of_fungus` | boolean | If true, this vegetation is associated with fungi. | `false` |
| `is_part_of_insect` | boolean | If true, this vegetation is associated with insects. | `false` |
| `is_part_of_fish` | boolean | If true, this vegetation is associated with fish. | `false` |
| `is_part_of_bird` | boolean | If true, this vegetation is associated with birds. | `false` |
| `is_part_of_mammal` | boolean | If true, this vegetation is associated with mammals. | `false` |
| `is_part_of_reptile` | boolean | If true, this vegetation is associated with reptiles. | `false` |
| `is_part_of_amphibian` | boolean | If true, this vegetation is associated with amphibians. | `false` |
| `is_part_of_undead` | boolean | If true, this vegetation is associated with the undead. | `false` |
| `is_part_of_construct` | boolean | If true, this vegetation is associated with constructs. | `false` |
| `is_part_of_elemental` | boolean | If true, this vegetation is associated with elementals. | `false` |
| `is_part_of_ghost` | boolean | If true, this vegetation is associated with ghosts. | `false` |
| `is_part_of_spirit` | boolean | If true, this vegetation is associated with spirits. | `false` |
| `is_part_of_demon` | boolean | If true, this vegetation is associated with demons. | `false` |
| `is_part_of_angel` | boolean | If true, this vegetation is associated with angels. | `false` |
| `is_part_of_god` | boolean | If true, this vegetation is associated with gods. | `false` |
| `is_part_of_player` | boolean | If true, this vegetation is associated with the player. | `false` |
| `is_part_of_enemy` | boolean | If true, this vegetation is associated with enemies. | `false` |
| `is_part_of_ally` | boolean | If true, this vegetation is associated with allies. | `false` |
| `is_part_of_neutral` | boolean | If true, this vegetation is associated with neutral entities. | `false` |
| `is_part_of_item` | boolean | If true, this vegetation is associated with items. | `false` |
| `is_part_of_structure` | boolean | If true, this vegetation is associated with structures. | `false` |
| `is_part_of_terrain` | boolean | If true, this vegetation is associated with terrain. | `false` |
| `is_part_of_environment` | boolean | If true, this vegetation is associated with the environment. | `false` |
| `is_part_of_world` | boolean | If true, this vegetation is associated with the world. | `false` |
| `is_part_of_game` | boolean | If true, this vegetation is associated with the game. | `false` |
| `is_part_of_mod` | boolean | If true, this vegetation is associated with mods. | `false` |
| `is_part_of_script` | boolean | If true, this vegetation is associated with scripts. | `false` |
| `is_part_of_component` | boolean | If true, this vegetation is associated with components. | `false` |
| `is_part_of_entity` | boolean | If true, this vegetation is associated with entities. | `false` |
| `is_part_of_scene` | boolean | If true, this vegetation is associated with scenes. | `false` |
| `is_part_of_level` | boolean | If true, this vegetation is associated with levels. | `false` |
| `is_part_of_biome` | boolean | If true, this vegetation is associated with biomes. | `true` |
| `is_part_of_cave` | boolean | If true, this vegetation is associated with caves. | `false` |
| `is_part_of_surface` | boolean | If true, this vegetation is associated with the surface. | `false` |
| `is_part_of_underground` | boolean | If true, this vegetation is associated with underground areas. | `false` |
| `is_part_of_wasteland` | boolean | If true, this vegetation is associated with wastelands. | `false` |
| `is_part_of_snowy` | boolean | If true, this vegetation is associated with snowy areas. | `false` |
| `is_part_of_desert` | boolean | If true, this vegetation is associated with desert areas. | `false` |
| `is_part_of_swamp` | boolean | If true, this vegetation is associated with swamp areas. | `false` |
| `is_part_of_forest` | boolean | If true, this vegetation is associated with forest areas. | `false` |
| `is_part_of_jungle` | boolean | If true, this vegetation is associated with jungle areas. | `false` |
| `is_part_of_fungal` | boolean | If true, this vegetation is associated with fungal areas. | `false` |
| `is_part_of_hell` | boolean | If true, this vegetation is associated with hell areas. | `false` |
| `is_part_of_crystal` | boolean | If true, this vegetation is associated with crystal areas. | `false` |
| `is_part_of_cursed` | boolean | If true, this vegetation is associated with cursed areas. | `false` |
| `is_part_of_toxic` | boolean | If true, this vegetation is associated with toxic areas. | `false` |
| `is_part_of_acidic` | boolean | If true, this vegetation is associated with acidic areas. | `false` |
| `is_part_of_lava` | boolean | If true, this vegetation is associated with lava areas. | `false` |
| `is_part_of_water` | boolean | If true, this vegetation is associated with water. | `false` |
| `is_part_of_air` | boolean | If true, this vegetation is associated with air. | `false` |
| `is_part_of_earth` | boolean | If true, this vegetation is associated with earth. | `false` |
| `is_part_of_fire` | boolean | If true, this vegetation is associated with fire. | `false` |
| `is_part_of_ice` | boolean | If true, this vegetation is associated with ice. | `false` |
| `is_part_of_poison` | boolean | If true, this vegetation is associated with poison. | `false` |
| `is_part_of_electricity` | boolean | If true, this vegetation is associated with electricity. | `false` |
| `is_part_of_blood` | boolean | If true, this vegetation is associated with blood. | `false` |
| `is_part_of_oil` | boolean | If true, this vegetation is associated with oil. | `false` |
| `is_part_of_slime` | boolean | If true, this vegetation is associated with slime. | `false` |
| `is_part_of_magic` | boolean | If true, this vegetation is associated with magic. | `false` |
| `is_part_of_light` | boolean | If true, this vegetation is associated with light. | `false` |
| `is_part_of_darkness` | boolean | If true, this vegetation is associated with darkness. | `false` |
| `is_part_of_healing` | boolean | If true, this vegetation is associated with healing. | `false` |
| `is_part_of_damage` | boolean | If true, this vegetation is associated with damage. | `false` |
| `is_part_of_explosion` | boolean | If true, this vegetation is associated with explosions. | `false` |
| `is_part_of_food` | boolean | If true, this vegetation is associated with food. | `false` |
| `is_part_of_drink` | boolean | If true, this vegetation is associated with drink. | `false` |
| `is_part_of_medicine` | boolean | If true, this vegetation is associated with medicine. | `false` |
| `is_part_of_tool` | boolean | If true, this vegetation is associated with tools. | `false` |
| `is_part_of_weapon` | boolean | If true, this vegetation is associated with weapons. | `false` |
| `is_part_of_armor` | boolean | If true, this vegetation is associated with armor. | `false` |
| `is_part_of_accessory` | boolean | If true, this vegetation is associated with accessories. | `false` |
| `is_part_of_material` | boolean | If true, this vegetation is associated with materials. | `false` |
| `is_part_of_gem` | boolean | If true, this vegetation is associated with gems. | `false` |
| `is_part_of_ore` | boolean | If true, this vegetation is associated with ores. | `false` |
| `is_part_of_metal` | boolean | If true, this vegetation is associated with metals. | `false` |
| `is_part_of_wood` | boolean | If true, this vegetation is associated with wood. | `false` |
| `is_part_of_stone` | boolean | If true, this vegetation is associated with stone. | `false` |
| `is_part_of_plant` | boolean | If true, this vegetation is associated with plants. | `false` |
| `is_part_of_animal` | boolean | If true, this vegetation is associated with animals. | `false` |
| `is_part_of_fungus` | boolean | If true, this vegetation is associated with fungi. | `false` |
| `is_part_of_insect` | boolean | If true, this vegetation is associated with insects. | `false` |
| `is_part_of_fish` | boolean | If true, this vegetation is associated with fish. | `false` |
| `is_part_of_bird` | boolean | If true, this vegetation is associated with birds. | `false` |
| `is_part_of_mammal` | boolean | If true, this vegetation is associated with mammals. | `false` |
| `is_part_of_reptile` | boolean | If true, this vegetation is associated with reptiles. | `false` |
| `is_part_of_amphibian` | boolean | If true, this vegetation is associated with amphibians. | `false` |
| `is_part_of_undead` | boolean | If true, this vegetation is associated with the undead. | `false` |
| `is_part_of_construct` | boolean | If true, this vegetation is associated with constructs. | `false` |
| `is_part_of_elemental` | boolean | If true, this vegetation is associated with elementals. | `false` |
| `is_part_of_ghost` | boolean | If true, this vegetation is associated with ghosts. | `false` |
| `is_part_of_spirit` | boolean | If true, this vegetation is associated with spirits. | `false` |
| `is_part_of_demon` | boolean | If true, this vegetation is associated with demons. | `false` |
| `is_part_of_angel` | boolean | If true, this vegetation is associated with angels. | `false` |
| `is_part_of_god` | boolean | If true, this vegetation is associated with gods. | `false` |
| `is_part_of_player` | boolean | If true, this vegetation is associated with the player. | `false` |
| `is_part_of_enemy` | boolean | If true, this vegetation is associated with enemies. | `false` |
| `is_part_of_ally` | boolean | If true, this vegetation is associated with allies. | `false` |
| `is_part_of_neutral` | boolean | If true, this vegetation is associated with neutral entities. | `false` |
| `is_part_of_item` | boolean | If true, this vegetation is associated with items. | `false` |
| `is_part_of_structure` | boolean | If true, this vegetation is associated with structures. | `false` |
| `is_part_of_terrain` | boolean | If true, this vegetation is associated with terrain. | `false` |
| `is_part_of_environment` | boolean | If true, this vegetation is associated with the environment. | `false` |
| `is_part_of_world` | boolean | If true, this vegetation is associated with the world. | `false` |
| `is_part_of_game` | boolean | If true, this vegetation is associated with the game. | `false` |
| `is_part_of_mod` | boolean | If true, this vegetation is associated with mods. | `false` |
| `is_part_of_script` | boolean | If true, this vegetation is associated with scripts. | `false` |
| `is_part_of_component` | boolean | If true, this vegetation is associated with components. | `false` |
| `is_part_of_entity` | boolean | If true, this vegetation is associated with entities. | `false` |
| `is_part_of_scene` | boolean | If true, this vegetation is associated with scenes. | `false` |
| `is_part_of_level` | boolean | If true, this vegetation is associated with levels. | `false` |
| `is_part_of_biome` | boolean | If true, this vegetation is associated with biomes. | `true` |
| `is_part_of_cave` | boolean | If true, this vegetation is associated with caves. | `false` |
| `is_part_of_surface` | boolean | If true, this vegetation is associated with the surface. | `false` |
| `is_part_of_underground` | boolean | If true, this vegetation is associated with underground areas. | `false` |
| `is_part_of_wasteland` | boolean | If true, this vegetation is associated with wastelands. | `false` |
| `is_part_of_snowy` | boolean | If true, this vegetation is associated with snowy areas. | `false` |
| `is_part_of_desert` | boolean | If true, this vegetation is associated with desert areas. | `false` |
| `is_part_of_swamp` | boolean | If true, this vegetation is associated with swamp areas. | `false` |
| `is_part_of_forest` | boolean | If true, this vegetation is associated with forest areas. | `false` |
| `is_part_of_jungle` | boolean | If true, this vegetation is associated with jungle areas. | `false` |
| `is_part_of_fungal` | boolean | If true, this vegetation is associated with fungal areas. | `false` |
| `is_part_of_hell` | boolean | If true, this vegetation is associated with hell areas. | `false` |
| `is_part_of_crystal` | boolean | If true, this vegetation is associated with crystal areas. | `false` |
| `is_part_of_cursed` | boolean | If true, this vegetation is associated with cursed areas. | `false` |
| `is_part_of_toxic` | boolean | If true, this vegetation is associated with toxic areas. | `false` |
| `is_part_of_acidic` | boolean | If true, this vegetation is associated with acidic areas. | `false` |
| `is_part_of_lava` | boolean | If true, this vegetation is associated with lava areas. | `false` |
| `is_part_of_water` | boolean | If true, this vegetation is associated with water. | `false` |
| `is_part_of_air` | boolean | If true, this vegetation is associated with air. | `false` |
| `is_part_of_earth` | boolean | If true, this vegetation is associated with earth. | `false` |
| `is_part_of_fire` | boolean | If true, this vegetation is associated with fire. | `false` |
| `is_part_of_ice` | boolean | If true, this vegetation is associated with ice. | `false` |
| `is_part_of_poison` | boolean | If true, this vegetation is associated with poison. | `false` |
| `is_part_of_electricity` | boolean | If true, this vegetation is associated with electricity. | `false` |
| `is_part_of_blood` | boolean | If true, this vegetation is associated with blood. | `false` |
| `is_part_of_oil` | boolean | If true, this vegetation is associated with oil. | `false` |
| `is_part_of_slime` | boolean | If true, this vegetation is associated with slime. | `false` |
| `is_part_of_magic` | boolean | If true, this vegetation is associated with magic. | `false` |
| `is_part_of_light` | boolean | If true, this vegetation is associated with light. | `false` |
| `is_part_of_darkness` | boolean | If true, this vegetation is associated with darkness. | `false` |
| `is_part_of_healing` | boolean | If true, this vegetation is associated with healing. | `false` |
| `is_part_of_damage` | boolean | If true, this vegetation is associated with damage. | `false` |
| `is_part_of_explosion` | boolean | If true, this vegetation is associated with explosions. | `false` |
| `is_part_of_food` | boolean | If true, this vegetation is associated with food. | `false` |
| `is_part_of_drink` | boolean | If true, this vegetation is associated with drink. | `false` |
| `is_part_of_medicine` | boolean | If true, this vegetation is associated with medicine. | `false` |
| `is_part_of_tool` | boolean | If true, this vegetation is associated with tools. | `false` |
| `is_part_of_weapon` | boolean | If true, this vegetation is associated with weapons. | `false` |
| `is_part_of_armor` | boolean | If true, this vegetation is associated with armor. | `false` |
| `is_part_of_accessory` | boolean | If true, this vegetation is associated with accessories. | `false` |
| `is_part_of_material` | boolean | If true, this vegetation is associated with materials. | `false` |
| `is_part_of_gem` | boolean | If true, this vegetation is associated with gems. | `false` |
| `is_part_of_ore` | boolean | If true, this vegetation is associated with ores. | `false` |
| `is_part_of_metal` | boolean | If true, this vegetation is associated with metals. | `false` |
| `is_part_of_wood` | boolean | If true, this vegetation is associated with wood. | `false` |
| `is_part_of_stone` | boolean | If true, this vegetation is associated with stone. | `false` |
| `is_part_of_plant` | boolean | If true, this vegetation is associated with plants. | `false` |
| `is_part_of_animal` | boolean | If true, this vegetation is associated with animals. | `false` |
| `is_part_of_fungus` | boolean | If true, this vegetation is associated with fungi. | `false` |
| `is_part_of_insect` | boolean | If true, this vegetation is associated with insects. | `false` |
| `is_part_of_fish` | boolean | If true, this vegetation is associated with fish. | `false` |
| `is_part_of_bird` | boolean | If true, this vegetation is associated with birds. | `false` |
| `is_part_of_mammal` | boolean | If true, this vegetation is associated with mammals. | `false` |
| `is_part_of_reptile` | boolean | If true, this vegetation is associated with reptiles. | `false` |
| `is_part_of_amphibian` | boolean | If true, this vegetation is associated with amphibians. | `false` |
| `is_part_of_undead` | boolean | If true, this vegetation is associated with the undead. | `false` |
| `is_part_of_construct` | boolean | If true, this vegetation is associated with constructs. | `false` |
| `is_part_of_elemental` | boolean | If true, this vegetation is associated with elementals. | `false` |
| `is_part_of_ghost` | boolean | If true, this vegetation is associated with ghosts. | `false` |
| `is_part_of_spirit` | boolean | If true, this vegetation is associated with spirits. | `false` |
| `is_part_of_demon` | boolean | If true, this vegetation is associated with demons. | `false` |
| `is_part_of_angel` | boolean | If true, this vegetation is associated with angels. | `false` |
| `is_part_of_god` | boolean | If true, this vegetation is associated with gods. | `false` |
| `is_part_of_player` | boolean | If true, this vegetation is associated with the player. | `false` |
| `is_part_of_enemy` | boolean | If true, this vegetation is associated with enemies. | `false` |
| `is_part_of_ally` | boolean | If true, this vegetation is associated with allies. | `false` |
| `is_part_of_neutral` | boolean | If true, this vegetation is associated with neutral entities. | `false` |
| `is_part_of_item` | boolean | If true, this vegetation is associated with items. | `false` |
| `is_part_of_structure` | boolean | If true, this vegetation is associated with structures. | `false` |
| `is_part_of_terrain` | boolean | If true, this vegetation is associated with terrain. | `false` |
| `is_part_of_environment` | boolean | If true, this vegetation is associated with the environment. | `false` |
| `is_part_of_world` | boolean | If true, this vegetation is associated with the world. | `false` |
| `is_part_of_game` | boolean | If true, this vegetation is associated with the game. | `false` |
| `is_part_of_mod` | boolean | If true, this vegetation is associated with mods. | `false` |
| `is_part_of_script` | boolean | If true, this vegetation is associated with scripts. | `false` |
| `is_part_of_component` | boolean | If true, this vegetation is associated with components. | `false` |
| `is_part_of_entity` | boolean | If true, this vegetation is associated with entities. | `false` |
| `is_part_of_scene` | boolean | If true, this vegetation is associated with scenes. | `false` |
| `is_part_of_level` | boolean | If true, this vegetation is associated with levels. | `false` |
| `is_part_of_biome` | boolean | If true, this vegetation is associated with biomes. | `true` |
| `is_part_of_cave` | boolean | If true, this vegetation is associated with caves. | `false` |
| `is_part_of_surface` | boolean | If true, this vegetation is associated with the surface. | `false` |
| `is_part_of_underground` | boolean | If true, this vegetation is associated with underground areas. | `false` |
| `is_part_of_wasteland` | boolean | If true, this vegetation is associated with wastelands. | `false` |
| `is_part_of_snowy` | boolean | If true, this vegetation is associated with snowy areas. | `false` |
| `is_part_of_desert` | boolean | If true, this vegetation is associated with desert areas. | `false` |
| `is_part_of_swamp` | boolean | If true, this vegetation is associated with swamp areas. | `false` |
| `is_part_of_forest` | boolean | If true, this vegetation is associated with forest areas. | `false` |
| `is_part_of_jungle` | boolean | If true, this vegetation is associated with jungle areas. | `false` |
| `is_part_of_fungal` | boolean | If true, this vegetation is associated with fungal areas. | `false` |
| `is_part_of_hell` | boolean | If true, this vegetation is associated with hell areas. | `false` |
| `is_part_of_crystal` | boolean | If true, this vegetation is associated with crystal areas. | `false` |
| `is_part_of_cursed` | boolean | If true, this vegetation is associated with cursed areas. | `false` |
| `is_part_of_toxic` | boolean | If true, this vegetation is associated with toxic areas. | `false` |
| `is_part_of_acidic` | boolean | If true, this vegetation is associated with acidic areas. | `false` |
| `is_part_of_lava` | boolean | If true, this vegetation is associated with lava areas. | `false` |
| `is_part_of_water` | boolean | If true, this vegetation is associated with water. | `false` |
| `is_part_of_air` | boolean | If true, this vegetation is associated with air. | `false` |
| `is_part_of_earth` | boolean | If true, this vegetation is associated with earth. | `false` |
| `is_part_of_fire` | boolean | If true, this vegetation is associated with fire. | `false` |
| `is_part_of_ice` | boolean | If true, this vegetation is associated with ice. | `false` |
| `is_part_of_poison` | boolean | If true, this vegetation is associated with poison. | `false` |
| `is_part_of_electricity` | boolean | If true, this vegetation is associated with electricity. | `false` |
| `is_part_of_blood` | boolean | If true, this vegetation is associated with blood. | `false` |
| `is_part_of_oil` | boolean | If true, this vegetation is associated with oil. | `false` |
| `is_part_of_slime` | boolean | If true, this vegetation is associated with slime. | `false` |
| `is_part_of_magic` | boolean | If true, this vegetation is associated with magic. | `false` |
| `is_part_of_light` | boolean | If true, this vegetation is associated with light. | `false` |
| `is_part_of_darkness` | boolean | If true, this vegetation is associated with darkness. | `false` |
| `is_part_of_healing` | boolean | If true, this vegetation is associated with healing. | `false` |
| `is_part_of_damage` | boolean | If true, this vegetation is associated with damage. | `false` |
| `is_part_of_explosion` | boolean | If true, this vegetation is associated with explosions. | `false` |
| `is_part_of_food` | boolean | If true, this vegetation is associated with food. | `false` |
| `is_part_of_drink` | boolean | If true, this vegetation is associated with drink. | `false` |
| `is_part_of_medicine` | boolean | If true, this vegetation is associated with medicine. | `false` |
| `is_part_of_tool` | boolean | If true, this vegetation is associated with tools. | `false` |
| `is_part_of_weapon` | boolean | If true, this vegetation is associated with weapons. | `false` |
| `is_part_of_armor` | boolean | If true, this vegetation is associated with armor. | `false` |
| `is_part_of_accessory` | boolean | If true, this vegetation is associated with accessories. | `false` |
| `is_part_of_material` | boolean | If true, this vegetation is associated with materials. | `false` |
| `is_part_of_gem` | boolean | If true, this vegetation is associated with gems. | `false` |
| `is_part_of_ore` | boolean | If true, this vegetation is associated with ores. | `false` |
| `is_part_of_metal` | boolean | If true, this vegetation is associated with metals. | `false` |
| `is_part_of_wood` | boolean | If true, this vegetation is associated with wood. | `false` |
| `is_part_of_stone` | boolean | If true, this vegetation is associated with stone. | `false` |
| `is_part_of_plant` | boolean | If true, this vegetation is associated with plants. | `false` |
| `is_part_of_animal` | boolean | If true, this vegetation is associated with animals. | `false` |
| `is_part_of_fungus` | boolean | If true, this vegetation is associated with fungi. | `false` |
| `is_part_of_insect` | boolean | If true, this vegetation is associated with insects. | `false` |
| `is_part_of_fish` | boolean | If true, this vegetation is associated with fish. | `false` |
| `is_part_of_bird` | boolean | If true, this vegetation is associated with birds. | `false` |
| `is_part_of_mammal` | boolean | If true, this vegetation is associated with mammals. | `false` |
| `is_part_of_reptile` | boolean | If true, this vegetation is associated with reptiles. | `false` |
| `is_part_of_amphibian` | boolean | If true, this vegetation is associated with amphibians. | `false` |
| `is_part_of_undead` | boolean | If true, this vegetation is associated with the undead. | `false` |
| `is_part_of_construct` | boolean | If true, this vegetation is associated with constructs. | `false` |
| `is_part_of_elemental` | boolean | If true, this vegetation is associated with elementals. | `false` |
| `is_part_of_ghost` | boolean | If true, this vegetation is associated with ghosts. | `false` |
| `is_part_of_spirit` | boolean | If true, this vegetation is associated with spirits. | `false` |
| `is_part_of_demon` | boolean | If true, this vegetation is associated with demons. | `false` |
| `is_part_of_angel` | boolean | If true, this vegetation is associated with angels. | `false` |
| `is_part_of_god` | boolean | If true, this vegetation is associated with gods. | `false` |
| `is_part_of_player` | boolean | If true, this vegetation is associated with the player. | `false` |
| `is_part_of_enemy` | boolean | If true, this vegetation is associated with enemies. | `false` |
| `is_part_of_ally` | boolean | If true, this vegetation is associated with allies. | `false` |
| `is_part_of_neutral` | boolean | If true, this vegetation is associated with neutral entities. | `false` |
| `is_part_of_item` | boolean | If true, this vegetation is associated with items. | `false` |
| `is_part_of_structure` | boolean | If true, this vegetation is associated with structures. | `false` |
| `is_part_of_terrain` | boolean | If true, this vegetation is associated with terrain. | `false` |
| `is_part_of_environment` | boolean | If true, this vegetation is associated with the environment. | `false` |
| `is_part_of_world` | boolean | If true, this vegetation is associated with the world. | `false` |
| `is_part_of_game` | boolean | If true, this vegetation is associated with the game. | `false` |
| `is_part_of_mod` | boolean | If true, this vegetation is associated with mods. | `false` |
| `is_part_of_script` | boolean | If true, this vegetation is associated with scripts. | `false` |
| `is_part_of_component` | boolean | If true, this vegetation is associated with components. | `false` |
| `is_part_of_entity` | boolean | If true, this vegetation is associated with entities. | `false` |
| `is_part_of_scene` | boolean | If true, this vegetation is associated with scenes. | `false` |
| `is_part_of_level` | boolean | If true, this vegetation is associated with levels. | `false` |
| `is_part_of_biome` | boolean | If true, this vegetation is associated with biomes. | `true` |
| `is_part_of_cave` | boolean | If true, this vegetation is associated with caves. | `false` |
| `is_part_of_surface` | boolean | If true, this vegetation is associated with the surface. | `false` |
| `is_part_of_underground` | boolean | If true, this vegetation is associated with underground areas. | `false` |
| `is_part_of_wasteland` | boolean | If true, this vegetation is associated with wastelands. | `false` |
| `is_part_of_snowy` | boolean | If true, this vegetation is associated with snowy areas. | `false` |
| `is_part_of_desert` | boolean | If true, this vegetation is associated with desert areas. | `false` |
| `is_part_of_swamp` | boolean | If true, this vegetation is associated with swamp areas. | `false` |
| `is_part_of_forest` | boolean | If true, this vegetation is associated with forest areas. | `false` |
| `is_part_of_jungle` | boolean | If true, this vegetation is associated with jungle areas. | `false` |
| `is_part_of_fungal` | boolean | If true, this vegetation is associated with fungal areas. | `false` |
| `is_part_of_hell` | boolean | If true, this vegetation is associated with hell areas. | `false` |
| `is_part_of_crystal` | boolean | If true, this vegetation is associated with crystal areas. | `false` |
| `is_part_of_cursed` | boolean | If true, this vegetation is associated with cursed areas. | `false` |
| `is_part_of_toxic` | boolean | If true, this vegetation is associated with toxic areas. | `false` |
| `is_part_of_acidic` | boolean | If true, this vegetation is associated with acidic areas. | `false` |
| `is_part_of_lava` | boolean | If true, this vegetation is associated with lava areas. | `false` |
| `is_part_of_water` | boolean | If true, this vegetation is associated with water. | `false` |
| `is_part_of_air` | boolean | If true, this vegetation is associated with air. | `false` |
| `is_part_of_earth` | boolean | If true, this vegetation is associated with earth. | `false` |
| `is_part_of_fire` | boolean | If true, this vegetation is associated with fire. | `false` |
| `is_part_of_ice` | boolean | If true, this vegetation is associated with ice. | `false` |
| `is_part_of_poison` | boolean | If true, this vegetation is associated with poison. | `false` |
| `is_part_of_electricity` | boolean | If true, this vegetation is associated with electricity. | `false` |
| `is_part_of_blood` | boolean | If true, this vegetation is associated with blood. | `false` |
| `is_part_of_oil` | boolean | If true, this vegetation is associated with oil. | `false` |
| `is_part_of_slime` | boolean | If true, this vegetation is associated with slime. | `false` |
| `is_part_of_magic` | boolean | If true, this vegetation is associated with magic. | `false` |
| `is_part_of_light` | boolean | If true, this vegetation is associated with light. | `false` |
| `is_part_of_darkness` | boolean | If true, this vegetation is associated with darkness. | `false` |
| `is_part_of_healing` | boolean | If true, this vegetation is associated with healing. | `false` |
| `is_part_of_damage` | boolean | If true, this vegetation is associated with damage. | `false` |
| `is_part_of_explosion` | boolean | If true, this vegetation is associated with explosions. | `false` |
| `is_part_of_food` | boolean | If true, this vegetation is associated with food. | `false` |
| `is_part_of_drink` | boolean | If true, this vegetation is associated with drink. | `false` |
| `is_part_of_medicine` | boolean | If true, this vegetation is associated with medicine. | `false` |
| `is_part_of_tool` | boolean | If true, this vegetation is associated with tools. | `false` |
| `is_part_of_weapon` | boolean | If true, this vegetation is associated with weapons. | `false` |
| `is_part_of_armor` | boolean | If true, this vegetation is associated with armor. | `false` |
| `is_part_of_accessory` | boolean | If true, this vegetation is associated with accessories. | `false` |
| `is_part_of_material` | boolean | If true, this vegetation is associated with materials. | `false` |
| `is_part_of_gem` | boolean | If true, this vegetation is associated with gems. | `false` |
| `is_part_of_ore` | boolean | If true, this vegetation is associated with ores. | `false` |
| `is_part_of_metal` | boolean | If true, this vegetation is associated with metals. | `false` |
| `is_part_of_wood` | boolean | If true, this vegetation is associated with wood. | `false` |
| `is_part_of_stone` | boolean | If true, this vegetation is associated with stone. | `false` |
| `is_part_of_plant` | boolean | If true, this vegetation is associated with plants. | `false` |
| `is_part_of_animal` | boolean | If true, this vegetation is associated with animals. | `false` |
| `is_part_of_fungus` | boolean | If true, this vegetation is associated with fungi. | `false` |
| `is_part_of_insect` | boolean | If true, this vegetation is associated with insects. | `false` |
| `is_part_of_fish` | boolean | If true, this vegetation is associated with fish. | `false` |
| `is_part_of_bird` | boolean | If true, this vegetation is associated with birds. | `false` |
| `is_part_of_mammal` | boolean | If true, this vegetation is associated with mammals. | `false` |
| `is_part_of_reptile` | boolean | If true, this vegetation is associated with reptiles. | `false` |
| `is_part_of_amphibian` | boolean | If true, this vegetation is associated with amphibians. | `false` |
| `is_part_of_undead` | boolean | If true, this vegetation is associated with the undead. | `false` |
| `is_part_of_construct` | boolean | If true, this vegetation is associated with constructs. | `false` |
| `is_part_of_elemental` | boolean | If true, this vegetation is associated with elementals. | `false` |
| `is_part_of_ghost` | boolean | If true, this vegetation is associated with ghosts. | `false` |
| `is_part_of_spirit` | boolean | If true, this vegetation is associated with spirits. | `false` |
| `is_part_of_demon` | boolean | If true, this vegetation is associated with demons. | `false` |
| `is_part_of_angel` | boolean | If true, this vegetation is associated with angels. | `false` |
| `is_part_of_god` | boolean | If true, this vegetation is associated with gods. | `false` |
| `is_part_of_player` | boolean | If true, this vegetation is associated with the player. | `false` |
| `is_part_of_enemy` | boolean | If true, this vegetation is associated with enemies. | `false` |
| `is_part_of_ally` | boolean | If true, this vegetation is associated with allies. | `false` |
| `is_part_of_neutral` | boolean | If true, this vegetation is associated with neutral entities. | `false` |
| `is_part_of_item` | boolean | If true, this vegetation is associated with items. | `false` |
| `is_part_of_structure` | boolean | If true, this vegetation is associated with structures. | `false` |
| `is_part_of_terrain` | boolean | If true, this vegetation is associated with terrain. | `false` |
| `is_part_of_environment` | boolean | If true, this vegetation is associated with the environment. | `false` |
| `is_part_of_world` | boolean | If true, this vegetation is associated with the world. | `false` |
| `is_part_of_game` | boolean | If true, this vegetation is associated with the game. | `false` |
| `is_part_of_mod` | boolean | If true, this vegetation is associated with mods. | `false` |
| `is_part_of_script` | boolean | If true, this vegetation is associated with scripts. | `false` |
| `is_part_of_component` | boolean | If true, this vegetation is associated with components. | `false` |
| `is_part_of_entity` | boolean | If true, this vegetation is associated with entities. | `false` |
| `is_part_of_scene` | boolean | If true, this vegetation is associated with scenes. | `false` |
| `is_part_of_level` | boolean | If true, this vegetation is associated with levels. | `false` |
| `is_part_of_biome` | boolean | If true, this vegetation is associated with biomes. | `true` |
| `is_part_of_cave` | boolean | If true, this vegetation is associated with caves. | `false` |
| `is_part_of_surface` | boolean | If true, this vegetation is associated with the surface. | `false` |
| `is_part_of_underground` | boolean | If true, this vegetation is associated with underground areas. | `false` |
| `is_part_of_wasteland` | boolean | If true, this vegetation is associated with wastelands. | `false` |
| `is_part_of_snowy` | boolean | If true, this vegetation is associated with snowy areas. | `false` |
| `is_part_of_desert` | boolean | If true, this vegetation is associated with desert areas. | `false` |
| `is_part_of_swamp` | boolean | If true, this vegetation is associated with swamp areas. | `false` |
| `is_part_of_forest` | boolean | If true, this vegetation is associated with forest areas. | `false` |
| `is_part_of_jungle` | boolean | If true, this vegetation is associated with jungle areas. | `false` |
| `is_part_of_fungal` | boolean | If true, this vegetation is associated with fungal areas. | `false` |
| `is_part_of_hell` | boolean | If true, this vegetation is associated with hell areas. | `false` |
| `is_part_of_crystal` | boolean | If true, this vegetation is associated with crystal areas. | `false` |
| `is_part_of_cursed` | boolean | If true, this vegetation is associated with cursed areas. | `false` |
| `is_part_of_toxic` | boolean | If true, this vegetation is associated with toxic areas. | `false` |
| `is_part_of_acidic` | boolean | If true, this vegetation is associated with acidic areas. | `false` |
| `is_part_of_lava` | boolean | If true, this vegetation is associated with lava areas. | `false` |
| `is_part_of_water` | boolean | If true, this vegetation is associated with water. | `false` |
| `is_part_of_air` | boolean | If true, this vegetation is associated with air. | `false` |
| `is_part_of_earth` | boolean | If true, this vegetation is associated with earth. | `false` |
| `is_part_of_fire` | boolean | If true, this vegetation is associated with fire. | `false` |
| `is_part_of_ice` | boolean | If true, this vegetation is associated with ice. | `false` |
| `is_part_of_poison` | boolean | If true, this vegetation is associated with poison. | `false` |
| `is_part_of_electricity` | boolean | If true, this vegetation is associated with electricity. | `false` |
| `is_part_of_blood` | boolean | If true, this vegetation is associated with blood. | `false` |
| `is_part_of_oil` | boolean | If true, this vegetation is associated with oil. | `false` |
| `is_part_of_slime` | boolean | If true, this vegetation is associated with slime. | `false` |
| `is_part_of_magic` | boolean | If true, this vegetation is associated with magic. | `false` |
| `is_part_of_light` | boolean | If true, this vegetation is associated with light. | `false` |
| `is_part_of_darkness` | boolean | If true, this vegetation is associated with darkness. | `false` |
| `is_part_of_healing` | boolean | If true, this vegetation is associated with healing. | `false` |
| `is_part_of_damage` | boolean | If true, this vegetation is associated with damage. | `false` |
| `is_part_of_explosion` | boolean | If true, this vegetation is associated with explosions. | `false` |
| `is_part_of_food` | boolean | If true, this vegetation is associated with food. | `false` |
| `is_part_of_drink` | boolean | If true, this vegetation is associated with drink. | `false` |
| `