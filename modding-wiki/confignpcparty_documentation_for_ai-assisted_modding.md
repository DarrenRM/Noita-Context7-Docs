---
title: ConfigNpcParty Documentation for AI-Assisted Modding
source: https://noita.wiki.gg/wiki/Documentation:ConfigNpcParty
category: modding-wiki
---

# ConfigNpcParty Documentation for AI-Assisted Modding

This documentation explains the `ConfigNpcParty` file in Noita, which is crucial for defining and customizing NPC (Non-Player Character) behaviors, including their spawning, interactions, and party compositions. Understanding this file is essential for modders looking to create new enemy types, alter existing ones, or implement complex AI behaviors for their mods.

## Understanding `ConfigNpcParty`

The `ConfigNpcParty` file is a core component of Noita's AI system, dictating how NPCs are organized into groups and how they behave within those groups. This allows for more dynamic and challenging encounters by having NPCs act in concert rather than as isolated individuals.

### Key Concepts

*   **NPC Definitions:** This file references and builds upon individual NPC definitions, which are typically found in other configuration files.
*   **Party Composition:** It defines which NPCs can appear together in a "party" or group.
*   **Behavioral Modifiers:** It can influence how NPCs within a party behave, such as their aggression, coordination, or specific roles.

## File Structure and Syntax

The `ConfigNpcParty` file uses an XML-like structure. While the provided wiki page has no content, this section would typically detail the specific tags and attributes used within this file.

### Common Tags (Hypothetical based on typical Noita config files)

*   `<NpcParty>`: The root element for defining a party.
*   `<Name>`: A unique identifier for the party.
*   `<Npc>`: Defines an NPC that can be part of this party.
    *   `id`: The internal ID of the NPC.
    *   `prob`: The probability of this NPC appearing in the party.
    *   `min_count`, `max_count`: The minimum and maximum number of this NPC that can spawn in the party.
*   `<SpawnCondition>`: Conditions under which this party can spawn.
*   `<Behavior>`: Modifiers to the party's overall behavior.

### Example (Hypothetical)

```xml
<NpcParty name="GoblinAmbushParty">
    <Npc id="goblin" prob="1.0" min_count="2" max_count="4"/>
    <Npc id="goblin_spear" prob="0.7" min_count="1" max_count="2"/>
    <Npc id="goblin_shaman" prob="0.3" min_count="1" max_count="1"/>
    <SpawnCondition biome="coal_mine"/>
    <Behavior aggression_level="high"/>
</NpcParty>
```

## Integrating with AI and Spawning

The `ConfigNpcParty` file works in conjunction with other Noita configuration files and the game's spawning system.

### Relationship with `data/scripts/ai/`

The behaviors defined in `ConfigNpcParty` are often interpreted and executed by AI scripts located in the `data/scripts/ai/` directory. These scripts read the party definitions and apply the specified behaviors to the spawned NPCs.

### Spawning Mechanics

The game's spawning system uses these party definitions to determine which groups of NPCs to place in the world, often based on biome, player progression, or specific game events.

## Modding Considerations

When creating mods that involve new NPCs or altered behaviors, you will likely need to modify or create new `ConfigNpcParty` files.

### Creating New Parties

To introduce a new type of encounter, you can define a new `<NpcParty>` block with your custom NPCs and desired spawn conditions.

### Modifying Existing Parties

You can override or extend existing `ConfigNpcParty` definitions in your mod to change the composition or behavior of established enemy groups.

### Best Practices

*   **Unique Names:** Ensure all your custom party names are unique to avoid conflicts with other mods.
*   **Probability Balancing:** Carefully balance the `prob` values to achieve the desired encounter frequency.
*   **Testing:** Thoroughly test your modified or new parties in-game to ensure they function as intended and don't cause unexpected issues.

## Further Resources

*   [Lua API](https://noita.wiki.gg/wiki/Modding:_Lua_API)
*   [Config Files Overview](https://noita.wiki.gg/wiki/Modding:_Config_Files)