---
title: SpriteAnimatorComponent
source: https://noita.wiki.gg/wiki/Documentation:SpriteAnimatorComponent
category: modding-wiki
---

# SpriteAnimatorComponent

This documentation explains the `SpriteAnimatorComponent` in Noita, a crucial component for managing sprite animations within the game. Understanding this component is essential for modders looking to create custom animations for entities, objects, and visual effects, significantly enhancing the visual fidelity and dynamism of their mods.

## Overview

The `SpriteAnimatorComponent` is responsible for controlling sprite animations. It allows entities to cycle through a sequence of sprites, creating the illusion of movement or change. This is fundamental for bringing characters, enemies, environmental elements, and special effects to life within Noita.

## Component Properties

The `SpriteAnimatorComponent` has several properties that can be configured in your entity XML files. These properties dictate how the animation behaves.

### `sprite_animation_file`

This property specifies the path to the `.xml` file containing the animation data.

*   **Type:** `string`
*   **Required:** Yes

**Example:**

```xml
<SpriteAnimatorComponent sprite_animation_file="data/animations/my_custom_animation.xml" />
```

### `animation_speed`

Controls the playback speed of the animation. A value of `1.0` is the default speed. Higher values make the animation faster, and lower values make it slower.

*   **Type:** `float`
*   **Required:** No
*   **Default:** `1.0`

**Example:**

```xml
<SpriteAnimatorComponent sprite_animation_file="data/animations/my_custom_animation.xml" animation_speed="0.5" />
```

### `loop`

Determines whether the animation should loop back to the beginning once it reaches the end.

*   **Type:** `bool`
*   **Required:** No
*   **Default:** `true`

**Example:**

```xml
<SpriteAnimatorComponent sprite_animation_file="data/animations/my_custom_animation.xml" loop="false" />
```

### `start_frame`

Specifies the index of the frame to start the animation from. Frame indices are zero-based.

*   **Type:** `int`
*   **Required:** No
*   **Default:** `0`

**Example:**

```xml
<SpriteAnimatorComponent sprite_animation_file="data/animations/my_custom_animation.xml" start_frame="5" />
```

### `animation_name`

Allows you to specify a particular animation sequence within the animation file to play. This is useful if your animation file defines multiple named sequences.

*   **Type:** `string`
*   **Required:** No
*   **Default:** The first animation defined in the file.

**Example:**

```xml
<SpriteAnimatorComponent sprite_animation_file="data/animations/my_custom_animation.xml" animation_name="attack_sequence" />
```

## Animation File Structure (`.xml`)

The `.xml` file referenced by `sprite_animation_file` defines the actual animation frames and their timing.

### Root Element

The root element of an animation file is typically `<SpriteAnimator>`.

### `<Animation>` Element

Each animation sequence is defined within an `<Animation>` element.

*   **`name` attribute:** A string identifier for the animation sequence.
*   **`speed` attribute:** Overrides the `animation_speed` property for this specific animation.
*   **`loop` attribute:** Overrides the `loop` property for this specific animation.

### `<Frame>` Element

Each individual frame of the animation is defined by a `<Frame>` element.

*   **`sprite_id` attribute:** The ID of the sprite to display for this frame.
*   **`duration` attribute:** The number of game frames this sprite should be displayed for.

**Example Animation File (`data/animations/my_custom_animation.xml`):**

```xml
<SpriteAnimator>
    <Animation name="idle" speed="1.0" loop="true">
        <Frame sprite_id="my_idle_sprite_0" duration="10" />
        <Frame sprite_id="my_idle_sprite_1" duration="10" />
    </Animation>

    <Animation name="walk" speed="1.5" loop="true">
        <Frame sprite_id="my_walk_sprite_0" duration="5" />
        <Frame sprite_id="my_walk_sprite_1" duration="5" />
        <Frame sprite_id="my_walk_sprite_2" duration="5" />
        <Frame sprite_id="my_walk_sprite_3" duration="5" />
    </Animation>
</SpriteAnimator>
```

## Integrating with Entities

To use the `SpriteAnimatorComponent`, you add it to the `<Entity>` definition in your mod's `.xml` files.

**Example Entity Definition:**

```xml
<Entity name="my_animated_object">
    <SpriteAnimatorComponent sprite_animation_file="data/animations/my_custom_animation.xml" animation_speed="1.2" loop="true" />
    <TransformComponent />
    <!-- Other components -->
</Entity>
```

## Important Notes and Tips

*   **Sprite IDs:** Ensure that the `sprite_id` values used in your animation files correspond to actual sprite definitions in your mod's sprite sheets or other sprite definition files.
*   **Performance:** Complex animations with many frames or very short durations can impact performance. Optimize your animations where possible.
*   **Debugging:** If your animation isn't playing as expected, double-check the `sprite_animation_file` path, the `sprite_id` references, and the `duration` values.
*   **Lua API:** While the `SpriteAnimatorComponent` is configured via XML, you can often interact with and control animations dynamically using the [Lua API](https://noita.wiki.gg/wiki/Modding:_Lua_API). For example, you might trigger specific animations based on game events.

This component is a cornerstone for creating visually engaging content in Noita mods. By mastering its properties and the structure of animation files, you can bring your creations to life with dynamic and captivating animations.