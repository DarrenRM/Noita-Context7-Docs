---
title: Music Energy 000 Entity
category: entities
---

# Music Energy 000 Entity

This entity defines a basic music trigger with the tag `music_energy_000`. It appears to be a placeholder or a very simple music event that doesn't contain any specific components or behaviors within its XML definition.

## Key Elements

*   **`<Entity>`**: The root element for defining an entity in Noita.
    *   **`tags`**: A comma-separated list of tags associated with this entity. In this case, it's `music_energy_000`. This tag is likely used by the game to identify and trigger specific music tracks or events.

## Usage Notes for Modding

*   **Music Trigger**: This entity's primary purpose is likely to act as a trigger for a specific music track. Modders can leverage this by:
    *   **Associating Music**: Linking this entity to a specific music file or music event within the game's audio system.
    *   **Placement**: Placing this entity in specific biomes or areas where the associated music should play.
    *   **Customization**: While this specific entity is empty, modders could extend it by adding components for more complex music behaviors (e.g., fading, looping, conditional playback).

## Example of Potential Extension (Conceptual)

While the provided XML is minimal, a modder might extend such an entity to include more functionality:

```xml
<Entity tags="music_energy_000, custom_music_trigger" >
    <LuaComponent
        script_path="mods/my_mod/scripts/music_trigger.lua"
        execute_on_spawn="1"
        remove_after_executed="1"
    />
    <AreaEffect
        tags="music_trigger_area"
        radius="50"
        affect_player="1"
        affect_enemies="0"
        affect_items="0"
    />
</Entity>
```

This conceptual example shows how a `LuaComponent` could be added to control music playback via a script, and an `AreaEffect` could define a radius for triggering the music.