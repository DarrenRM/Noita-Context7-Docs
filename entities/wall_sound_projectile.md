---
title: Wall Sound Projectile
category: entities
---

# Wall Sound Projectile

This document describes the `wall_sound.xml` entity, which defines a projectile that emits a looping sound when active.

## Entity Definition

The core of this entity is a projectile with the tag `projectile_player`.

```xml
<Entity name="$projectile_default" tags="projectile_player">
    <!-- Components -->
</Entity>
```

## Key Components

### LifetimeComponent

This component dictates how long the projectile will exist before being removed.

| Attribute | Value | Description                               |
| :-------- | :---- | :---------------------------------------- |
| `lifetime` | `400` | The duration in frames the projectile lasts. |

### AudioLoopComponent

This component is responsible for playing a looping sound effect associated with the projectile.

| Attribute   | Value                               | Description                                                                 |
| :---------- | :---------------------------------- | :-------------------------------------------------------------------------- |
| `file`      | `data/audio/Desktop/projectiles.bank` | The audio bank file containing the sound event.                             |
| `event_name`| `player_projectiles/wall/loop`      | The specific sound event name to be played from the audio bank.             |
| `set_speed_parameter` | `0` | Controls if the sound's playback speed is linked to the projectile's speed (0 means no). |
| `auto_play` | `1` | Automatically starts playing the sound when the component is initialized. |