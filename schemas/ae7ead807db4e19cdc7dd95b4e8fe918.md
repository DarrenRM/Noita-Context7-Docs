---
title: ae7ead807db4e19cdc7dd95b4e8fe918
category: schemas
source: https://github.com/NathanSnail/noitadata/tree/main/data/schemas/ae7ead807db4e19cdc7dd95b4e8fe918.xml
---

# ae7ead807db4e19cdc7dd95b4e8fe918

This XML file, identified by the hash `ae7ead807db4e19cdc7dd95b4e8fe918`, defines a schema for game data within Noita. It appears to be a foundational file that outlines the structure and types of various game components and their associated variables. These schemas are crucial for the game engine to understand and interpret the data associated with entities, behaviors, and game mechanics. By defining these structures, the game can correctly load, process, and utilize all the elements that make up the Noita experience, from enemy AI to environmental interactions.

## File Structure

The file is structured as a series of `<Component>` elements, each representing a distinct functional part of a game entity or system. Within each `<Component>`, there are `<Var>` elements that define individual properties or variables.

*   **`<Schema>`:** The root element, containing a `hash` attribute that uniquely identifies this schema.
*   **`<Component>`:** Represents a specific component or module within the game's architecture. It has a `component_name` attribute that names the component (e.g., `AIAttackComponent`, `AIComponent`, `LightningComponent`).
*   **`<Var>`:** Defines a variable or property within a component. Each `<Var>` element has the following attributes:
    *   `name`: The name of the variable (e.g., `use_probability`, `min_distance`, `sprite_lightning_file`).
    *   `size`: The size of the variable in bytes.
    *   `type`: The data type of the variable (e.g., `int`, `float`, `bool`, `class std::basic_string<char,struct std::char_traits<char>,class std::allocator<char> >`, `class ConfigExplosion`, `class ceng::math::CVector2<float>`). The `class` types indicate custom data structures or objects used by the game engine.

The structure is hierarchical, with components containing variables. The XML format is clean and descriptive, making it relatively straightforward to understand the intended data structure.

## Key Patterns

Several patterns are evident in the sampled content:

*   **Component-Based Design:** The game's data is organized around distinct components, suggesting a modular and extensible design. Each component encapsulates a specific set of functionalities or properties.
*   **Variable Definitions:** Variables within components are consistently defined with `name`, `size`, and `type` attributes. This provides a clear contract for how data should be structured and interpreted.
*   **Data Types:** A mix of fundamental C++ data types (`int`, `float`, `bool`) and custom class types are used. The string type `class std::basic_string<char,struct std::char_traits<char>,class std::allocator<char> >` is a common way to represent text data like filenames or animation names.
*   **AI and Behavior Focus:** Several components like `AIAttackComponent` and `AIComponent` suggest a strong focus on defining enemy AI, attack patterns, movement, and sensory behaviors.
*   **Visual and Physical Properties:** Components like `LightningComponent` and `LiquidDisplacerComponent` indicate definitions for visual effects and physical interactions with the game world.
*   **Transform and Spatial Data:** Variables like `root_offset_x`, `root_offset_y`, `init_offset_x`, `init_offset_y`, and `mLocalPosition` point to the definition of positional and transformational data for entities.

## Sample Entries

Here are a few representative examples from the sampled content:

1.  **`AIAttackComponent` Variables:**
    ```xml
    <Component component_name="AIAttackComponent" >
      <Var name="use_probability" size="4" type="int" >
      </Var>
      <Var name="min_distance" size="4" type="float" >
      </Var>
      <Var name="max_distance" size="4" type="float" >
      </Var>
      <Var name="animation_name" size="24" type="class std::basic_string<char,struct std::char_traits<char>,class std::allocator<char> >" >
      </Var>
      <Var name="attack_ranged_entity_file" size="24" type="class std::basic_string<char,struct std::char_traits<char>,class std::allocator<char> >" >
      </Var>
    </Component>
    ```
    This component defines parameters for an AI's attack capabilities. It includes variables for attack probability, range (`min_distance`, `max_distance`), the name of the attack animation, and the entity file to be spawned for ranged attacks.

2.  **`AIComponent` Variables (partial sample):**
    ```xml
    <Component component_name="AIComponent" >
      <Var name="direction_adjust_speed" size="4" type="float" >
      </Var>
      <Var name="gravity" size="4" type="float" >
      </Var>
      <Var name="eat_ground" size="1" type="bool" >
      </Var>
      <Var name="bite_damage" size="4" type="float" >
      </Var>
    </Component>
    ```
    This component seems to govern general AI behavior. The sample shows variables related to movement (`direction_adjust_speed`), physics (`gravity`), interaction with the environment (`eat_ground`), and combat damage (`bite_damage`).

3.  **`LightningComponent` Variables:**
    ```xml
    <Component component_name="LightningComponent" >
      <Var name="sprite_lightning_file" size="24" type="class std::basic_string<char,struct std::char_traits<char>,class std::allocator<char> >" >
      </Var>
      <Var name="is_projectile" size="1" type="bool" >
      </Var>
      <Var name="arc_lifetime" size="4" type="int" >
      </Var>
    </Component>
    ```
    This component defines properties for lightning effects. It includes the sprite file for the lightning, a boolean to indicate if it's a projectile, and its lifetime in frames.

## Reference

This file contains 6304 lines. For complete data, see the [full source](https://github.com/NathanSnail/noitadata/tree/main/data/schemas/ae7ead807db4e19cdc7dd95b4e8fe918.xml).

---