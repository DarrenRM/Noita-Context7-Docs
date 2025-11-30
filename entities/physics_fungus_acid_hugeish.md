---
title: Physics Fungus Acid Hugeish
category: entities
---

# Physics Fungus Acid Hugeish

This entity represents a large, physics-enabled acid fungus prop. It's designed to be destructible, spill its contents upon damage, and explode when sufficiently damaged or destroyed.

## Key Components

### PhysicsBody2Component
Manages the physical properties of the entity.

*   **is\_static**: `0` - The body is not static and can be moved.
*   **allow\_sleep**: `1` - The body can enter a sleep state to save performance when not in motion.
*   **linear\_damping**: `0.5` - Reduces linear velocity over time.
*   **init\_offset\_y**: `48` - Initial vertical offset for the physics body.

### PhysicsImageShapeComponent
Defines the visual and physical shape of the fungus, composed of multiple parts.

*   **image\_file**: Specifies the sprite for each part (cap, stalk, foot).
*   **material**: `fungus_loose_green` - The material used for collision and visual representation.
*   **offset\_x**, **offset\_y**: Position of each shape relative to its parent body.
*   **body\_id**: Unique identifier for each physics shape.

### PhysicsJoint2Component
Connects the various parts of the fungus together and to the environment.

*   **type**: `REVOLUTE_JOINT` for connecting fungus segments, `REVOLUTE_JOINT_ATTACH_TO_NEARBY_SURFACE` for anchoring to the ground.
*   **joint\_id**: Links joints to specific body IDs.
*   **body1\_id**, **body2\_id**: The physics bodies being connected.
*   **break\_force**, **break\_distance**: Thresholds at which the joint will break.

### MaterialInventoryComponent
Manages the internal materials and their behavior.

*   **on\_death\_spill**: `1` - The entity will spill its contents upon death.
*   **leak\_on\_damage\_percent**: `1` - The entity will leak materials when damaged.
*   **leak\_pressure\_min**, **leak\_pressure\_max**: Controls the pressure of the leaked material.
*   **kill\_when\_empty**: `1` - The entity is destroyed when its material inventory is depleted.
*   **count\_per\_material\_type**:
    *   **Material material="acid" count="1200"**: Contains 1200 units of "acid".

### DamageModelComponent
Handles damage and health of the entity.

*   **hp**: `0.8` - The entity's health points.
*   **blood\_material**: `slime_green` - The material that spills when damaged.
*   **blood\_sprite\_directional**, **blood\_sprite\_large**: Sprites used for blood splatters.
*   **damage\_multipliers**:
    *   **fire="40.0"**: Takes significantly more damage from fire.

### ExplodeOnDamageComponent
Defines the explosion behavior upon damage or death.

*   **explode\_on\_death\_percent**: `1` - Explodes when health reaches 0.
*   **physics\_body\_destruction\_required**: `0.25` - The entity's physics body must be at least 25% destroyed for an explosion.
*   **config\_explosion**: Contains detailed parameters for the explosion.
    *   **camera\_shake**: `40` - Intensity of camera shake during explosion.
    *   **explosion\_radius**: `55` - The radius of the explosion.
    *   **damage**: `2` - Damage dealt by the explosion.
    *   **particle\_effect**: `1` - Enables particle effects for the explosion.
    *   **physics\_explosion\_power**: `min="0.8", max="1.8"` - The force of the physics-based explosion.
    *   **spark\_material**: `acid` - The material of the sparks generated.
    *   **audio\_event\_name**: `explosions/slime` - The sound event played during the explosion.

### LightComponent
Adds a light source to the entity.

*   **radius**: `120` - The radius of the light.
*   **r**, **g**, **b**: Color components of the light (greenish-cyan).

### LuaComponent
Attaches a Lua script for custom behavior.

*   **script\_source\_file**: `data/scripts/props/physics_fungus.lua` - The script controlling the fungus's logic.
*   **execute\_every\_n\_frame**: `1` - The script executes every frame.

### AudioLoopComponent
Plays a looping sound effect.

*   **event\_name**: `materials/spray_fungus` - The sound event for spraying fungus.