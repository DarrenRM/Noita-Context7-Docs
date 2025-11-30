---
title: Magic Eye Platform
category: entities
---

---

# Magic Eye Platform

This entity represents a special platform that is part of the "magic eye" system. It has unique properties related to particle emission and script execution.

## Key Components

### VelocityComponent

Controls the movement and physics of the platform.

*   **gravity\_y**: `0` - The platform is not affected by gravity.
*   **air\_friction**: `10` - Applies air friction.
*   **mass**: `0.00` - Has negligible mass.

### ParticleEmitterComponent

Responsible for emitting particles, likely for visual effects.

*   **emitted\_material\_name**: `spark_red` - The material of the emitted particles.
*   **lifetime\_min/max**: `1.0` / `3.0` - Duration the particles exist.
*   **count\_min/max**: `4` / `4` - Number of particles emitted per burst.
*   **render\_on\_grid**: `1` - Particles are rendered on the game grid.
*   **fade\_based\_on\_lifetime**: `1` - Particles fade out as they age.
*   **cosmetic\_force\_create**: `1` - Particles are created with a cosmetic force.
*   **emission\_interval\_min/max\_frames**: `1` / `1` - Particles are emitted every frame.
*   **image\_animation\_file**: `data/particles/image_emitters/temporary_platform_wide.png` - Specifies the animation for emitted particles.
*   **image\_animation\_speed**: `10` - Speed of the particle animation.
*   **x\_vel\_min/max**: `-140` / `140` - Horizontal velocity range for emitted particles.
*   **y\_vel\_min/max**: `0` / `0` - Vertical velocity range for emitted particles.
*   **is\_emitting**: `1` - The emitter is active.

### LuaComponent

Executes a Lua script for custom behavior.

*   **script\_source\_file**: `data/scripts/magic/platform_disable.lua` - The path to the script file.
*   **execute\_every\_n\_frame**: `40` - The script is executed every 40 frames.

### AudioLoopComponent

Handles audio playback for the platform.

*   **file**: `data/audio/Desktop/projectiles.bank` - The audio bank file.
*   **event\_name**: `player_projectiles/wall/loop_solid` - The specific audio event to play.
*   **play\_on\_component\_enable**: `1` - Audio plays when the component is enabled.
*   **auto\_play\_if\_enabled**: `1` - Audio automatically plays if the component is enabled.