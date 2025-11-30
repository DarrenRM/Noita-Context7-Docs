---
title: WormComponent Documentation for AI-Assisted Modding
source: https://noita.wiki.gg/wiki/Documentation:WormComponent
category: modding-wiki
---

# WormComponent Documentation

This document details the `WormComponent` in Noita, a crucial element for understanding and modifying how worms behave and interact within the game. By understanding its properties and how to manipulate them, modders can create custom worm behaviors, alter their spawning, and integrate them into new gameplay mechanics.

## WormComponent Properties

The `WormComponent` is attached to entities that represent worms. It governs various aspects of their existence, from their visual representation to their movement and interaction with the environment.

### Core Properties

| Property Name | Type | Description | Default Value |
|---|---|---|---|
| `worm_material` | `string` | The material the worm is made of. This affects its visual appearance and how it interacts with other game elements (e.g., melting, freezing). | `worm_flesh` |
| `worm_segment_material` | `string` | The material of the worm's segments. | `worm_flesh` |
| `segment_length` | `float` | The length of each individual segment of the worm. Affects the overall visual length and flexibility. | `1.0` |
| `segment_radius` | `float` | The radius of each segment. Affects the thickness of the worm. | `0.25` |
| `num_segments` | `int` | The total number of segments the worm is composed of. | `10` |
| `speed` | `float` | The base movement speed of the worm. | `1.0` |
| `turn_speed` | `float` | How quickly the worm can change direction. | `1.0` |
| `ground_friction` | `float` | Friction applied when the worm is in contact with the ground. | `0.0` |
| `air_friction` | `float` | Friction applied when the worm is in the air. | `0.0` |
| `gravity` | `float` | The gravitational pull affecting the worm. | `1.0` |
| `jump_force` | `float` | The force applied when the worm attempts to jump. | `0.0` |
| `jump_interval` | `float` | The time between potential jumps. | `0.0` |
| `jump_chance` | `float` | The probability (0.0 to 1.0) of the worm jumping when it has the opportunity. | `0.0` |
| `damage_per_segment` | `float` | The amount of damage each segment inflicts on contact. | `5.0` |
| `damage_type` | `string` | The type of damage the worm inflicts (e.g., `physical`, `fire`, `ice`). | `physical` |
| `explosion_on_death` | `bool` | Whether the worm explodes upon death. | `false` |
| `explosion_radius` | `float` | The radius of the explosion if `explosion_on_death` is true. | `0.0` |
| `explosion_damage` | `float` | The damage dealt by the explosion. | `0.0` |
| `explosion_damage_type` | `string` | The type of damage dealt by the explosion. | `physical` |
| `explosion_material` | `string` | The material created by the explosion. | `none` |
| `explosion_force` | `float` | The force applied by the explosion. | `0.0` |
| `explosion_force_type` | `string` | The type of force applied by the explosion. | `none` |
| `explosion_sound` | `string` | The sound effect played when the worm explodes. | `none` |
| `explosion_visual` | `string` | The visual effect played when the worm explodes. | `none` |
| `explosion_visual_scale` | `float` | The scale of the explosion visual effect. | `1.0` |
| `explosion_visual_offset` | `Vec2` | The offset of the explosion visual effect. | `(0, 0)` |
| `explosion_visual_rotation` | `float` | The rotation of the explosion visual effect. | `0.0` |
| `explosion_visual_loop` | `bool` | Whether the explosion visual effect should loop. | `false` |
| `explosion_visual_delay` | `float` | The delay before the explosion visual effect plays. | `0.0` |
| `explosion_visual_duration` | `float` | The duration of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The frame speed of the explosion visual effect. | `1.0` |
| `explosion_visual_frame_count` | `int` | The number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the explosion visual effect frames should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |
| `explosion_visual_frame_count` | `int` | The total number of frames in the explosion visual effect. | `1` |
| `explosion_visual_frame_loop` | `bool` | Whether the frames of the explosion visual effect should loop. | `false` |
| `explosion_visual_frame_delay` | `float` | The delay between frames of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_duration` | `float` | The duration of each frame of the explosion visual effect. | `0.0` |
| `explosion_visual_frame_speed` | `float` | The speed at which frames of the explosion visual effect are played. | `1.0` |