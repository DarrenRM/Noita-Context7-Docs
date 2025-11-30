---
title: Colour Spell Projectile Logic
category: scripts
---

# Colour Spell Projectile Logic

This script defines the behavior of projectiles that change their visual effects based on a specified color. It dynamically assigns particle effects and modifies explosion properties based on the `colour_name` variable stored in the projectile's `VariableStorageComponent`.

## Key Components and Logic

### 1. Variable Retrieval

The script first attempts to retrieve the `colour_name` from the projectile's `VariableStorageComponent`. This variable dictates which color-specific effects will be applied.

### 2. Color Data Mapping

A `data` table maps color names to specific particle effects.

```lua
local data =
{
	red =
	{
		particle = "spark_red",
	},
	orange =
	{
		particle = "spark",
	},
	yellow =
	{
		particle = "spark_yellow",
	},
	green =
	{
		particle = "spark_green",
	},
	blue =
	{
		particle = "plasma_fading",
	},
	purple =
	{
		particle = "spark_purple_bright",
	},
	rainbow =
	{
		particles = {"spark_red", "spark", "spark_yellow", "spark_green", "plasma_fading", "spark_purple_bright"},
	},
	invis =
	{
	},
}
```

-   **`particle`**: Specifies a single particle material to be emitted.
-   **`particles`**: For "rainbow" effects, this is a table of particle materials from which one is randomly selected.

### 3. Effect Application

If a `colour` is successfully retrieved:

-   **Particle Emitter Component**: The `emitted_material_name` of cosmetic particle emitters is set to the determined particle effect. If no particle is found for the color, emission is disabled.
-   **Sprite Particle Emitter Component**: Emission is disabled for these emitters.
-   **Sprite Component**: The sprite itself is made invisible.
-   **Projectile Component**:
    -   The `config_explosion.explosion_sprite` is cleared.
    -   The `config_explosion.spark_material` is set to the determined particle effect. If no particle is found, spark effects are disabled.

## Key Attributes Modified

-   **`VariableStorageComponent.colour_name`**: (Input) Determines the color effect.
-   **`ParticleEmitterComponent.emitted_material_name`**: (Output) Sets the particle material for cosmetic effects.
-   **`ParticleEmitterComponent.is_emitting`**: (Output) Controls whether cosmetic particles are emitted.
-   **`SpriteParticleEmitterComponent.is_emitting`**: (Output) Disables sprite particle emission.
-   **`SpriteComponent.visible`**: (Output) Hides the projectile's sprite.
-   **`ProjectileComponent.config_explosion.explosion_sprite`**: (Output) Clears the explosion sprite.
-   **`ProjectileComponent.config_explosion.spark_material`**: (Output) Sets the material for explosion sparks.
-   **`ProjectileComponent.config_explosion.material_sparks_enabled`**: (Output) Controls material spark emission.
-   **`ProjectileComponent.config_explosion.sparks_enabled`**: (Output) Controls general spark emission.