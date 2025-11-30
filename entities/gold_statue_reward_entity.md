---
title: Gold Statue Reward Entity
category: entities
---

# Gold Statue Reward Entity

This entity represents a gold statue that can be dropped as a reward, likely from a boss. It's designed to be a physical object in the game world with visual and interactive components.

## Key Components

### `UIInfoComponent`
This component defines the in-game name for the reward.

*   **`name`**: `$reward_gold_statue` - The localization key for the reward's name.

### `PhysicsBodyComponent`
Handles the physical properties of the gold statue.

*   **`_tags`**: `enabled_in_world` - Ensures the physics are active when the entity is in the game world.
*   **`allow_sleep`**: `1` - Allows the physics body to go to sleep when inactive to save performance.
*   **`is_bullet`**: `1` - Indicates it's a projectile-like object, though likely not fired.
*   **`auto_clean`**: `1` - The entity will be automatically removed when it's no longer needed.
*   **`hax_fix_going_through_ground`**: `1` - A specific fix to prevent it from falling through the ground.

### `PhysicsImageShapeComponent`
Defines the visual representation and collision shape of the statue.

*   **`body_id`**: `1` - Links this shape to the `PhysicsBodyComponent` with `uid="1"`.
*   **`image_file`**: `data/entities/animals/boss_centipede/rewards/gold_reward_sprite.png` - The sprite used for the statue.
*   **`material`**: `metal_prop` - The material type, influencing its physical interactions.

### `ItemComponent`
Marks this entity as an item that can be picked up.

*   **`item_name`**: `$reward_gold_statue` - The localization key for the item's name, matching the UI.
*   **`play_spinning_animation`**: `0` - The statue does not play a spinning animation when spawned.

### `LuaComponent`
Attaches custom Lua scripting to the entity.

*   **`script_item_picked_up`**: `data/entities/animals/boss_centipede/rewards/gold_reward.lua` - The script executed when the item is picked up. This script likely handles the logic for what happens when the player collects the reward.

### `LightComponent`
Adds a light source to the entity.

*   **`_tags`**: `enabled_in_world` - The light is active when the entity is in the game world.
*   **`r`, `g`, `b`**: `255`, `255`, `255` - Sets the light color to white.
*   **`radius`**: `64` - The range of the light.
*   **`fade_out_time`**: `0.75` - How long it takes for the light to fade out.