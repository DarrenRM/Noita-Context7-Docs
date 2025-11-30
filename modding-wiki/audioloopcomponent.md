---
title: AudioLoopComponent
source: https://noita.wiki.gg/wiki/Documentation:AudioLoopComponent
category: modding-wiki
---

# AudioLoopComponent

This documentation page details the `AudioLoopComponent` in Noita, a crucial component for implementing looping sound effects within the game. Understanding this component is essential for modders who wish to add custom ambient sounds, recurring effects, or dynamic audio elements to their mods, enhancing the player's immersive experience.

## Overview

The `AudioLoopComponent` is responsible for managing and playing sound effects that loop continuously. This is commonly used for background music, ambient environmental sounds, or any audio that needs to persist over a period of time without being manually retriggered.

## Component Properties

The `AudioLoopComponent` has several properties that can be configured within the game's entity XML files. These properties allow for fine-grained control over how the audio loop behaves.

### `sound`

*   **Type:** `String`
*   **Description:** The name of the sound file to be played. This should correspond to a sound defined in the game's audio assets.

### `loop_sound`

*   **Type:** `String`
*   **Description:** The name of the sound file to be used for the looping portion of the audio. This is often the same as `sound`, but can be different for more complex audio designs.

### `loop_delay`

*   **Type:** `Float`
*   **Description:** The delay in seconds before the `loop_sound` begins playing after the initial `sound` has finished. A value of `0` means the loop starts immediately.

### `loop_duration`

*   **Type:** `Float`
*   **Description:** The duration in seconds for which the `loop_sound` will play before restarting. If this is set to `0`, the loop will play indefinitely until the entity is destroyed or the component is disabled.

### `play_on_spawn`

*   **Type:** `Boolean`
*   **Description:** If `true`, the audio loop will start playing automatically when the entity containing this component spawns. If `false`, the loop must be triggered by other game logic (e.g., via Lua scripting).

### `volume`

*   **Type:** `Float`
*   **Description:** The volume of the audio loop, ranging from `0.0` (silent) to `1.0` (full volume).

### `pitch`

*   **Type:** `Float`
*   **Description:** The pitch of the audio loop. A value of `1.0` is the default pitch. Values greater than `1.0` increase the pitch, while values less than `1.0` decrease it.

### `spatial`

*   **Type:** `Boolean`
*   **Description:** If `true`, the sound will be played with spatial audio properties, meaning its volume and position will be affected by the player's location. If `false`, the sound will be played as a 2D audio effect.

### `distance`

*   **Type:** `Float`
*   **Description:** If `spatial` is `true`, this property defines the maximum distance at which the sound can be heard.

### `random_pitch_range`

*   **Type:** `Float`
*   **Description:** A range added to the `pitch` property to introduce slight variations in pitch for each playback. For example, a value of `0.1` would mean the pitch can randomly vary between `pitch - 0.1` and `pitch + 0.1`.

### `random_volume_range`

*   **Type:** `Float`
*   **Description:** A range added to the `volume` property to introduce slight variations in volume for each playback.

## Example Usage

Here's an example of how to implement an `AudioLoopComponent` in an entity's XML definition. This example creates an entity that plays a looping ambient sound when it spawns.

```xml
<entity name="ambient_cave_drips">
    <physics gravity_affect="0" />
    <audioloopcomponent
        sound="data/sounds/ambient/cave_drips.ogg"
        loop_sound="data/sounds/ambient/cave_drips.ogg"
        loop_delay="0"
        loop_duration="0"
        play_on_spawn="1"
        volume="0.7"
        pitch="1.0"
        spatial="1"
        distance="50"
        random_pitch_range="0.05"
        random_volume_range="0.1"
    />
</entity>
```

In this example:

*   `sound` and `loop_sound` are set to the same ambient drip sound.
*   `loop_delay` is `0`, so the loop starts immediately.
*   `loop_duration` is `0`, meaning it will loop indefinitely.
*   `play_on_spawn` is `1` (true), so the sound starts as soon as the entity is created.
*   `volume` is set to `0.7` for a moderate sound level.
*   `spatial` is `1` (true), making it a 3D sound.
*   `distance` is `50`, meaning it can be heard up to 50 units away.
*   `random_pitch_range` and `random_volume_range` add subtle variations to make the sound feel more natural.

## Integration with Lua Scripting

While `play_on_spawn` can automatically start audio loops, modders can also control `AudioLoopComponent` behavior dynamically using Lua scripting. This allows for more complex audio events, such as starting or stopping loops based on player actions, game events, or entity states.

You can access and modify the properties of an `AudioLoopComponent` attached to an entity using the `Entity.GetComponent(component_name)` and `Component.SetProperty(property_name, value)` methods in Lua.

### Example Lua Snippet (Conceptual)

```lua
-- Assuming 'my_entity' is a reference to an entity with an AudioLoopComponent
local audio_component = my_entity:GetComponent("AudioLoopComponent")

if audio_component then
    -- Start the audio loop if it's not already playing
    if not audio_component:IsPlaying() then -- Note: Actual method might differ, check Lua API
        audio_component:Play() -- Note: Actual method might differ, check Lua API
    end

    -- Change the volume
    audio_component:SetProperty("volume", 0.5)

    -- Stop the audio loop
    -- audio_component:Stop() -- Note: Actual method might differ, check Lua API
end
```

**Note:** The exact Lua methods for controlling audio components might vary. Always refer to the [Noita Lua API documentation](https://noita.wiki.gg/wiki/Modding:_Lua_API) for the most up-to-date information on available functions and their usage.

## Related Components

*   **`SoundComponent`**: For playing single, non-looping sound effects.
*   **`MusicComponent`**: For managing background music tracks, which often have more complex playback and transition logic.

By understanding and utilizing the `AudioLoopComponent`, modders can significantly enrich the auditory experience of their Noita mods, creating more atmospheric and engaging gameplay.