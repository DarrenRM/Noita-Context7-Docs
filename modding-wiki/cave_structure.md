---
title: Cave Structure
source: https://noita.wiki.gg/wiki/Documentation:CaveStructure
category: modding-wiki
---

# Cave Structure

This documentation explains the internal structure of Noita's caves, focusing on how they are defined and generated. Understanding these structures is crucial for modders who wish to create custom biomes, alter existing cave generation, or introduce new environmental elements.

## Cave Structure Definition

Noita's caves are defined by a hierarchical structure that dictates their appearance, contents, and generation logic. This structure is primarily managed through XML files, which are then interpreted by the game engine.

### Core Components of Cave Structure

The fundamental building blocks of cave structures include:

*   **Biomes:** These are the overarching themes and environments that define a particular area of the game world. Each biome has a unique set of properties and associated cave structures.
*   **Cave Structures:** These are the actual physical layouts of caves, including walls, floors, and the placement of various entities and environmental features.
*   **Entities:** These are the objects placed within the cave structures, such as enemies, pickups, decorations, and interactive elements.
*   **Materials:** The types of blocks that form the cave walls and floors, influencing their properties (e.g., destructibility, elemental effects).

### XML Structure for Cave Definitions

Cave structures are defined in XML files, typically located within the `data/biome/` directory of the game's assets. These files describe the various elements that make up a biome and its associated cave generation.

A simplified example of an XML structure might look like this:

```xml
<CaveSet>
    <Cave name="example_cave">
        <Tags>
            <Tag name="common"/>
            <Tag name="forest"/>
        </Tags>
        <Cells>
            <Cell x="0" y="0" material="stone"/>
            <Cell x="1" y="0" material="dirt"/>
            <!-- More cells defining the cave layout -->
        </Cells>
        <Entities>
            <Entity name="enemy_goblin" position="5,5"/>
            <Entity name="pickup_health" position="10,2"/>
            <!-- More entities -->
        </Entities>
    </Cave>
    <!-- More cave definitions -->
</CaveSet>
```

**Key elements within the XML:**

*   `<CaveSet>`: The root element for a collection of cave definitions.
*   `<Cave name="...">`: Defines a specific cave structure with a unique name.
*   `<Tags>`: Assigns tags to the cave structure, which can be used for filtering during generation.
*   `<Cells>`: Defines the individual blocks (cells) that make up the cave's geometry, specifying their material.
*   `<Entities>`: Lists the entities to be spawned within this cave structure, along with their positions.

## Biome Mappings and Generation

The game engine uses biome definitions to determine which cave structures are eligible to spawn in different areas of the world. This mapping is crucial for creating diverse and thematically consistent environments.

### Biome Definition Files

Biome definitions are also typically found in XML files, often within `data/biome/`. These files link biomes to specific cave structures and define their generation parameters.

### Biome to Cave Structure Association

The following table illustrates a conceptual mapping between biomes and the types of cave structures they might utilize. This is a simplified representation, and actual game files contain more complex relationships and parameters.

| Biome Name       | Associated Cave Structure Types | Primary Materials | Common Entities                               |
| :--------------- | :------------------------------ | :---------------- | :-------------------------------------------- |
| Forest           | `forest_cave`, `ruins_cave`     | Dirt, Stone       | Goblins, Spiders, Mushrooms                   |
| Caves            | `standard_cave`, `mining_cave`  | Stone, Rock       | Bats, Slimes, Ore Veins                       |
| Snow             | `ice_cave`, `tundra_cave`       | Ice, Snow         | Ice Golems, Snowmen, Frozen Enemies           |
| Desert           | `sand_cave`, `oasis_cave`       | Sand, Rock        | Scorpions, Vultures, Cacti                    |
| Underground Lake | `water_cave`, `aquatic_cave`    | Water, Stone      | Fish, Aquatic Enemies, Coral                  |

### Generation Parameters

Biome definitions also include parameters that influence how cave structures are generated, such as:

*   **Frequency:** How often a particular cave structure is likely to appear within a biome.
*   **Size constraints:** Minimum and maximum dimensions for generated caves.
*   **Connectivity:** Rules for how different cave sections should connect.
*   **Environmental effects:** Properties like ambient temperature, light levels, and special hazards.

## Modding Cave Structures

Modders can leverage this understanding to create their own cave structures or modify existing ones.

### Creating Custom Cave Structures

1.  **Define your cave in XML:** Create a new XML file (or add to an existing one) within your mod's `data/biome/` directory. Define your cave structure with unique `name` attributes.
2.  **Specify cells and entities:** Use `<Cells>` and `<Entities>` tags to define the physical layout and contents of your cave.
3.  **Assign tags:** Use `<Tags>` to categorize your cave structure, making it eligible for specific biomes or generation rules.

### Modifying Existing Cave Structures

You can override or extend existing cave structure definitions by placing your modified XML files in your mod's `data/biome/` directory with the same file names and structure as the original game files.

### Referencing Lua API

For more dynamic generation or interaction with cave structures, you will likely need to use the [Lua API](https://noita.wiki.gg/wiki/Modding:_Lua_API). Functions within the API allow you to:

*   Spawn entities programmatically.
*   Modify terrain materials.
*   Trigger environmental effects.
*   Control game logic based on cave properties.

## Important File Paths

*   `data/biome/`: Contains XML files defining biomes and cave structures.
*   `data/entities/`: Contains definitions for various entities that can be placed in caves.

## Further Resources

*   [Modding:Lua API](https://noita.wiki.gg/wiki/Modding:_Lua_API)
*   [Modding:Entities](https://noita.wiki.gg/wiki/Modding:_Entities)