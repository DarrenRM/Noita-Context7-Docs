---
title: ddedabee7c7080ef24717e6bca010ae2
category: schemas
source: https://github.com/NathanSnail/noitadata/tree/main/data/schemas/ddedabee7c7080ef24717e6bca010ae2.xml
---

# ddedabee7c7080ef24717e6bca010ae2

This XML file defines a collection of game components and their associated variables, which are fundamental building blocks for entities within the game Noita. These components dictate the behavior, properties, and interactions of various game objects, such as creatures, items, and environmental elements. The `hash` attribute in the root `<Schema>` tag likely serves as an identifier for this specific set of definitions. This file is crucial for understanding how different game mechanics are implemented and for modding purposes, as it exposes the underlying data structures that govern entity behavior.

## File Structure

The file is structured as a series of `<Component>` elements, each representing a distinct functional unit that can be attached to game entities. Within each `<Component>`, there are `<Var>` elements that define individual properties or variables associated with that component.

*   **`<Schema>`:** The root element, containing a `hash` attribute.
*   **`<Component>`:** Represents a specific component or module that can be added to game entities. It has a `component_name` attribute that identifies the type of component (e.g., `AIAttackComponent`, `AIComponent`, `AnimalAIComponent`).
*   **`<Var>`:** Defines a variable within a component. Each `<Var>` element has the following attributes:
    *   `name`: The name of the variable (e.g., `use_probability`, `min_distance`, `animation_name`).
    *   `size`: The size of the variable in bytes.
    *   `type`: The data type of the variable. This can include primitive types like `int`, `float`, `bool`, `__int64`, `unsigned int`, and more complex C++ types like `class std::basic_string<char,struct std::char_traits<char>,class std::allocator<char> >` (which represents a string) or `class ceng::math::CVector2<float>` (representing a 2D vector of floats).

The structure is hierarchical, with components containing variables. The XML format is clean and descriptive, making it relatively easy to parse and understand the purpose of each defined element.

## Key Patterns

Several patterns emerge from the sampled content:

*   **Component-Based Design:** The game utilizes a component-based architecture, where entities are composed of various functional components. This file defines these components and their configurable parameters.
*   **AI Components:** A significant portion of the file appears to be dedicated to defining AI-related components, such as `AIAttackComponent`, `AIComponent`, and `AnimalAIComponent`. These components control creature behavior, including attack patterns, movement, detection, and reactions.
*   **Data Types:** A variety of data types are used, ranging from simple integers and booleans to more complex string and vector types, indicating a sophisticated system for defining entity properties.
*   **Configuration Parameters:** Variables within components often represent configurable parameters that can be adjusted to fine-tune entity behavior. For example, `use_probability`, `min_distance`, and `animation_name` in `AIAttackComponent` directly influence how an entity attacks.
*   **Scripting Hooks:** Components like `ScriptComponent` (observed in the last sample chunk) indicate that entities can have custom scripts attached to them, triggered by various in-game events (e.g., `script_damage_received`, `script_item_picked_up`). This allows for highly dynamic and moddable gameplay.
*   **Physical Properties:** Components like `IngestionComponent` define physical attributes such as size, capacity, and damage related to ingestion, suggesting mechanics for entities that consume other entities.

## Sample Entries

Here are a few representative examples from the sampled content:

**1. `AIAttackComponent`:**

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

This component defines parameters for an entity's attack capabilities. It includes variables for the probability of using an attack, the range (minimum and maximum distance), the name of the animation associated with the attack, and the entity file to be spawned when performing a ranged attack.

**2. `AnimalAIComponent`:**

```xml
  <Component component_name="AnimalAIComponent" >
    <Var name="ai_state" size="4" type="int" >
    </Var>
    <Var name="preferred_job" size="24" type="class std::basic_string<char,struct std::char_traits<char>,class std::allocator<char> >" >
    </Var>
    <Var name="escape_if_damaged_probability" size="4" type="int" >
    </Var>
    <Var name="creature_detection_range_x" size="4" type="float" >
    </Var>
    <Var name="creature_detection_range_y" size="4" type="float" >
    </Var>
  </Component>
```

This component specifically defines AI behaviors for animal-like creatures. It includes variables for their current AI state, a preferred job or action, the probability of escaping when damaged, and their detection range for other creatures.

**3. `ScriptComponent` (from the last sample chunk):**

```xml
    <Var name="script_enabled_changed" size="24" type="class std::basic_string<char,struct std::char_traits<char>,class std::allocator<char> >" >
    </Var>
    <Var name="script_damage_received" size="24" type="class std::basic_string<char,struct std::char_traits<char>,class std::allocator<char> >" >
    </Var>
    <Var name="script_item_picked_up" size="24" type="class std::basic_string<char,struct std::char_traits<char>,class std::allocator<char> >" >
    </Var>
```

This component, likely named `ScriptComponent` (though the full component tag is not in the sample), defines hooks for custom scripting. The variables represent the names of Lua scripts that will be executed when specific events occur, such as when the script's enabled state changes, when the entity receives damage, or when an item is picked up.

## Reference

This file contains 6796 lines. For complete data, see the [full source](https://github.com/NathanSnail/noitadata/tree/main/data/schemas/ddedabee7c7080ef24717e6bca010ae2.xml).

---