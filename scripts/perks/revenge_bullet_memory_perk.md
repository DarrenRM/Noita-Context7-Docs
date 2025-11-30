---
title: Revenge Bullet Memory Perk
category: scripts/perks
---

# Revenge Bullet Memory Perk

This perk allows the player to "remember" the last projectile that hit them and fire it back.

## Core Functionality

The perk identifies the projectile that last damaged the player. It then extracts the projectile's file path from its `VariableStorageComponent` and stores it in the player's own `VariableStorageComponent` under the key "projectile_memory". This stored projectile file can then be used by other game mechanics (e.g., a wand or another perk) to replicate the projectile.

## Key Attributes and Elements

*   **`entity_id`**: The unique identifier for the player entity.
*   **`projectiles`**: A list of projectile entities found within a radius around the player.
*   **`projectile_id`**: The ID of the projectile that last hit the player.
*   **`shooter_id`**: The ID of the entity that fired the projectile. This is used to ensure the projectile that hit the player was not fired by the player themselves.
*   **`VariableStorageComponent`**: A component used to store custom variables on entities.
    *   **`projectile_file`**: A variable within the projectile's `VariableStorageComponent` that holds the string path to the projectile's definition file.
    *   **`projectile_memory`**: A variable within the player's `VariableStorageComponent` where the `projectile_file` string is stored.

## Logic Flow

1.  **Get Player Entity**: The script first obtains the `entity_id` of the player.
2.  **Find Nearby Projectiles**: It searches for any entities tagged as "projectile" within a small radius of the player.
3.  **Identify Last Hit Projectile**: The script iterates through the found projectiles. For each projectile, it checks the `mWhoShot` component to determine if the projectile was fired by the player. If it was *not* fired by the player, that projectile is considered the "last hit" and its `projectile_id` is stored.
4.  **Extract Projectile File Path**: If a valid `projectile_id` is found, the script accesses its `VariableStorageComponent`. It looks for a variable named "projectile\_file" and retrieves its string value, which is the path to the projectile's definition.
5.  **Store Projectile Memory**: If a projectile file path was successfully retrieved, the script then accesses the player's own `VariableStorageComponent`. It updates or creates a variable named "projectile\_memory" and sets its value to the retrieved projectile file path.

## Example Usage (Conceptual)

This perk's output (`projectile_memory`) would typically be consumed by a wand or another perk. For instance, a wand might have a component that checks for the "projectile\_memory" variable on the player. If found, it would then spawn a projectile using that stored file path instead of its default projectile.

```lua
-- Conceptual example of how another system might use the perk's output
local player_entity = GetPlayerEntity() -- Assume this gets the player's entity ID
local storages = EntityGetComponent(player_entity, "VariableStorageComponent")
local remembered_projectile_path = ""

if storages then
    for _, comp in ipairs(storages) do
        local name = ComponentGetValue2(comp, "name")
        if name == "projectile_memory" then
            remembered_projectile_path = ComponentGetValue2(comp, "value_string")
            break
        end
    end
end

if string.len(remembered_projectile_path) > 0 then
    -- Spawn a projectile using the remembered path
    -- Example: EntityLoad(remembered_projectile_path, player_x, player_y)
end
```