---
title: Sampo Pickup Logic
category: entities
---

# Sampo Pickup Logic

This document details the Lua script responsible for handling the pickup of the "Sampo" item in Noita, which triggers boss encounters and game events.

## Core Functionality

The `item_pickup` function is executed when the player collects the Sampo. It orchestrates the following:

*   **Music and Sound:** Fades out current music, plays a specific sound effect, and triggers boss arena music.
*   **Global State:** Sets a global variable `FINAL_BOSS_ACTIVE` to "1", indicating the final boss encounter is imminent.
*   **Visual Effects:** Spawns a chest effect particle emitter at the pickup location.
*   **Boss Activation:** Identifies and activates boss entities, specifically the centipede boss.
*   **Environment Manipulation:** Spawns environmental hazards like loose lava ceilings and bridges.
*   **Pacifist Run Handling:** Includes logic to potentially disable the boss fight if the player has achieved a pacifist run (though this is commented out and overridden by default).
*   **Victory Condition:** If the boss is not fought (pacifist run), it spawns a victory teleport.

## Key Attributes and Elements

### `item_pickup( entity_item, entity_who_picked, name )`

This is the main function triggered upon item pickup.

*   `entity_item`: The entity representing the item being picked up.
*   `entity_who_picked`: The entity that picked up the item (usually the player).
*   `name`: The name of the item being picked up.

### Global State Management

*   `GlobalsSetValue( "FINAL_BOSS_ACTIVE", "1" )`: Crucial for signaling the game that the final boss encounter has begun.

### Entity Identification and Manipulation

*   `EntityGetWithTag( "sampo_or_boss" )`: Retrieves all entities tagged as "sampo_or_boss". This is used to find the boss entities.
*   `EntityGetWithTag( "reference" )`: Finds a "reference" entity, likely used to get a central coordinate for boss spawning.
*   `EntitySetComponentsWithTagEnabled( entity_id, tag, enabled )`: Used to enable or disable specific components of entities based on tags.
    *   `"enabled_at_start"`: Components that are active when the entity is first loaded.
    *   `"disabled_at_start"`: Components that are inactive when the entity is first loaded.
*   `PhysicsSetStatic( entity_id, is_static )`: Controls whether an entity's physics are static or dynamic.
*   `EntityAddTag( entity_id, tag )`: Adds a tag to an entity.
    *   `"boss_centipede_active"`: Tag applied to the centipede boss when it becomes active.
*   `EntityGetAllChildren( entity_id )`: Retrieves all child entities of a given entity.
*   `EntityKill( entity_id )`: Destroys an entity.
*   `EntityLoad( xml_path, x, y )`: Loads a new entity from an XML file at specified coordinates.

### Music and Sound Events

*   `GameTriggerMusicFadeOutAndDequeueAll( fade_time )`: Smoothly fades out all currently playing music.
*   `GamePlaySound( bank, event, x, y )`: Plays a specific sound effect at given coordinates.
    *   `"data/audio/Desktop/event_cues.bank", "event_cues/sampo_pick/create"`: The sound played upon Sampo pickup.
*   `GameTriggerMusicEvent( event_name, play_immediately, x, y )`: Triggers a specific music event.
    *   `"music/boss_arena/battle", false, x, y`: Starts the boss arena battle music.

### Environmental Spawns

The following entities are loaded to create the boss arena environment:

*   `data/entities/animals/boss_centipede/loose_lavaceiling.xml`
*   `data/entities/animals/boss_centipede/loose_lavabridge.xml`

### Pacifist Run Logic (Commented Out/Overridden)

The script includes logic to check `StatsGetValue("enemies_killed")`. If this value is 0, the `fight_player` flag is set to `false`, and boss components are disabled. However, a subsequent line `fight_player = true` overrides this, ensuring the boss always fights by default.

### Victory Condition

*   `EntityLoad( "data/entities/buildings/teleport_ending_victory.xml", x, y )`: If `fight_player` is `false`, this teleporter is spawned, leading to a victory screen.

---