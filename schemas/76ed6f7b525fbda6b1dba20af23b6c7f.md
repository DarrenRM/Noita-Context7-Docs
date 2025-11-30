---
title: 76ed6f7b525fbda6b1dba20af23b6c7f
category: schemas
source: https://github.com/NathanSnail/noitadata/tree/main/data/schemas/76ed6f7b525fbda6b1dba20af23b6c7f.xml
---

# 76ed6f7b525fbda6b1dba20af23b6c7f

This XML file defines the structure and properties of various game components and entities within Noita. It acts as a schema, outlining the data types and names for variables associated with different game systems. These definitions are crucial for the game engine to correctly load, interpret, and utilize the data for entities, behaviors, and effects. Essentially, it's a blueprint for how game data is organized and what parameters can be adjusted for different game elements.

## File Structure

The file is structured as a collection of `<Component>` elements, each representing a distinct game component or system. The root element is `<Schema>`, which contains these components.

Each `<Component>` element has a `component_name` attribute that identifies the specific system it describes (e.g., `AIAttackComponent`, `AIComponent`, `AltarComponent`).

Inside each `<Component>`, there are `<Var>` elements. These `<Var>` elements define individual variables or properties associated with that component. Each `<Var>` has the following attributes:

*   **`name`**: The name of the variable (e.g., `use_probability`, `min_distance`, `recognized_entity_tags`).
*   **`size`**: The size of the variable in bytes. This often indicates the data type.
*   **`type`**: The data type of the variable. This can range from primitive types like `int`, `float`, `bool` to more complex C++ types like `class std::basic_string<char,struct std::char_traits<char>,class std::allocator<char> >` (which represents a string) or enums like `enum RAGDOLL_FX::Enum`.

The `<Var>` elements themselves are typically empty, as their purpose is to define the structure and metadata of the variable, not to hold its value.

## Key Patterns

*   **Component-Based Architecture**: The file clearly demonstrates a component-based design for game entities. Different functionalities (AI, attacks, visual effects, physics) are encapsulated in distinct components.
*   **Variable Definitions**: The `<Var>` tags consistently define properties with names, sizes, and types, providing a clear schema for data serialization and deserialization.
*   **String Representation**: C++ string types are represented using a verbose `class std::basic_string<char,struct std::char_traits<char>,class std::allocator<char> >`.
*   **Enum Usage**: Enums are used for variables that represent a fixed set of states or options, indicated by types like `enum RAGDOLL_FX::Enum` or `enum PARTICLE_EMITTER_CUSTOM_STYLE::Enum`.
*   **AI and Behavior**: A significant portion of the components seem to relate to AI behavior, including movement, attacking, and state management (`AIAttackComponent`, `AIComponent`, `AnimalAIComponent`).
*   **Entity Properties**: Components like `AltarComponent` and those related to ragdoll effects suggest definitions for how entities interact with the environment or behave upon death.
*   **Particle Systems**: The presence of `PARTICLE_EMITTER_CUSTOM_STYLE::Enum` indicates definitions for particle effects and their emission properties.

## Sample Entries

Here are a few representative examples from the sampled content:

**1. `AIAttackComponent` Variables:**

```xml
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
```

This section defines parameters for an AI's attack capabilities. It includes probabilities of using an attack, ranges, animation names, and the entity file to spawn for ranged attacks.

**2. `AltarComponent` Variables:**

```xml
  <Component component_name="AltarComponent" >

    <Var name="recognized_entity_tags" size="24" type="class std::basic_string<char,struct std::char_traits<char>,class std::allocator<char> >" >
    </Var>

    <Var name="good_fx_material" size="4" type="int" >
    </Var>

    <Var name="uses_remaining" size="4" type="int" >
    </Var>

  </Component>
```

This component describes an altar. It specifies which entity tags it recognizes, the material IDs for associated visual effects (good, neutral, evil), and how many uses it has remaining.

**3. Particle Emission Variables:**

```xml
    <Var name="lifetime_min" size="4" type="float" >
    </Var>

    <Var name="lifetime_max" size="4" type="float" >
    </Var>

    <Var name="emission_interval_min_frames" size="4" type="int" >
    </Var>

    <Var name="emission_interval_max_frames" size="4" type="int" >
    </Var>

    <Var name="custom_style" size="4" type="enum PARTICLE_EMITTER_CUSTOM_STYLE::Enum" >
    </Var>
```

This snippet shows variables related to particle emitters. It defines the minimum and maximum lifetime of particles, the interval between emissions (in frames), and a custom style for the emission.

## Reference

This file contains 6360 lines. For complete data, see the [full source](https://github.com/NathanSnail/noitadata/tree/main/data/schemas/76ed6f7b525fbda6b1dba20af23b6c7f.xml).
---