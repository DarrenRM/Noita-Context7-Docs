---
title: Biome Modifiers
source: https://noita.wiki.gg/wiki/Documentation:BiomeModifiers
category: modding-wiki
---

# Biome Modifiers

This documentation explains how to modify and create biome-specific effects and behaviors in Noita. Understanding biome modifiers is crucial for creating immersive and dynamic modded experiences, allowing you to alter the environment, enemy spawns, and visual properties of different areas within the game.

## Understanding Biome Modifiers

Biome modifiers are a powerful tool for game customization. They allow you to attach specific behaviors, visual changes, and gameplay elements to different biomes within Noita. This section will cover the fundamental concepts and how they are implemented.

### Core Concepts

Biome modifiers are typically defined within the game's data files and can be manipulated through modding. They control various aspects of a biome, including:

*   **Environmental Effects:** Such as rain, fog, or specific particle effects.
*   **Enemy Spawns:** Defining which enemies are more likely to appear in a given biome.
*   **Visual Properties:** Modifying lighting, background elements, and color palettes.
*   **Gameplay Mechanics:** Introducing unique challenges or opportunities tied to the biome.

### File Structure and Location

Biome modifiers are primarily defined in XML files within the game's data directory. Mods can override or extend these definitions.

*   **Core Biome Definitions:** These are usually found in files related to `data/biome/` or similar structures.
*   **Mod Overrides:** Mods will typically place their custom biome modifier definitions in their own mod folder, often mirroring the game's internal structure.

## Implementing Biome Modifiers

This section details how to create and apply biome modifiers through modding.

### Modifying Existing Biomes

To modify an existing biome, you will typically need to identify the relevant biome definition file and then create an override or extension in your mod.

#### Example: Adding a Visual Effect to a Biome

Let's say you want to add a subtle shimmering effect to the Coal Pits biome. You would typically find the XML definition for the Coal Pits and add a new component or modify an existing one.

```xml
<!-- Example: Hypothetical modification to a biome definition -->
<Biome name="coal_pits">
    <Modifier name="my_custom_shimmer_effect">
        <Component type="ParticleEmitter"
                   particle_type="data/particles/effects/shimmer.particle"
                   spawn_rate="0.1"
                   area_type="circle"
                   area_radius="500" />
    </Modifier>
    <!-- Other existing biome properties -->
</Biome>
```

**Note:** The exact structure and component names will vary based on the specific biome and the desired effect. Referencing the game's original data files is crucial.

### Creating New Biomes

Creating entirely new biomes is a more complex process that involves defining the biome's properties, its associated modifiers, and potentially new assets.

#### Key Components for New Biomes

When defining a new biome, you'll need to consider:

*   **Biome Name:** A unique identifier for your biome.
*   **Associated Modifiers:** Which modifiers will be active in this biome.
*   **Visuals:** Backgrounds, lighting, and particle effects.
*   **Enemy Spawns:** Defining the enemy pool.
*   **Terrain Generation:** How the biome's physical structure is formed.

#### Example: Basic Biome Definition Structure

```xml
<Biome name="my_new_biome">
    <Modifier name="default_modifiers_for_my_biome">
        <!-- Define modifiers here -->
        <Component type="EnemySpawner" enemy_id="goblin" spawn_chance="0.5" />
        <Component type="EnvironmentalEffect" effect_type="rain" intensity="0.3" />
    </Modifier>
    <Visuals>
        <Background name="data/backgrounds/my_new_biome_bg.png" />
        <Lighting color="#334455" intensity="0.8" />
    </Visuals>
    <!-- Other biome properties -->
</Biome>
```

## Biome Modifier Components

Biome modifiers can utilize various components to achieve different effects. Here's a list of common component types and their potential uses.

### Common Component Types

*   **`ParticleEmitter`**: Spawns particles within the biome.
    *   `particle_type`: Path to the particle definition file.
    *   `spawn_rate`: How frequently particles are spawned.
    *   `area_type`, `area_radius`: Defines the spawn area.
*   **`EnemySpawner`**: Controls enemy spawns.
    *   `enemy_id`: The ID of the enemy to spawn.
    *   `spawn_chance`: Probability of spawning the enemy.
    *   `spawn_limit`: Maximum number of this enemy that can exist.
*   **`EnvironmentalEffect`**: Applies global environmental changes.
    *   `effect_type`: The type of effect (e.g., "rain", "fog", "wind").
    *   `intensity`: Strength or density of the effect.
*   **`Lighting`**: Modifies the biome's lighting.
    *   `color`: RGB color value.
    *   `intensity`: Brightness of the lighting.
*   **`SoundEmitter`**: Plays ambient sounds.
    *   `sound_file`: Path to the sound file.
    *   `volume`: Playback volume.
    *   `loop`: Whether the sound should loop.

### Referencing Game Data

To effectively use these components, you'll need to refer to the game's internal data files for particle definitions, enemy IDs, sound files, and more.

*   **Particle Definitions:** Found in `data/particles/`.
*   **Enemy IDs:** Often found in `data/entities/animals/` or `data/entities/enemies/`.
*   **Sound Files:** Typically located in `data/audio/`.

## Lua Scripting and Biome Modifiers

While XML defines the core properties of biome modifiers, Lua scripting can be used to create more dynamic and complex behaviors.

### Triggering Lua Scripts from Biomes

You can often trigger Lua functions based on biome events or conditions. This is usually done by referencing Lua scripts within your XML definitions.

#### Example: Executing a Lua Function on Biome Entry

```xml
<Biome name="my_special_biome">
    <Modifier name="lua_event_modifier">
        <Component type="LuaScriptTrigger"
                   event="on_biome_enter"
                   script_function="my_mod.handle_biome_entry" />
    </Modifier>
    <!-- ... -->
</Biome>
```

In your mod's Lua files (e.g., `mods/my_mod/scripts/main.lua`):

```lua
-- mods/my_mod/scripts/main.lua
local my_mod = {}

function my_mod.handle_biome_entry(biome_name, player)
    print("Player entered biome: " .. biome_name)
    -- Add custom logic here, e.g., spawn a unique item, apply a status effect
    if biome_name == "my_special_biome" then
        -- Example: Give the player a temporary buff
        player:add_status_effect("invincibility", 10) -- 10 seconds of invincibility
    end
end

return my_mod
```

### Accessing Biome Information in Lua

Your Lua scripts can access information about the current biome and its properties.

*   **`Game.GetActiveBiome()`**: Returns the name of the currently active biome.
*   **`Game.GetBiomeProperties(biome_name)`**: Returns a table of properties for a given biome.

#### Example: Checking Biome Properties in Lua

```lua
local current_biome_name = Game.GetActiveBiome()
local biome_props = Game.GetBiomeProperties(current_biome_name)

if biome_props and biome_props.lighting_color == "#FF0000" then
    print("This biome has red lighting!")
end
```

## Useful Links and Resources

*   [Noita Modding: Lua API](https://noita.wiki.gg/wiki/Modding:_Lua_API)
*   [Noita Modding: XML Structure](https://noita.wiki.gg/wiki/Modding:_XML_Structure)
*   [Noita Wiki - Biomes](https://noita.wiki.gg/wiki/Biomes) (for understanding existing biomes)

By leveraging these concepts and resources, you can significantly enhance your Noita mods with custom biome behaviors and environments.