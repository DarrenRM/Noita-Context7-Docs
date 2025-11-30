---
title: AudioListenerComponent
source: https://noita.wiki.gg/wiki/Documentation:AudioListenerComponent
category: modding-wiki
---

# AudioListenerComponent

This documentation page details the `AudioListenerComponent` in Noita, a crucial component for managing how sound is perceived and processed within the game. Understanding this component is essential for modders looking to implement custom audio behaviors, effects, or to fine-tune the game's soundscape.

## Overview

The `AudioListenerComponent` is attached to entities that act as the "listener" for audio in the game. Typically, this is the player character. It dictates how sound sources are perceived, including factors like volume falloff, spatialization, and potential audio effects applied to the listener's perspective. Modding this component allows for advanced audio manipulation.

## Component Properties

The `AudioListenerComponent` has several properties that can be configured within the game's XML files. These properties control various aspects of audio perception.

### `volume_falloff_factor`

This property controls how quickly the volume of a sound source decreases with distance from the listener. A higher value means the volume drops off more rapidly.

*   **Type:** `float`
*   **Default:** `1.0`

### `min_volume`

The minimum volume a sound can be reduced to, regardless of distance. This prevents sounds from becoming completely inaudible at extreme distances if desired.

*   **Type:** `float`
*   **Default:** `0.0`

### `max_volume`

The maximum volume a sound can be played at, irrespective of its source's volume setting. This can be used to boost quieter sounds or cap louder ones.

*   **Type:** `float`
*   **Default:** `1.0`

### `spatialization_factor`

This property influences how much the stereo panning of a sound is affected by its position relative to the listener. A value of `1.0` means full spatialization, where sounds from the left will be panned left, and sounds from the right will be panned right. A value of `0.0` would disable spatialization, making all sounds mono and centered.

*   **Type:** `float`
*   **Default:** `1.0`

### `do_not_process_audio`

A boolean flag that, when set to `true`, prevents this listener from processing any audio. This is rarely used for the player but could be useful for specific scenarios or debugging.

*   **Type:** `bool`
*   **Default:** `false`

## Example Usage (XML)

Here's an example of how the `AudioListenerComponent` might be defined in an entity's XML file. This example shows a listener with slightly more aggressive volume falloff and full spatialization.

```xml
<entity name="player" >
    <AudioListenerComponent
        volume_falloff_factor="1.2"
        min_volume="0.1"
        max_volume="1.5"
        spatialization_factor="1.0"
        do_not_process_audio="false"
    />
    <!-- Other components for the player -->
</entity>
```

## Modding Considerations

When modding Noita, you can modify existing entities to include or alter their `AudioListenerComponent`. This is typically done by creating or editing XML files within your mod's directory structure.

### Adding an Audio Listener to a Custom Entity

If you are creating a new entity that should act as an audio listener (e.g., a special camera or a drone that "hears" the environment), you would add the component like this:

```xml
<entity name="my_custom_listener_entity" >
    <AudioListenerComponent
        volume_falloff_factor="0.8"
        spatialization_factor="0.7"
    />
    <!-- Other components -->
</entity>
```

### Modifying the Player's Audio Listener

To alter the player's audio perception, you would typically target the `player` entity and modify its `AudioListenerComponent`. This might involve overriding the default values to create a specific audio experience for your mod.

**Note:** Modifying core game entities like the player should be done with care, as it can have widespread effects on gameplay.

## Related Components and Concepts

*   **`AudioSourceComponent`**: This component is attached to entities that *produce* sound. The `AudioListenerComponent` interacts with `AudioSourceComponent`s to determine how those sounds are perceived.
*   **Sound Design**: Understanding how audio propagates and is perceived is key to effective sound design in games. The `AudioListenerComponent` is a fundamental part of this.
*   **Lua API**: While the core properties are set in XML, advanced audio manipulation or dynamic changes to listener properties might be achievable through the Lua API. Refer to the [Lua API](https://noita.wiki.gg/wiki/Modding:_Lua_API) for more details on scripting audio.