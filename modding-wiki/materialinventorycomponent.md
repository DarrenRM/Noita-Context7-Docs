---
title: MaterialInventoryComponent
source: https://noita.wiki.gg/wiki/Documentation:MaterialInventoryComponent
category: modding-wiki
---

# MaterialInventoryComponent

This documentation page details the `MaterialInventoryComponent` in Noita, a crucial component for managing the materials an entity possesses. Understanding this component is vital for modders looking to create custom items, modify existing ones, or implement new mechanics that involve material collection and consumption.

## Overview

The `MaterialInventoryComponent` is responsible for tracking and managing the materials that an entity holds. This includes adding, removing, and checking for the presence of specific materials. It's fundamental for any mod that interacts with the game's material system, such as crafting, alchemy, or custom spell effects that consume or produce materials.

## Component Properties

The `MaterialInventoryComponent` has several properties that can be configured in the entity's XML definition.

### `max_items`

*   **Type:** Integer
*   **Description:** The maximum number of unique material stacks the inventory can hold. If this limit is reached, new materials cannot be added unless an existing one is removed.

### `initial_material_count`

*   **Type:** Integer
*   **Description:** The number of material slots that are initially filled when the entity spawns. This is often used to pre-fill an inventory with specific materials.

### `material_slots`

*   **Type:** List of `MaterialSlot` objects
*   **Description:** Defines the materials that are initially present in the inventory and their quantities.

#### `MaterialSlot` Object

Each `MaterialSlot` object within `material_slots` has the following properties:

*   `material`: The name of the material (e.g., "material_water", "material_lava").
*   `count`: The quantity of the material in this slot.

**Example:**

```xml
<MaterialInventoryComponent
    max_items="10"
    initial_material_count="2"
    >
    <material_slots>
        <MaterialSlot material="material_water" count="50" />
        <MaterialSlot material="material_slime" count="25" />
    </material_slots>
</MaterialInventoryComponent>
```

## Lua API Interaction

The `MaterialInventoryComponent` can be accessed and manipulated via the Lua API. This allows for dynamic control over an entity's material inventory during gameplay.

### Getting the Component

You can get the `MaterialInventoryComponent` from an entity using the `GetComponent` function.

```lua
local entity_id = GetUpdatedEntityID() -- Or any other way to get an entity ID
local inventory_component = EntityGetFirstComponent(entity_id, "MaterialInventoryComponent")

if inventory_component then
    -- Component found, proceed with operations
end
```

### Key Lua Functions

*   `EntityHasMaterial(entity_id, material_name)`: Checks if an entity possesses a specific material.
    *   **Parameters:**
        *   `entity_id`: The ID of the entity to check.
        *   `material_name`: The name of the material (e.g., "material_water").
    *   **Returns:** `true` if the entity has the material, `false` otherwise.

*   `EntityAddMaterial(entity_id, material_name, count)`: Adds a specified amount of a material to the entity's inventory.
    *   **Parameters:**
        *   `entity_id`: The ID of the entity.
        *   `material_name`: The name of the material to add.
        *   `count`: The quantity of the material to add.
    *   **Returns:** `true` if the material was successfully added, `false` otherwise (e.g., if the inventory is full).

*   `EntityRemoveMaterial(entity_id, material_name, count)`: Removes a specified amount of a material from the entity's inventory.
    *   **Parameters:**
        *   `entity_id`: The ID of the entity.
        *   `material_name`: The name of the material to remove.
        *   `count`: The quantity of the material to remove.
    *   **Returns:** `true` if the material was successfully removed, `false` otherwise (e.g., if the entity doesn't have enough of the material).

*   `EntityGetMaterialCount(entity_id, material_name)`: Returns the current count of a specific material in the entity's inventory.
    *   **Parameters:**
        *   `entity_id`: The ID of the entity.
        *   `material_name`: The name of the material.
    *   **Returns:** The count of the material, or `0` if the entity does not have the material.

*   `EntityGetMaterialInventory(entity_id)`: Returns a table containing all materials and their counts in the entity's inventory.
    *   **Parameters:**
        *   `entity_id`: The ID of the entity.
    *   **Returns:** A Lua table where keys are material names and values are their counts.

**Example Usage:**

```lua
local player_id = GetPlayer()

-- Check if the player has water
if EntityHasMaterial(player_id, "material_water") then
    print("Player has water!")
end

-- Add 100 units of slime to the player
EntityAddMaterial(player_id, "material_slime", 100)

-- Remove 50 units of lava from the player
EntityRemoveMaterial(player_id, "material_lava", 50)

-- Get the current count of gold
local gold_count = EntityGetMaterialCount(player_id, "material_gold")
print("Player has " .. gold_count .. " gold.")

-- Get the entire inventory
local inventory = EntityGetMaterialInventory(player_id)
for material, count in pairs(inventory) do
    print("Material: " .. material .. ", Count: " .. count)
end
```

## Common Materials

Here is a list of some commonly used material names. This list is not exhaustive, and many more materials exist within the game's files.

| Material Name       | Description                               |
| :------------------ | :---------------------------------------- |
| `material_water`    | Water                                     |
| `material_lava`     | Lava                                      |
| `material_slime`    | Slime                                     |
| `material_blood`    | Blood                                     |
| `material_poison`   | Poison                                    |
| `material_oil`      | Oil                                       |
| `material_fire`     | Fire (often used for effects)             |
| `material_ice`      | Ice                                       |
| `material_gold`     | Gold                                      |
| `material_fungus`   | Fungus                                    |
| `material_mud`      | Mud                                       |
| `material_acid`     | Acid                                      |
| `material_swamp`    | Swamp material                            |
| `material_perk`     | Used for perk-related effects             |
| `material_mana`     | Mana (for spellcasting)                   |
| `material_health`   | Health (for healing effects)              |
| `material_stamina`  | Stamina (for movement/actions)            |
| `material_explosion`| Used to trigger explosion effects         |
| `material_damage`   | Used to apply damage effects              |
| `material_healing`  | Used to apply healing effects             |
| `material_teleport` | Used for teleportation effects            |
| `material_light`    | Light source material                     |
| `material_darkness` | Darkness material                         |
| `material_food`     | Food item material                        |
| `material_meat`     | Meat material                             |
| `material_bone`     | Bone material                             |
| `material_rock`     | Rock material                             |
| `material_sand`     | Sand material                             |
| `material_grass`    | Grass material                            |
| `material_wood`     | Wood material                             |
| `material_metal`    | Metal material                            |
| `material_crystal`  | Crystal material                          |
| `material_gem`      | Gem material                              |
| `material_ether`    | Ether material (often for magical effects)|
| `material_spirit`   | Spirit material                           |
| `material_shadow`   | Shadow material                           |
| `material_light_orb`| Light orb material                        |
| `material_dark_orb` | Dark orb material                         |
| `material_chaos`    | Chaos material                            |
| `material_order`    | Order material                            |
| `material_time`     | Time material                             |
| `material_space`    | Space material                            |
| `material_life`     | Life material                             |
| `material_death`    | Death material                            |

**Note:** The exact names and availability of materials can vary between game updates and mods. It's always a good practice to check the game's internal files or use modding tools to discover material names.

## Modding Examples

### Creating a Potion that Heals and Adds Water

This example shows how to create an item that, when used, heals the player and adds a certain amount of water to their inventory.

**XML Definition (e.g., in `data/items/my_potion.xml`):**

```xml
<entity name="my_potion" tags="consumable,item">
    <item
        name="My Healing Potion"
        description="Restores health and adds water."
        >
        <sprite texture="mods/my_mod/sprites/potion.png" />
        <item_material
            material_name="material_water"
            material_count="50"
            />
        <item_use_action
            action="HEAL"
            amount="20"
            />
        <MaterialInventoryComponent
            max_items="1"
            initial_material_count="1"
            >
            <material_slots>
                <MaterialSlot material="material_water" count="50" />
            </material_slots>
        </MaterialInventoryComponent>
    </item>
</entity>
```

**Lua Script (e.g., in `mods/my_mod/scripts/items/my_potion.lua`):**

```lua
-- This script might be attached to the item to handle its use logic
local function on_use(entity_id, item_id)
    local player_id = GetPlayer()
    local potion_component = EntityGetFirstComponent(item_id, "MaterialInventoryComponent")

    if potion_component then
        -- Get the material from the potion itself
        local inventory = EntityGetMaterialInventory(item_id)
        for material, count in pairs(inventory) do
            EntityAddMaterial(player_id, material, count)
            EntityRemoveMaterial(item_id, material, count) -- Remove from potion
        end
    end

    -- Heal the player
    EntityHeal(player_id, 20)

    -- Remove the potion after use
    EntityKill(item_id)
end

-- Register the use action if not handled by XML directly
-- This is an example, actual registration might depend on how you structure your item scripts.
-- For simple cases like this, the XML `item_use_action` might be sufficient.
```

### Custom Spell that Consumes Materials

This example outlines how a custom spell might consume specific materials from the player's inventory to cast.

**XML Definition (e.g., in `data/spells/my_consume_spell.xml`):**

```xml
<spell name="My Consume Spell" tags="spell,consumable">
    <sprite texture="mods/my_mod/sprites/consume_spell.png" />
    <spell_material
        material_name="material_mana"
        material_count="10"
        />
    <spell_material
        material_name="material_gold"
        material_count="5"
        />
    <spell_effect
        effect_type="CUSTOM"
        script_path="mods/my_mod/scripts/spells/consume_spell.lua"
        />
</spell>
```

**Lua Script (e.g., in `mods/my_mod/scripts/spells/consume_spell.lua`):**

```lua
-- This script would be executed when the spell is cast
local function on_cast(spell_entity_id, caster_entity_id)
    local required_materials = {
        material_mana = 10,
        material_gold = 5
    }

    local can_cast = true
    for material, count in pairs(required_materials) do
        if not EntityHasMaterial(caster_entity_id, material) or EntityGetMaterialCount(caster_entity_id, material) < count then
            can_cast = false
            break
        end
    end

    if can_cast then
        -- Consume materials
        for material, count in pairs(required_materials) do
            EntityRemoveMaterial(caster_entity_id, material, count)
        end

        -- Perform the spell's actual effect here
        print("Spell cast successfully! Consumed materials.")
        -- Example: Spawn a projectile, apply an effect, etc.
        -- EntityLoad("mods/my_mod/entities/my_projectile.xml", EntityGetTransform(caster_entity_id))
    else
        print("Not enough materials to cast the spell.")
        -- Optionally, provide feedback to the player
    end
end
```

## Further Resources

*   [Lua API](https://noita.wiki.gg/wiki/Modding:_Lua_API)
*   [Entity Components](https://noita.wiki.gg/wiki/Documentation:Entity_Components)
*   [Material System Overview](https://noita.wiki.gg/wiki/Documentation:Material_System)