---
title: ccf11b18cb6bdf72ba5f5680feabbd28
category: schemas
source: https://github.com/NathanSnail/noitadata/tree/main/data/schemas/ccf11b18cb6bdf72ba5f5680feabbd28.xml
---

# ccf11b18cb6bdf72ba5f5680feabbd28

This XML file, identified by the hash `ccf11b18cb6bdf72ba5f5680feabbd28`, defines a collection of game components and their associated variables. These components are fundamental building blocks for entities within the game Noita, dictating their behavior, properties, and interactions. This schema file acts as a blueprint, specifying the data structure for various game systems, such as AI, inventory management, and scripting. Understanding this file is crucial for comprehending how different game elements are configured and how they function.

## File Structure

The file is structured as an XML document with a root `<Schema>` element. Inside this root element, various `<Component>` elements are defined. Each `<Component>` represents a distinct game system or functionality and has a `component_name` attribute that identifies it.

Within each `<Component>`, individual properties or variables are defined using `<Var>` tags. Each `<Var>` tag has the following key attributes:

*   **`name`**: The name of the variable.
*   **`size`**: The size of the variable in bytes.
*   **`type`**: The data type of the variable (e.g., `int`, `float`, `bool`, `class std::basic_string<char,struct std::char_traits<char>,class std::allocator<char> >`, `class ceng::math::CVector2<int>`).

The content within a `<Var>` tag is typically empty, as the actual values for these variables are defined elsewhere in the game's data files, likely in entity-specific configuration files that reference these schema definitions.

## Key Patterns

Several patterns are evident in the sampled content:

*   **Component-Based Architecture**: The file clearly follows a component-based design, where distinct functionalities are encapsulated within named components. This allows for modularity and reusability of game logic.
*   **Variable Definitions**: The `<Var>` tag is consistently used to define the properties of each component. The `type` attribute is particularly informative, indicating how the data should be interpreted (e.g., numerical values, boolean flags, string identifiers, or vector types).
*   **String Types**: A common string type observed is `class std::basic_string<char,struct std::char_traits<char>,class std::allocator<char> >`. This likely represents standard C++ string objects, often used for names of animations, scripts, or entity files.
*   **Vector Types**: The `class ceng::math::CVector2<int>` type suggests the use of 2D integer vectors, likely for representing positions, sizes, or dimensions.
*   **Boolean Flags**: Many variables are of type `bool`, indicating simple on/off states or flags that control specific behaviors.
*   **Numerical Types**: `int` and `float` types are used for numerical parameters, such as probabilities, distances, durations, and offsets.

## Sample Entries

Here are a few representative examples from the sampled content:

1.  **`AIAttackComponent`**:
    ```xml
    <Component component_name="AIAttackComponent" >
      <Var name="use_probability" size="4" type="int" >
      </Var>
      <Var name="min_distance" size="4" type="float" >
      </Var>
      <Var name="animation_name" size="24" type="class std::basic_string<char,struct std::char_traits<char>,class std::allocator<char> >" >
      </Var>
      <Var name="attack_ranged_entity_file" size="24" type="class std::basic_string<char,struct std::char_traits<char>,class std::allocator<char> >" >
      </Var>
    </Component>
    ```
    This component appears to define parameters related to an AI's attacking behavior. It includes variables for attack probability, range, the name of an attack animation, and the entity file to be used for ranged attacks.

2.  **`InventoryComponent`**:
    ```xml
    <Component component_name="InventoryComponent" >
      <Var name="ui_container_type" size="4" type="int" >
      </Var>
      <Var name="ui_container_size" size="8" type="class ceng::math::CVector2<int>" >
      </Var>
      <Var name="ui_element_sprite" size="24" type="class std::basic_string<char,struct std::char_traits<char>,class std::allocator<char> >" >
      </Var>
      <Var name="actions" size="24" type="class std::basic_string<char,struct std::char_traits<char>,class std::allocator<char> >" >
      </Var>
    </Component>
    ```
    This component likely governs an entity's inventory system. It defines variables for the UI representation of the inventory, such as its container type, size, sprite, and associated actions.

3.  **`ScriptComponent` (implied by `script_` prefixed variables)**:
    ```xml
    <Component component_name="ScriptComponent" >
      <Var name="remove_after_executed" size="1" type="bool" >
      </Var>
      <Var name="script_enabled_changed" size="24" type="class std::basic_string<char,struct std::char_traits<char>,class std::allocator<char> >" >
      </Var>
      <Var name="script_damage_received" size="24" type="class std::basic_string<char,struct std::char_traits<char>,class std::allocator<char> >" >
      </Var>
      <Var name="script_item_picked_up" size="24" type="class std::basic_string<char,struct std::char_traits<char>,class std::allocator<char> >" >
      </Var>
    </Component>
    ```
    While not explicitly named `ScriptComponent` in the sample, the presence of variables like `script_enabled_changed`, `script_damage_received`, and `script_item_picked_up` strongly suggests a component responsible for handling scripted events. These variables likely store the names of Lua scripts that are triggered by specific in-game events.

## Reference

This file contains 6620 lines. For complete data, see the [full source](https://github.com/NathanSnail/noitadata/tree/main/data/schemas/ccf11b18cb6bdf72ba5f5680feabbd28.xml).

---