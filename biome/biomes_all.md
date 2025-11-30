---
title: _biomes_all
category: biome
source: https://github.com/NathanSnail/noitadata/tree/main/data/biome/_biomes_all.xml
---

# _biomes_all

This file, `_biomes_all.xml`, serves as a central registry for all the different biome types that can be generated within the game Noita. It acts as a lookup table, mapping specific color values and height indices to the actual biome definition files. When the game needs to decide what kind of terrain to generate at a particular location, it consults this file to determine which biome definition to load based on these parameters. Essentially, it's the master list that tells the game engine how to interpret the raw biome data and translate it into the visually distinct and gameplay-relevant areas players explore.

## File Structure

The `_biomes_all.xml` file is structured as an XML document. The root element is `<BiomesToLoad>`, which contains global attributes and then a series of `<Biome>` elements.

*   **`<BiomesToLoad>`**: This is the main container for all biome definitions.
    *   `biome_image_map`: An attribute pointing to an image file (`data/biome_impl/biome_map.png`) that likely serves as a visual reference or a texture atlas for biome elements.
    *   `biome_offset_y`: An attribute that seems to define a vertical offset, possibly for rendering or placement purposes.

*   **`<Biome>`**: Each `<Biome>` element represents a specific instance or variation of a biome.
    *   `biome_filename`: This attribute is crucial, as it specifies the path to the individual XML file that contains the detailed definition of that particular biome (e.g., `data/biome/hills.xml`).
    *   `height_index`: This attribute assigns a numerical value representing the vertical layer or depth at which this biome is intended to appear. Lower numbers generally correspond to higher elevations or shallower areas, while higher numbers indicate deeper or lower areas.
    *   `color`: This attribute defines a hexadecimal color code (e.g., `ff36d517`). This color is likely used by the game's internal biome generation system to identify and select specific biomes based on a color map or during the generation process. The `ff` prefix typically indicates full opacity in RGBA color formats.

Comments (`<!-- ... -->`) are used within the file to provide explanations, such as indicating the range of `height_index` values or clarifying the purpose of certain biome entries.

## Key Patterns

Several patterns emerge from the sampled content:

*   **Height-Based Organization**: The `height_index` attribute is a primary organizational principle. Biomes are grouped by their intended vertical placement, suggesting a layered world generation system. For example, `height_index="0"` appears frequently for "ground layer" biomes, while higher indices like `10`, `11`, `12`, and `13` are associated with deeper or more specific structures like solid walls, deserts, mountains, and pyramids.
*   **Color as Identifier**: The `color` attribute acts as a unique identifier for each specific biome entry. This implies that the game might use a color-coded map or a color-based lookup mechanism to determine which biome to spawn. Different colors are assigned even to biomes that share the same `biome_filename` and `height_index`, suggesting variations or specific instances of a biome type.
*   **Modular Biome Definitions**: The `biome_filename` attribute points to separate XML files. This modular design allows for complex biome definitions to be managed independently, making the data more organized and easier to modify or expand.
*   **Categorization by Theme**: While not explicitly tagged, the `biome_filename` often hints at the biome's theme. Examples include `hills`, `snowcave`, `coalmine`, `temple`, `desert`, and `pyramid`, indicating distinct environmental zones within the game.
*   **Specialized Entries**: Some entries appear to be for specific purposes, such as `empty.xml` or `temple_altar_empty.xml`, which are noted in comments as being used for things like "new\_daily\_run." This suggests that not all biome entries are for standard world generation but can also serve gameplay-specific functions.
*   **Variations of Core Biomes**: The presence of multiple entries with similar `biome_filename` but different `color` attributes (e.g., `hills.xml` with two different colors) indicates that the game supports variations or sub-types of a core biome, potentially affecting visual appearance or minor gameplay elements.

## Sample Entries

Here are a few representative examples from the sampled content:

1.  **Basic Ground Biome:**
    ```xml
    <Biome 
        biome_filename="data/biome/hills.xml" 
        height_index="0"
        color="ff36d517" >
    </Biome>
    ```
    This entry defines a "hills" biome intended for the ground layer (`height_index="0"`). The specific color `ff36d517` is associated with this particular instance of the hills biome.

2.  **Deep Structure Biome:**
    ```xml
    <Biome 
        biome_filename="data/biome/solid_wall.xml" 
        height_index="10"
        color="ff3d3d3d" >
    </Biome>
    ```
    This entry represents a "solid wall" biome, likely a structural element found at a deeper level (`height_index="10"`). The color `ff3d3d3d` is assigned to this specific wall type.

3.  **Temple Variation:**
    ```xml
    <Biome 
        biome_filename="data/biome/temple_altar_right.xml"
        height_index="0"
        color="ff93cb4e" >
    </Biome>
    ```
    This defines a specific part of a temple, the "temple\_altar\_right," also at `height_index="0"`. The color `ff93cb4e` distinguishes this particular altar variant.

## Reference

This file contains 1072 lines. For complete data, see the [full source](https://github.com/NathanSnail/noitadata/tree/main/data/biome/_biomes_all.xml).

---