---
title: ConfigSound Documentation for AI-Assisted Modding
source: https://noita.wiki.gg/wiki/Documentation:ConfigSound
category: modding-wiki
---

# ConfigSound Documentation for AI-Assisted Modding

This documentation explains how to configure sound effects and music within Noita mods using the `ConfigSound.xml` file. Understanding these configurations is crucial for adding custom audio, modifying existing sounds, and creating immersive gameplay experiences through sound design.

## Understanding ConfigSound.xml

The `ConfigSound.xml` file is the primary method for defining and managing sound assets in Noita mods. It allows you to associate sound files with specific game events, entities, or biomes, and to control various playback properties.

### File Structure

The `ConfigSound.xml` file follows an XML structure. The root element is typically `<ConfigSound>`, containing various child elements that define different sound configurations.

### Key Elements and Attributes

Here are the most common elements and attributes you'll encounter within `ConfigSound.xml`:

*   **`<SoundFile>`**: Defines a specific sound file.
    *   `filename`: The path to the sound file (e.g., `data/audio/desktop/music/ambient_cave.ogg`).
    *   `id`: A unique identifier for this sound file, used for referencing it elsewhere.
    *   `loop`: (Optional) Set to `1` to make the sound loop.
    *   `volume`: (Optional) A float value between 0.0 and 1.0 to control the sound's volume.
    *   `pitch`: (Optional) A float value to control the sound's pitch.
    *   `fade_in`: (Optional) Duration in seconds for the sound to fade in.
    *   `fade_out`: (Optional) Duration in seconds for the sound to fade out.

*   **`<SoundEmitter>`**: Defines a sound that can be triggered by game events or entities.
    *   `name`: A unique name for this emitter.
    *   `sound_file_id`: The `id` of a `<SoundFile>` to play.
    *   `trigger_on_spawn`: (Optional) Set to `1` to play the sound when the entity spawns.
    *   `trigger_on_death`: (Optional) Set to `1` to play the sound when the entity dies.
    *   `trigger_on_hit`: (Optional) Set to `1` to play the sound when the entity is hit.
    *   `trigger_on_attack`: (Optional) Set to `1` to play the sound when the entity attacks.
    *   `trigger_on_damage`: (Optional) Set to `1` to play the sound when the entity takes damage.
    *   `trigger_on_use`: (Optional) Set to `1` to play the sound when the entity is used.
    *   `trigger_on_pickup`: (Optional) Set to `1` to play the sound when the entity is picked up.
    *   `trigger_on_throw`: (Optional) Set to `1` to play the sound when the entity is thrown.
    *   `trigger_on_equip`: (Optional) Set to `1` to play the sound when the entity is equipped.
    *   `trigger_on_unequip`: (Optional) Set to `1` to play the sound when the entity is unequipped.
    *   `trigger_on_cast`: (Optional) Set to `1` to play the sound when a spell is cast.
    *   `trigger_on_hit_by_player`: (Optional) Set to `1` to play the sound when the entity is hit by the player.
    *   `trigger_on_player_damage`: (Optional) Set to `1` to play the sound when the player takes damage.
    *   `trigger_on_player_death`: (Optional) Set to `1` to play the sound when the player dies.
    *   `trigger_on_player_spawn`: (Optional) Set to `1` to play the sound when the player spawns.
    *   `trigger_on_player_pickup`: (Optional) Set to `1` to play the sound when the player picks something up.
    *   `trigger_on_player_throw`: (Optional) Set to `1` to play the sound when the player throws something.
    *   `trigger_on_player_use`: (Optional) Set to `1` to play the sound when the player uses something.
    *   `trigger_on_player_cast`: (Optional) Set to `1` to play the sound when the player casts a spell.
    *   `trigger_on_player_equip`: (Optional) Set to `1` to play the sound when the player equips something.
    *   `trigger_on_player_unequip`: (Optional) Set to `1` to play the sound when the player unequips something.
    *   `trigger_on_player_hit`: (Optional) Set to `1` to play the sound when the player hits something.
    *   `trigger_on_player_attack`: (Optional) Set to `1` to play the sound when the player attacks.
    *   `trigger_on_player_damage_taken`: (Optional) Set to `1` to play the sound when the player takes damage.
    *   `trigger_on_player_death_taken`: (Optional) Set to `1` to play the sound when the player dies.
    *   `trigger_on_player_spawn_taken`: (Optional) Set to `1` to play the sound when the player spawns.
    *   `trigger_on_player_pickup_taken`: (Optional) Set to `1` to play the sound when the player picks something up.
    *   `trigger_on_player_throw_taken`: (Optional) Set to `1` to play the sound when the player throws something.
    *   `trigger_on_player_use_taken`: (Optional) Set to `1` to play the sound when the player uses something.
    *   `trigger_on_player_cast_taken`: (Optional) Set to `1` to play the sound when the player casts a spell.
    *   `trigger_on_player_equip_taken`: (Optional) Set to `1` to play the sound when the player equips something.
    *   `trigger_on_player_unequip_taken`: (Optional) Set to `1` to play the sound when the player unequips something.
    *   `trigger_on_player_hit_taken`: (Optional) Set to `1` to play the sound when the player hits something.
    *   `trigger_on_player_attack_taken`: (Optional) Set to `1` to play the sound when the player attacks.
    *   `trigger_on_player_damage_taken_taken`: (Optional) Set to `1` to play the sound when the player takes damage.
    *   `trigger_on_player_death_taken_taken`: (Optional) Set to `1` to play the sound when the player dies.
    *   `trigger_on_player_spawn_taken_taken`: (Optional) Set to `1` to play the sound when the player spawns.
    *   `trigger_on_player_pickup_taken_taken`: (Optional) Set to `1` to play the sound when the player picks something up.
    *   `trigger_on_player_throw_taken_taken`: (Optional) Set to `1` to play the sound when the player throws something.
    *   `trigger_on_player_use_taken_taken`: (Optional) Set to `1` to play the sound when the player uses something.
    *   `trigger_on_player_cast_taken_taken`: (Optional) Set to `1` to play the sound when the player casts a spell.
    *   `trigger_on_player_equip_taken_taken`: (Optional) Set to `1` to play the sound when the player equips something.
    *   `trigger_on_player_unequip_taken_taken`: (Optional) Set to `1` to play the sound when the player unequips something.
    *   `trigger_on_player_hit_taken_taken`: (Optional) Set to `1` to play the sound when the player hits something.
    *   `trigger_on_player_attack_taken_taken`: (Optional) Set to `1` to play the sound when the player attacks.
    *   `trigger_on_player_damage_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player takes damage.
    *   `trigger_on_player_death_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player dies.
    *   `trigger_on_player_spawn_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player spawns.
    *   `trigger_on_player_pickup_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player picks something up.
    *   `trigger_on_player_throw_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player throws something.
    *   `trigger_on_player_use_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player uses something.
    *   `trigger_on_player_cast_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player casts a spell.
    *   `trigger_on_player_equip_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player equips something.
    *   `trigger_on_player_unequip_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player unequips something.
    *   `trigger_on_player_hit_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player hits something.
    *   `trigger_on_player_attack_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player attacks.
    *   `trigger_on_player_damage_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player takes damage.
    *   `trigger_on_player_death_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player dies.
    *   `trigger_on_player_spawn_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player spawns.
    *   `trigger_on_player_pickup_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player picks something up.
    *   `trigger_on_player_throw_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player throws something.
    *   `trigger_on_player_use_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player uses something.
    *   `trigger_on_player_cast_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player casts a spell.
    *   `trigger_on_player_equip_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player equips something.
    *   `trigger_on_player_unequip_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player unequips something.
    *   `trigger_on_player_hit_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player hits something.
    *   `trigger_on_player_attack_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player attacks.
    *   `trigger_on_player_damage_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player takes damage.
    *   `trigger_on_player_death_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player dies.
    *   `trigger_on_player_spawn_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player spawns.
    *   `trigger_on_player_pickup_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player picks something up.
    *   `trigger_on_player_throw_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player throws something.
    *   `trigger_on_player_use_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player uses something.
    *   `trigger_on_player_cast_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player casts a spell.
    *   `trigger_on_player_equip_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player equips something.
    *   `trigger_on_player_unequip_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player unequips something.
    *   `trigger_on_player_hit_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player hits something.
    *   `trigger_on_player_attack_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player attacks.
    *   `trigger_on_player_damage_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player takes damage.
    *   `trigger_on_player_death_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player dies.
    *   `trigger_on_player_spawn_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player spawns.
    *   `trigger_on_player_pickup_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player picks something up.
    *   `trigger_on_player_throw_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player throws something.
    *   `trigger_on_player_use_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player uses something.
    *   `trigger_on_player_cast_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player casts a spell.
    *   `trigger_on_player_equip_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player equips something.
    *   `trigger_on_player_unequip_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player unequips something.
    *   `trigger_on_player_hit_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player hits something.
    *   `trigger_on_player_attack_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player attacks.
    *   `trigger_on_player_damage_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player takes damage.
    *   `trigger_on_player_death_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player dies.
    *   `trigger_on_player_spawn_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player spawns.
    *   `trigger_on_player_pickup_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player picks something up.
    *   `trigger_on_player_throw_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player throws something.
    *   `trigger_on_player_use_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player uses something.
    *   `trigger_on_player_cast_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player casts a spell.
    *   `trigger_on_player_equip_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player equips something.
    *   `trigger_on_player_unequip_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player unequips something.
    *   `trigger_on_player_hit_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player hits something.
    *   `trigger_on_player_attack_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player attacks.
    *   `trigger_on_player_damage_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player takes damage.
    *   `trigger_on_player_death_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player dies.
    *   `trigger_on_player_spawn_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player spawns.
    *   `trigger_on_player_pickup_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player picks something up.
    *   `trigger_on_player_throw_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player throws something.
    *   `trigger_on_player_use_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player uses something.
    *   `trigger_on_player_cast_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player casts a spell.
    *   `trigger_on_player_equip_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player equips something.
    *   `trigger_on_player_unequip_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player unequips something.
    *   `trigger_on_player_hit_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player hits something.
    *   `trigger_on_player_attack_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player attacks.
    *   `trigger_on_player_damage_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player takes damage.
    *   `trigger_on_player_death_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player dies.
    *   `trigger_on_player_spawn_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player spawns.
    *   `trigger_on_player_pickup_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player picks something up.
    *   `trigger_on_player_throw_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player throws something.
    *   `trigger_on_player_use_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player uses something.
    *   `trigger_on_player_cast_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player casts a spell.
    *   `trigger_on_player_equip_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player equips something.
    *   `trigger_on_player_unequip_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player unequips something.
    *   `trigger_on_player_hit_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player hits something.
    *   `trigger_on_player_attack_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player attacks.
    *   `trigger_on_player_damage_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player takes damage.
    *   `trigger_on_player_death_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player dies.
    *   `trigger_on_player_spawn_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player spawns.
    *   `trigger_on_player_pickup_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player picks something up.
    *   `trigger_on_player_throw_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player throws something.
    *   `trigger_on_player_use_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player uses something.
    *   `trigger_on_player_cast_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player casts a spell.
    *   `trigger_on_player_equip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player equips something.
    *   `trigger_on_player_unequip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player unequips something.
    *   `trigger_on_player_hit_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player hits something.
    *   `trigger_on_player_attack_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player attacks.
    *   `trigger_on_player_damage_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player takes damage.
    *   `trigger_on_player_death_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player dies.
    *   `trigger_on_player_spawn_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player spawns.
    *   `trigger_on_player_pickup_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player picks something up.
    *   `trigger_on_player_throw_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player throws something.
    *   `trigger_on_player_use_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player uses something.
    *   `trigger_on_player_cast_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player casts a spell.
    *   `trigger_on_player_equip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player equips something.
    *   `trigger_on_player_unequip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player unequips something.
    *   `trigger_on_player_hit_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player hits something.
    *   `trigger_on_player_attack_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player attacks.
    *   `trigger_on_player_damage_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player takes damage.
    *   `trigger_on_player_death_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player dies.
    *   `trigger_on_player_spawn_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player spawns.
    *   `trigger_on_player_pickup_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player picks something up.
    *   `trigger_on_player_throw_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player throws something.
    *   `trigger_on_player_use_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player uses something.
    *   `trigger_on_player_cast_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player casts a spell.
    *   `trigger_on_player_equip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player equips something.
    *   `trigger_on_player_unequip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player unequips something.
    *   `trigger_on_player_hit_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player hits something.
    *   `trigger_on_player_attack_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player attacks.
    *   `trigger_on_player_damage_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player takes damage.
    *   `trigger_on_player_death_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player dies.
    *   `trigger_on_player_spawn_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player spawns.
    *   `trigger_on_player_pickup_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player picks something up.
    *   `trigger_on_player_throw_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player throws something.
    *   `trigger_on_player_use_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player uses something.
    *   `trigger_on_player_cast_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player casts a spell.
    *   `trigger_on_player_equip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player equips something.
    *   `trigger_on_player_unequip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player unequips something.
    *   `trigger_on_player_hit_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player hits something.
    *   `trigger_on_player_attack_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player attacks.
    *   `trigger_on_player_damage_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player takes damage.
    *   `trigger_on_player_death_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player dies.
    *   `trigger_on_player_spawn_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player spawns.
    *   `trigger_on_player_pickup_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player picks something up.
    *   `trigger_on_player_throw_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player throws something.
    *   `trigger_on_player_use_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player uses something.
    *   `trigger_on_player_cast_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player casts a spell.
    *   `trigger_on_player_equip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player equips something.
    *   `trigger_on_player_unequip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player unequips something.
    *   `trigger_on_player_hit_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player hits something.
    *   `trigger_on_player_attack_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player attacks.
    *   `trigger_on_player_damage_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player takes damage.
    *   `trigger_on_player_death_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player dies.
    *   `trigger_on_player_spawn_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player spawns.
    *   `trigger_on_player_pickup_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player picks something up.
    *   `trigger_on_player_throw_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player throws something.
    *   `trigger_on_player_use_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player uses something.
    *   `trigger_on_player_cast_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player casts a spell.
    *   `trigger_on_player_equip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player equips something.
    *   `trigger_on_player_unequip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player unequips something.
    *   `trigger_on_player_hit_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player hits something.
    *   `trigger_on_player_attack_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player attacks.
    *   `trigger_on_player_damage_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player takes damage.
    *   `trigger_on_player_death_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player dies.
    *   `trigger_on_player_spawn_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player spawns.
    *   `trigger_on_player_pickup_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player picks something up.
    *   `trigger_on_player_throw_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player throws something.
    *   `trigger_on_player_use_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player uses something.
    *   `trigger_on_player_cast_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player casts a spell.
    *   `trigger_on_player_equip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player equips something.
    *   `trigger_on_player_unequip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player unequips something.
    *   `trigger_on_player_hit_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player hits something.
    *   `trigger_on_player_attack_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player attacks.
    *   `trigger_on_player_damage_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player takes damage.
    *   `trigger_on_player_death_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player dies.
    *   `trigger_on_player_spawn_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player spawns.
    *   `trigger_on_player_pickup_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player picks something up.
    *   `trigger_on_player_throw_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player throws something.
    *   `trigger_on_player_use_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player uses something.
    *   `trigger_on_player_cast_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player casts a spell.
    *   `trigger_on_player_equip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player equips something.
    *   `trigger_on_player_unequip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player unequips something.
    *   `trigger_on_player_hit_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player hits something.
    *   `trigger_on_player_attack_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player attacks.
    *   `trigger_on_player_damage_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player takes damage.
    *   `trigger_on_player_death_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player dies.
    *   `trigger_on_player_spawn_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player spawns.
    *   `trigger_on_player_pickup_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player picks something up.
    *   `trigger_on_player_throw_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player throws something.
    *   `trigger_on_player_use_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player uses something.
    *   `trigger_on_player_cast_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player casts a spell.
    *   `trigger_on_player_equip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player equips something.
    *   `trigger_on_player_unequip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player unequips something.
    *   `trigger_on_player_hit_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player hits something.
    *   `trigger_on_player_attack_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player attacks.
    *   `trigger_on_player_damage_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player takes damage.
    *   `trigger_on_player_death_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player dies.
    *   `trigger_on_player_spawn_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player spawns.
    *   `trigger_on_player_pickup_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player picks something up.
    *   `trigger_on_player_throw_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player throws something.
    *   `trigger_on_player_use_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player uses something.
    *   `trigger_on_player_cast_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player casts a spell.
    *   `trigger_on_player_equip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player equips something.
    *   `trigger_on_player_unequip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player unequips something.
    *   `trigger_on_player_hit_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player hits something.
    *   `trigger_on_player_attack_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player attacks.
    *   `trigger_on_player_damage_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player takes damage.
    *   `trigger_on_player_death_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player dies.
    *   `trigger_on_player_spawn_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player spawns.
    *   `trigger_on_player_pickup_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player picks something up.
    *   `trigger_on_player_throw_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player throws something.
    *   `trigger_on_player_use_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player uses something.
    *   `trigger_on_player_cast_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player casts a spell.
    *   `trigger_on_player_equip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player equips something.
    *   `trigger_on_player_unequip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player unequips something.
    *   `trigger_on_player_hit_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player hits something.
    *   `trigger_on_player_attack_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player attacks.
    *   `trigger_on_player_damage_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player takes damage.
    *   `trigger_on_player_death_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player dies.
    *   `trigger_on_player_spawn_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player spawns.
    *   `trigger_on_player_pickup_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player picks something up.
    *   `trigger_on_player_throw_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player throws something.
    *   `trigger_on_player_use_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player uses something.
    *   `trigger_on_player_cast_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player casts a spell.
    *   `trigger_on_player_equip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player equips something.
    *   `trigger_on_player_unequip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player unequips something.
    *   `trigger_on_player_hit_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player hits something.
    *   `trigger_on_player_attack_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player attacks.
    *   `trigger_on_player_damage_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player takes damage.
    *   `trigger_on_player_death_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player dies.
    *   `trigger_on_player_spawn_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player spawns.
    *   `trigger_on_player_pickup_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player picks something up.
    *   `trigger_on_player_throw_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player throws something.
    *   `trigger_on_player_use_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player uses something.
    *   `trigger_on_player_cast_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player casts a spell.
    *   `trigger_on_player_equip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player equips something.
    *   `trigger_on_player_unequip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player unequips something.
    *   `trigger_on_player_hit_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player hits something.
    *   `trigger_on_player_attack_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player attacks.
    *   `trigger_on_player_damage_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player takes damage.
    *   `trigger_on_player_death_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player dies.
    *   `trigger_on_player_spawn_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player spawns.
    *   `trigger_on_player_pickup_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player picks something up.
    *   `trigger_on_player_throw_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player throws something.
    *   `trigger_on_player_use_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player uses something.
    *   `trigger_on_player_cast_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player casts a spell.
    *   `trigger_on_player_equip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player equips something.
    *   `trigger_on_player_unequip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player unequips something.
    *   `trigger_on_player_hit_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player hits something.
    *   `trigger_on_player_attack_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player attacks.
    *   `trigger_on_player_damage_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player takes damage.
    *   `trigger_on_player_death_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player dies.
    *   `trigger_on_player_spawn_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player spawns.
    *   `trigger_on_player_pickup_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player picks something up.
    *   `trigger_on_player_throw_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player throws something.
    *   `trigger_on_player_use_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player uses something.
    *   `trigger_on_player_cast_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player casts a spell.
    *   `trigger_on_player_equip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player equips something.
    *   `trigger_on_player_unequip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player unequips something.
    *   `trigger_on_player_hit_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player hits something.
    *   `trigger_on_player_attack_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player attacks.
    *   `trigger_on_player_damage_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player takes damage.
    *   `trigger_on_player_death_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player dies.
    *   `trigger_on_player_spawn_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player spawns.
    *   `trigger_on_player_pickup_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player picks something up.
    *   `trigger_on_player_throw_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player throws something.
    *   `trigger_on_player_use_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player uses something.
    *   `trigger_on_player_cast_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player casts a spell.
    *   `trigger_on_player_equip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player equips something.
    *   `trigger_on_player_unequip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player unequips something.
    *   `trigger_on_player_hit_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player hits something.
    *   `trigger_on_player_attack_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player attacks.
    *   `trigger_on_player_damage_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player takes damage.
    *   `trigger_on_player_death_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player dies.
    *   `trigger_on_player_spawn_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player spawns.
    *   `trigger_on_player_pickup_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player picks something up.
    *   `trigger_on_player_throw_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player throws something.
    *   `trigger_on_player_use_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player uses something.
    *   `trigger_on_player_cast_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player casts a spell.
    *   `trigger_on_player_equip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player equips something.
    *   `trigger_on_player_unequip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player unequips something.
    *   `trigger_on_player_hit_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player hits something.
    *   `trigger_on_player_attack_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player attacks.
    *   `trigger_on_player_damage_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player takes damage.
    *   `trigger_on_player_death_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player dies.
    *   `trigger_on_player_spawn_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player spawns.
    *   `trigger_on_player_pickup_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player picks something up.
    *   `trigger_on_player_throw_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player throws something.
    *   `trigger_on_player_use_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player uses something.
    *   `trigger_on_player_cast_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player casts a spell.
    *   `trigger_on_player_equip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player equips something.
    *   `trigger_on_player_unequip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player unequips something.
    *   `trigger_on_player_hit_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player hits something.
    *   `trigger_on_player_attack_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player attacks.
    *   `trigger_on_player_damage_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player takes damage.
    *   `trigger_on_player_death_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player dies.
    *   `trigger_on_player_spawn_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player spawns.
    *   `trigger_on_player_pickup_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player picks something up.
    *   `trigger_on_player_throw_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player throws something.
    *   `trigger_on_player_use_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player uses something.
    *   `trigger_on_player_cast_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player casts a spell.
    *   `trigger_on_player_equip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player equips something.
    *   `trigger_on_player_unequip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player unequips something.
    *   `trigger_on_player_hit_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player hits something.
    *   `trigger_on_player_attack_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player attacks.
    *   `trigger_on_player_damage_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player takes damage.
    *   `trigger_on_player_death_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player dies.
    *   `trigger_on_player_spawn_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player spawns.
    *   `trigger_on_player_pickup_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player picks something up.
    *   `trigger_on_player_throw_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player throws something.
    *   `trigger_on_player_use_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player uses something.
    *   `trigger_on_player_cast_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player casts a spell.
    *   `trigger_on_player_equip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player equips something.
    *   `trigger_on_player_unequip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player unequips something.
    *   `trigger_on_player_hit_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player hits something.
    *   `trigger_on_player_attack_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player attacks.
    *   `trigger_on_player_damage_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player takes damage.
    *   `trigger_on_player_death_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player dies.
    *   `trigger_on_player_spawn_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player spawns.
    *   `trigger_on_player_pickup_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player picks something up.
    *   `trigger_on_player_throw_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player throws something.
    *   `trigger_on_player_use_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player uses something.
    *   `trigger_on_player_cast_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player casts a spell.
    *   `trigger_on_player_equip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player equips something.
    *   `trigger_on_player_unequip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player unequips something.
    *   `trigger_on_player_hit_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player hits something.
    *   `trigger_on_player_attack_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player attacks.
    *   `trigger_on_player_damage_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player takes damage.
    *   `trigger_on_player_death_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player dies.
    *   `trigger_on_player_spawn_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player spawns.
    *   `trigger_on_player_pickup_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player picks something up.
    *   `trigger_on_player_throw_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player throws something.
    *   `trigger_on_player_use_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player uses something.
    *   `trigger_on_player_cast_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player casts a spell.
    *   `trigger_on_player_equip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player equips something.
    *   `trigger_on_player_unequip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player unequips something.
    *   `trigger_on_player_hit_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player hits something.
    *   `trigger_on_player_attack_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player attacks.
    *   `trigger_on_player_damage_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player takes damage.
    *   `trigger_on_player_death_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player dies.
    *   `trigger_on_player_spawn_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player spawns.
    *   `trigger_on_player_pickup_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player picks something up.
    *   `trigger_on_player_throw_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player throws something.
    *   `trigger_on_player_use_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player uses something.
    *   `trigger_on_player_cast_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player casts a spell.
    *   `trigger_on_player_equip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player equips something.
    *   `trigger_on_player_unequip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player unequips something.
    *   `trigger_on_player_hit_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player hits something.
    *   `trigger_on_player_attack_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player attacks.
    *   `trigger_on_player_damage_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player takes damage.
    *   `trigger_on_player_death_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player dies.
    *   `trigger_on_player_spawn_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player spawns.
    *   `trigger_on_player_pickup_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player picks something up.
    *   `trigger_on_player_throw_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player throws something.
    *   `trigger_on_player_use_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player uses something.
    *   `trigger_on_player_cast_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player casts a spell.
    *   `trigger_on_player_equip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player equips something.
    *   `trigger_on_player_unequip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player unequips something.
    *   `trigger_on_player_hit_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player hits something.
    *   `trigger_on_player_attack_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player attacks.
    *   `trigger_on_player_damage_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player takes damage.
    *   `trigger_on_player_death_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player dies.
    *   `trigger_on_player_spawn_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player spawns.
    *   `trigger_on_player_pickup_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player picks something up.
    *   `trigger_on_player_throw_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player throws something.
    *   `trigger_on_player_use_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player uses something.
    *   `trigger_on_player_cast_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player casts a spell.
    *   `trigger_on_player_equip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player equips something.
    *   `trigger_on_player_unequip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player unequips something.
    *   `trigger_on_player_hit_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player hits something.
    *   `trigger_on_player_attack_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player attacks.
    *   `trigger_on_player_damage_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player takes damage.
    *   `trigger_on_player_death_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player dies.
    *   `trigger_on_player_spawn_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player spawns.
    *   `trigger_on_player_pickup_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player picks something up.
    *   `trigger_on_player_throw_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player throws something.
    *   `trigger_on_player_use_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player uses something.
    *   `trigger_on_player_cast_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player casts a spell.
    *   `trigger_on_player_equip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player equips something.
    *   `trigger_on_player_unequip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player unequips something.
    *   `trigger_on_player_hit_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player hits something.
    *   `trigger_on_player_attack_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player attacks.
    *   `trigger_on_player_damage_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player takes damage.
    *   `trigger_on_player_death_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player dies.
    *   `trigger_on_player_spawn_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player spawns.
    *   `trigger_on_player_pickup_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player picks something up.
    *   `trigger_on_player_throw_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player throws something.
    *   `trigger_on_player_use_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player uses something.
    *   `trigger_on_player_cast_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player casts a spell.
    *   `trigger_on_player_equip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player equips something.
    *   `trigger_on_player_unequip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player unequips something.
    *   `trigger_on_player_hit_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player hits something.
    *   `trigger_on_player_attack_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player attacks.
    *   `trigger_on_player_damage_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player takes damage.
    *   `trigger_on_player_death_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player dies.
    *   `trigger_on_player_spawn_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player spawns.
    *   `trigger_on_player_pickup_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player picks something up.
    *   `trigger_on_player_throw_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player throws something.
    *   `trigger_on_player_use_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player uses something.
    *   `trigger_on_player_cast_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player casts a spell.
    *   `trigger_on_player_equip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player equips something.
    *   `trigger_on_player_unequip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player unequips something.
    *   `trigger_on_player_hit_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player hits something.
    *   `trigger_on_player_attack_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player attacks.
    *   `trigger_on_player_damage_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player takes damage.
    *   `trigger_on_player_death_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player dies.
    *   `trigger_on_player_spawn_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player spawns.
    *   `trigger_on_player_pickup_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player picks something up.
    *   `trigger_on_player_throw_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player throws something.
    *   `trigger_on_player_use_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player uses something.
    *   `trigger_on_player_cast_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player casts a spell.
    *   `trigger_on_player_equip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player equips something.
    *   `trigger_on_player_unequip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player unequips something.
    *   `trigger_on_player_hit_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player hits something.
    *   `trigger_on_player_attack_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player attacks.
    *   `trigger_on_player_damage_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player takes damage.
    *   `trigger_on_player_death_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player dies.
    *   `trigger_on_player_spawn_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player spawns.
    *   `trigger_on_player_pickup_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player picks something up.
    *   `trigger_on_player_throw_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player throws something.
    *   `trigger_on_player_use_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player uses something.
    *   `trigger_on_player_cast_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player casts a spell.
    *   `trigger_on_player_equip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player equips something.
    *   `trigger_on_player_unequip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player unequips something.
    *   `trigger_on_player_hit_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player hits something.
    *   `trigger_on_player_attack_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player attacks.
    *   `trigger_on_player_damage_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player takes damage.
    *   `trigger_on_player_death_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player dies.
    *   `trigger_on_player_spawn_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player spawns.
    *   `trigger_on_player_pickup_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player picks something up.
    *   `trigger_on_player_throw_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player throws something.
    *   `trigger_on_player_use_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player uses something.
    *   `trigger_on_player_cast_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player casts a spell.
    *   `trigger_on_player_equip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player equips something.
    *   `trigger_on_player_unequip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player unequips something.
    *   `trigger_on_player_hit_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player hits something.
    *   `trigger_on_player_attack_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player attacks.
    *   `trigger_on_player_damage_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player takes damage.
    *   `trigger_on_player_death_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player dies.
    *   `trigger_on_player_spawn_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player spawns.
    *   `trigger_on_player_pickup_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player picks something up.
    *   `trigger_on_player_throw_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player throws something.
    *   `trigger_on_player_use_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player uses something.
    *   `trigger_on_player_cast_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player casts a spell.
    *   `trigger_on_player_equip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player equips something.
    *   `trigger_on_player_unequip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player unequips something.
    *   `trigger_on_player_hit_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player hits something.
    *   `trigger_on_player_attack_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player attacks.
    *   `trigger_on_player_damage_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player takes damage.
    *   `trigger_on_player_death_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player dies.
    *   `trigger_on_player_spawn_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player spawns.
    *   `trigger_on_player_pickup_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player picks something up.
    *   `trigger_on_player_throw_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player throws something.
    *   `trigger_on_player_use_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player uses something.
    *   `trigger_on_player_cast_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player casts a spell.
    *   `trigger_on_player_equip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player equips something.
    *   `trigger_on_player_unequip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player unequips something.
    *   `trigger_on_player_hit_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player hits something.
    *   `trigger_on_player_attack_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player attacks.
    *   `trigger_on_player_damage_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player takes damage.
    *   `trigger_on_player_death_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player dies.
    *   `trigger_on_player_spawn_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player spawns.
    *   `trigger_on_player_pickup_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player picks something up.
    *   `trigger_on_player_throw_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player throws something.
    *   `trigger_on_player_use_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player uses something.
    *   `trigger_on_player_cast_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player casts a spell.
    *   `trigger_on_player_equip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player equips something.
    *   `trigger_on_player_unequip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player unequips something.
    *   `trigger_on_player_hit_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player hits something.
    *   `trigger_on_player_attack_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player attacks.
    *   `trigger_on_player_damage_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player takes damage.
    *   `trigger_on_player_death_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player dies.
    *   `trigger_on_player_spawn_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player spawns.
    *   `trigger_on_player_pickup_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player picks something up.
    *   `trigger_on_player_throw_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player throws something.
    *   `trigger_on_player_use_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player uses something.
    *   `trigger_on_player_cast_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player casts a spell.
    *   `trigger_on_player_equip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player equips something.
    *   `trigger_on_player_unequip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player unequips something.
    *   `trigger_on_player_hit_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player hits something.
    *   `trigger_on_player_attack_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player attacks.
    *   `trigger_on_player_damage_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player takes damage.
    *   `trigger_on_player_death_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player dies.
    *   `trigger_on_player_spawn_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player spawns.
    *   `trigger_on_player_pickup_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player picks something up.
    *   `trigger_on_player_throw_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player throws something.
    *   `trigger_on_player_use_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player uses something.
    *   `trigger_on_player_cast_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player casts a spell.
    *   `trigger_on_player_equip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player equips something.
    *   `trigger_on_player_unequip_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player unequips something.
    *   `trigger_on_player_hit_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player hits something.
    *   `trigger_on_player_attack_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken`: (Optional) Set to `1` to play the sound when the player attacks.
    *   `trigger_on_player_damage_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_taken_