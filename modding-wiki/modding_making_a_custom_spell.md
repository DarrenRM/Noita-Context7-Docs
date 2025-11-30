---
title: Modding: Making a Custom Spell
source: https://noita.wiki.gg/wiki/Modding:_Making_a_custom_spell
category: modding-wiki
---

# Modding: Making a Custom Spell

This documentation guides you through the process of creating and implementing custom spells in Noita using mods. Understanding how to define, register, and customize spells is crucial for expanding the game's magic system and creating unique gameplay experiences.

## Registering Your New Spell

To create a custom spell, you'll define it within a Lua file and then register it with the game.

1.  **Define Your Spell:**
    Add a new file to your mod (e.g., `files/actions.lua`). In this file, you'll define your custom spells by appending to the `actions` table provided by the base game Lua.

    ```lua
    table.insert(actions,
         {
           id                 = "MY_CUSTOM_SPELL",
           name               = "My Fancy Spell",
           description        = "Fancy spell doing fancy things",
           sprite             = "data/ui_gfx/gun_actions/air_bullet.png",
           type               = ACTION_TYPE_PROJECTILE,
           spawn_level        = "1,2",
           spawn_probability  = "1,1",
           price              = 80,
           mana               = 5,
           max_uses           = 120,  -- optional
           custom_xml_file = "data/entities/misc/custom_cards/torch_electric.xml", -- optional
           action = function()
             add_projectile("data/entities/projectiles/deck/light_bullet_air.xml")

             -- Examples for triggers:
             --add_projectile_trigger_hit_world("data/entities/projectiles/deck/light_bullet.xml", 1)
             --add_projectile_trigger_timer("data/entities/projectiles/deck/light_bullet.xml", 10, 1)
             --add_projectile_trigger_death("data/entities/projectiles/deck/mine.xml", 1)
           end,
         }
    )
    ```
    *   **ID:** Must be all uppercase.

2.  **Reference Your Definition File:**
    Add the following line to the very beginning of your `init.lua`, referencing the file you just created:

    ```lua
    ModLuaFileAppend("data/scripts/gun/gun_actions.lua", "mods/<MY_FANCY_MOD>/files/actions.lua")
    ```

Your new spell should now be available in the game, initially with default values similar to the "light air bullet" example.

## Spawning Custom Spells

Once your spell is registered, you can test it by adding it to a custom wand or spawning it directly via Lua.

```lua
-- Easiest place to test new stuff, in reality the code could be anywhere.
function OnPlayerSpawned(player)
  local x, y = EntityGetTransform(player)
  CreateItemActionEntity("MY_CUSTOM_SPELL", x+20, y)
end
```

Be aware that the `CreateItemActionEntity` function does not appear to print or return errors, so typos in the `SPELL_ID` can be difficult to debug.

## Customizing Your New Spell

The fields within the `actions` table offer various customization options:

*   **`sprite`**: This defines the image of the spell *card* (the item you pick up in the world), not the projectile itself.
*   **`type`**: Can be one of the following valid values:
    *   `ACTION_TYPE_PROJECTILE`
    *   `ACTION_TYPE_STATIC_PROJECTILE`
    *   `ACTION_TYPE_MODIFIER`
    *   `ACTION_TYPE_DRAW_MANY`
    *   `ACTION_TYPE_PASSIVE`
    *   `ACTION_TYPE_MATERIAL`
    *   `ACTION_TYPE_UTILITY`
    *   `ACTION_TYPE_OTHER`
*   **`max_uses`**: This field is optional. If omitted or set to `-1`, the spell will have unlimited uses.
*   **`action`**: This function is the core of your spell's behavior. It's called when the spell is cast and can perform almost any action achievable with Lua.
    *   Here, you register any projectiles to be fired (which must be defined separately via XML).
    *   You can also register projectile triggers such as `hit_world`, `timer`, or `death`.
    *   This function can be left empty for passive spells like shields.
*   **`custom_xml_file`**: This optional field is rarely needed but extremely useful. It defines the XML for a custom *card*.
    *   Beyond controlling the world item, cards can also affect the wand itself, adding custom effects (e.g., the electric torch).
    *   This can be used to make spell items physics objects, change their glow, and more.
    *   If left empty, the default file `data/entities/misc/custom_cards/action.xml` is used. The `ItemActionComponent::action_id` reference in this default file is filled in silently by the game for each action.

For a comprehensive list of all actions and excellent learning material, refer to `data/scripts/gun/gun_actions.lua`.

## Creating a Custom Projectile

To create a custom projectile for your spell, you'll need to define it using XML.

*   Refer to the files in `data/entities/projectiles/` for examples.
*   Consult [Enums: RAGDOLL FX](https://noita.wiki.gg/wiki/Modding:_Enums#RAGDOLL_FX) for a list of effects your projectile can have.

**Note:** The game applies certain behaviors to some projectiles based on Entity tags defined in their `.xml` files. The game searches for precise strings within these tags, not entire words. For instance, using the tag `"black_hole_custom"` will still correctly identify the projectile as a black hole type.

This section is currently a Work In Progress (WIP).