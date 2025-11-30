---
title: Gunpowder Tiny Explosion Particle
category: entities
---

---

# Gunpowder Tiny Explosion Particle

This entity defines the visual components of a small gunpowder explosion particle effect in Noita. It primarily uses `LoadEntitiesComponent` to spawn other particle entities, creating a layered and dynamic explosion.

## Key Components

### LoadEntitiesComponent

This component is responsible for loading and spawning other entities. The `count.min` and `count.max` attributes determine the number of instances to spawn, while `entity_file` specifies the entity to load. `kill_entity="0"` means the parent entity (this gunpowder particle) is not destroyed after spawning its children.

*   **`entity_file="data/entities/particles/particle_explosion/explosion_flare_small.xml"`**: Spawns a small explosion flare.
*   **`entity_file="data/entities/particles/particle_explosion/explosion_flare_fog_of_war_hole_small.xml"`**: Spawns a small fog of war hole flare, likely to briefly reveal the area.
*   **`entity_file="data/entities/particles/particle_explosion/explosion_trail_smoke_gunpowder_short.xml"`**: Spawns short gunpowder smoke trails. The `count.min` and `count.max` are set to 2-3, indicating multiple trails.
*   **`entity_file="data/entities/particles/particle_explosion/explosion_smoke_gunpowder.xml"`**: Spawns standard gunpowder smoke particles. Similar to the trails, 2-3 instances are spawned.
*   **`entity_file="data/entities/particles/particle_explosion/ember_trail.xml"`**: Spawns ember trails.
    *   **`count.min="-3"`**: This is a notable attribute. A negative `count.min` is used to make the appearance of these ember trails less predictable and potentially rarer, adding a subtle variation to the explosion.
    *   **`count.max="3"`**: Spawns up to 3 ember trails.
    *   **`kill_entity="1"`**: This indicates that the parent entity *will* be killed after spawning these ember trails. This is different from the other `LoadEntitiesComponent` instances in this file.

## Summary

The `main_gunpowder_tiny.xml` entity orchestrates a small, multi-faceted explosion by loading several pre-defined particle effects. It creates a visual sequence of flares, smoke, and ember trails, with a specific mechanic for controlling the rarity of ember trails.