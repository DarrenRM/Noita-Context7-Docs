---
title: Modding: Tags System
source: https://noita.wiki.gg/wiki/Modding:_Tags_System
category: modding-wiki
---

# Modding: Tags System

Noita utilizes a tag system to assign identifiers to components and entities. This system allows for efficient querying and management of game objects, making it a crucial aspect of modding for tracking and manipulating entities. While there are some special tags, new tags are dynamically allocated as they are used, meaning mods can invent their own tags for convenience.

## Internals of the Tag System

The game maintains a list of objects associated with each unique tag. Conversely, every entity and component also stores a record of the tags assigned to it. This bidirectional relationship enables optimized operations such as `EntityGetInRadiusWithTag` and `ComponentHasTag`.

For example, when using `EntityGetInRadiusWithTag`, the game doesn't need to iterate through every entity in the game. Instead, it first checks if the specified tag has been allocated. If it has, the game then only examines the entities within that tag's associated list, significantly improving performance by avoiding checks on entities that do not possess the tag.

## Limitations and Considerations

Each component and entity system has its own dedicated tag manager. These tag managers have a limit of 512 unique tags.

When a new, previously unseen tag is applied to a component or entity, it consumes one slot in the respective tag manager's available space. Tags are **permanent** and cannot be deallocated. Even if a tag is removed from all objects, or if a new game run is started, the tag manager will retain the tag in its memory, counting towards the 512-tag limit. Tags are only cleared from memory upon restarting the game.

Exceeding the entity tag manager's limit will cause Noita to crash. The component tag manager is slightly more forgiving; it may allow the game to continue running but will log errors to `logger.txt`. While the game might not immediately crash, functionality will be impaired as tags cannot be assigned correctly.

### Modding Advice

Given that tags are a finite, shared resource, it is essential to consider alternatives before introducing a new tag.

*   **Avoid Tags When Possible:** Mods should refrain from using tags if the same functionality can be achieved using simpler methods, such as entity names or Lua tables.
*   **Do Not Create Dynamic Tags:** Dynamically generating tags based on runtime conditions (e.g., entity position) is strongly discouraged as it rapidly depletes the tag limit.

    ```lua
    -- BAD PRACTICE: This will gradually allocate more tags until the game breaks
    spidey = EntityLoad("mods/mymod/spidey.xml", x, y)
    EntityAddTag(spidey, "mymod_home_chunk" .. math.floor(x/100) .. "_" .. math.floor(y/100))
    -- This creates tags like:
    -- mymod_home_chunk0_0
    -- mymod_home_chunk1_5
    -- mymod_home_chunk2_0
    -- mymod_home_chunk2_3
    -- ... and so on
    ```

*   **Reuse Existing Tags:** When possible, mods should reuse tags from the base game or other mods if they already serve a similar purpose.

    ```lua
    -- Instead of creating a new 'fish' tag, reuse the 'mortal' tag
    function get_nearby_fish(x, y)
        local mortals = EntityGetInRadiusWithTag(x, y, 200, "mortal")
        local fish = {}
        for _, entity in ipairs(mortals) do
            if EntityGetFirstComponent(entity, "AdvancedFishAIComponent") then
                table.insert(fish, entity)
            end
        end
        return fish
    end
    ```