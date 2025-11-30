---
title: Modding: Making a Custom Spritesheet
source: https://noita.wiki.gg/wiki/Modding:_Making_a_custom_spritesheet
category: modding-wiki
---

# Modding: Making a Custom Spritesheet

This documentation guides you through the process of creating and customizing spritesheets for Noita mods. Understanding spritesheets is crucial for modders who wish to introduce new character visuals, animations, or modify existing ones, significantly enhancing the visual variety and depth of your mods.

## Creating a Custom Player Character

This section details the components required to create a custom player character's visual assets. The player character is used as a primary example due to its extensive animation set.

### Animations Spritesheet

The main visual assets for a character are stored in a PNG file. For the player character, this is located at `data/enemies_gfx/player.png`.

*   Each row in the spritesheet represents a distinct animation.
*   Animations can have unique dimensions, frame counts, speeds, and vertical positions. These do not need to be consistent across different animations but must match the specifications in the Metadata XML.
*   A single animation can be referenced by multiple names in the metadata, allowing it to function as different animations within the game.
*   The player spritesheet is one of the largest in Noita, containing numerous animations, though not all are actively used or necessary for basic functionality.

### Hotspot Spritesheet

This is a PNG file, typically located at `data/enemies_gfx/player_hotspots.png`, used to define specific points on a character for attachments or actions.

*   **Purpose:** Defines positions for extra attachments like physics-simulated capes, hand positions for holding wands, or general points for actions like shooting or crouching.
*   **Content:** Contains only the hotspot pixels, without any other graphical elements. Alternatively, hotspots can be defined using simple x/y coordinates directly in the entity file, which is more common for wands.
*   **Color Matching:** Each hotspot has a specific color defined by a hex code. These must precisely match the values specified in the Metadata XML.
*   **Dimensions:** Must exactly match the dimensions of the main animations spritesheet. It can be overlaid on the main spritesheet as a separate layer during editing and then saved independently.
*   **Definition:** Hotspot entities are linked in the player entity's XML file (`data/entities/player_base.xml`), while their colors are defined in the spritesheet's Metadata XML.

### Stains Spritesheet

This spritesheet, usually found at `data/enemies_gfx/player_uv_src.png`, is used for generating UV maps for character textures.

*   **Location:** Must be in the same directory as the main animations spritesheet.
*   **Dimensions:** Must exactly match the dimensions of the main animations spritesheet.
*   **UV Generation:** To generate UV maps for custom sprites, you need to include the following line in your `init.lua`:
    ```lua
    ModDevGenerateSpriteUVsForDirectory( "data/enemies_gfx" )
    ```
    This command should point to the directory containing the sprites you want to generate UVs for.
*   **Output:** When the game is run with `noita_dev.exe`, the generated UV maps will be placed in your mod's `data/generated/` directory.
*   **Applicability:** This is primarily relevant when creating a new character with a distinct shape. For simple recoloring of existing assets (like a character's robes), the default stains will likely suffice.

### Metadata XML

This XML file, typically `data/enemies_gfx/player.xml`, defines the properties and behaviors of the animations within the spritesheet.

*   **Animation Events:** Animations can have associated events, such as "kick" or "throw." These events are critical for the character's functionality and can be triggered manually via Lua scripting using functions like `GamePlayAnimation(player_entity, "kick", 10)`.

### Ragdoll Folder

This folder, located at `data/ragdolls/player/*`, contains the assets for the character's ragdoll physics.

*   **Contents:** Consists of individual image files for each body part and a single text file listing the file paths of all these body parts.
*   **Size:** Ragdoll files must be the exact same size as the "reference frame," which is typically the first frame of the first animation in your spritesheet.
*   **Flexibility:** You can include any number of ragdoll parts.
*   **Joint Generation:** Joints between ragdoll parts are automatically created based on overlapping pixels. To ensure body parts remain connected (e.g., to prevent a character from falling apart when drowning), there must be at least one overlapping pixel between the parts intended to be joined.

### Bonus: Cape Color

Some characters, including the player, have a cape that can be visually modified. This is often achieved through Lua scripting.

*   **Implementation:** The cape is typically a child entity attached to the player. A common place to modify its appearance is within the `init.lua` file, specifically in the `OnPlayerSpawned` callback function.

    ```lua
    function OnPlayerSpawned(player)
        for _, child in ipairs(EntityGetAllChildren(player)) do
            if EntityGetName(child) == "cape" then
                local cape_verlet = EntityGetFirstComponentIncludingDisabled(child, "VerletPhysicsComponent")
                ComponentSetValue2(cape_verlet, "cloth_color", 0xFF0011BB)
                ComponentSetValue2(cape_verlet, "cloth_color_edge", 0xFF0011BB)
            end
        end
    end
    ```
*   **Color Format:** Noita typically uses "ABGR" (Alpha, Blue, Green, Red) for color definitions, which is the reverse of the common "RGBA" format seen in most graphics software. In the example above:
    *   Alpha: `FF`
    *   Blue: `00`
    *   Green: `11`
    *   Red: `BB`

## Tying Everything Together

When modifying existing character spritesheets or introducing new ones, you have two primary methods for integrating these assets into the game:

1.  **In-Place Replacement:**
    *   Replace the original files directly within the `data/` folder.
    *   This method is generally suitable for simple player character mods where conflicts with other mods are unlikely, as only one such mod would typically be active.

2.  **Manual Setting via Lua:**
    *   Define and load assets manually using Lua scripting in your `init.lua` file.
    *   This approach often offers better compatibility with other mods.
    *   Refer to the example mod `mods/starting_loadouts` for a practical demonstration of this technique.

If you are creating an entirely new character, it is recommended to place your custom files within the `files/` directory of your mod, organizing them in a structure that best suits your needs.