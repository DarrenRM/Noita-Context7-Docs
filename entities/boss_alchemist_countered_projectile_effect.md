---
title: Boss Alchemist Countered Projectile Effect
category: entities
---

---

# Boss Alchemist Countered Projectile Effect

This entity defines the visual and particle effects applied to projectiles that have been "countered" or reflected by the Boss Alchemist's shield.

## Key Components

### SpriteComponent
This component defines the visual representation of the countered projectile.

*   **image\_file**: `data/projectiles_gfx/orb_pink_ring.xml` - Specifies the graphical asset used for the effect.
*   **alpha**: `1` - The opacity of the sprite.
*   **offset\_x**, **offset\_y**: `8` - Adjusts the sprite's position relative to the entity's origin.
*   **rect\_animation**: `"spawn"` - Indicates the animation state to play.

### ParticleEmitterComponent (Trail)
This component generates a continuous trail of particles behind the countered projectile.

*   **emitted\_material\_name**: `"plasma_fading_pink"` - The material used for the emitted particles.
*   **gravity.y**: `0.0` - No vertical gravity applied to the trail particles.
*   **x\_vel\_min**, **x\_vel\_max**, **y\_vel\_min**, **y\_vel\_max**: `0` - Particles have no initial velocity.
*   **friction**: `10` - High friction to slow down particles quickly.
*   **count\_min**, **count\_max**: `1` - Emits a single particle per emission.
*   **lifetime\_min**, **lifetime\_max**: `0.05` to `1.15` - The duration each particle exists.
*   **is\_trail**: `1` - Marks this emitter as a trail effect.
*   **trail\_gap**: `3` - The spacing between trail particles.
*   **emit\_cosmetic\_particles**: `1` - Emits particles that are purely visual.
*   **emission\_interval\_min\_frames**, **emission\_interval\_max\_frames**: `1` - Particles are emitted every frame.
*   **is\_emitting**: `1` - The emitter is active.

### ParticleEmitterComponent (Poof)
This component generates a burst of particles when the countered projectile effect is active, simulating a "poof" or dissipation.

*   **emitted\_material\_name**: `"plasma_fading_pink"` - The material used for the emitted particles.
*   **emitter\_lifetime\_frames**: `2` - The emitter itself only lasts for 2 frames.
*   **gravity.y**: `0.0` - No vertical gravity applied to these particles.
*   **area\_circle\_radius.min**, **area\_circle\_radius.max**: `3` - Particles are emitted within a small circular area.
*   **velocity\_always\_away\_from\_center**: `10` - Particles are pushed outwards from the emission point.
*   **friction**: `1.5` - Moderate friction applied to the particles.
*   **count\_min**, **count\_max**: `20` to `40` - The number of particles emitted in the burst.
*   **lifetime\_min**, **lifetime\_max**: `0.5` to `2.0` - The duration each particle exists.
*   **emit\_cosmetic\_particles**: `1` - Emits particles that are purely visual.
*   **emission\_interval\_min\_frames**, **emission\_interval\_max\_frames**: `1` - Particles are emitted every frame while the emitter is active.
*   **is\_emitting**: `1` - The emitter is active.