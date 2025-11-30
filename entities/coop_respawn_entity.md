---
title: Coop Respawn Entity
category: entities
---

# Coop Respawn Entity

This entity defines the behavior and appearance of the respawn point used in cooperative multiplayer modes in Noita.

## Key Attributes

*   **`tags`**: `coop_respawn` - Identifies this entity as a cooperative respawn point.

## Core Functionality

The `coop_respawn` entity is a fundamental building block for Noita's multiplayer functionality. Its primary purpose is to serve as a designated location where players can respawn after being defeated. While the provided XML is minimal, this entity would typically be associated with:

*   **Visual Representation**: A sprite or visual effect to clearly indicate the respawn point to players.
*   **Spawn Logic**: Scripts that handle the actual respawning of a player character at this location, including any associated effects or delays.
*   **Player Interaction**: Potentially, logic to prevent players from interacting with or destroying the respawn point.

## Example Usage (Conceptual)

While the provided XML is empty, a more complete definition might include:

```xml
<Entity tags="coop_respawn, static_building">
    <Base entity="data/entities/base_custom_entity.xml" />
    <Sprite anim="data/anim/coop_respawn.xml" />
    <LuaComponent script_path="data/scripts/coop_respawn.lua" />
    <ParticleEmitterComponent
        particle_file="data/particles/respawn_glow.xml"
        delay="0.1"
        count="1"
        lifetime="1.0"
        always_active="1"
        >
    </ParticleEmitterComponent>
</Entity>
```

**Explanation of Conceptual Elements:**

*   **`static_building` tag**: Indicates it's a permanent part of the environment.
*   **`Sprite`**: Defines the visual appearance of the respawn point.
*   **`LuaComponent`**: Links to a script that handles the respawn logic.
*   **`ParticleEmitterComponent`**: Adds a visual effect, like a glow, to make the respawn point more noticeable.