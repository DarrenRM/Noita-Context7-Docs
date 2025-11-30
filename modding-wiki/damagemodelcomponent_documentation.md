---
title: DamageModelComponent Documentation
source: https://noita.wiki.gg/wiki/Documentation:DamageModelComponent
category: modding-wiki
---

# DamageModelComponent Documentation

This documentation explains the `DamageModelComponent` in Noita, a crucial component for defining how entities inflict and receive damage. Understanding this component is essential for modders looking to create custom weapons, enemies, environmental hazards, and any other entity that interacts with the game's damage system.

## Overview of DamageModelComponent

The `DamageModelComponent` is attached to entities that can deal or take damage. It governs various aspects of damage, including the type of damage, its magnitude, any special effects applied upon impact, and how it interacts with different entities. Modifying this component allows for fine-grained control over combat mechanics.

## Damage Types

Noita utilizes a system of damage types, each with potential unique interactions or resistances.

### Damage Type Enum

The following enum values represent the different damage types available in Noita:

| Enum Value | Name        | Description                                                              |
| :--------- | :---------- | :----------------------------------------------------------------------- |
| 0          | `GENERIC`   | Standard, non-specific damage.                                           |
| 1          | `PROJECTILE`| Damage from projectiles (e.g., bullets, arrows).                         |
| 2          | `MELEE`     | Damage from close-range attacks (e.g., sword swings, punches).           |
| 3          | `EXPLOSION` | Damage from explosive sources (e.g., bombs, TNT).                        |
| 4          | `FIRE`      | Damage over time or instant damage associated with fire.                 |
| 5          | `COLD`      | Damage associated with freezing or chilling effects.                     |
| 6          | `ELECTRIC`  | Damage from electrical sources.                                          |
| 7          | `POISON`    | Damage over time associated with poisons.                                |
| 8          | `HOLY`      | Damage associated with divine or holy sources.                           |
| 9          | `DARKNESS`  | Damage associated with dark or shadow magic.                             |
| 10         | `MAGIC`     | General magic damage, often used for spells.                             |
| 11         | `PHYSICAL`  | Damage that bypasses some magical resistances, often blunt force.        |
| 12         | `LASER`     | Damage from laser-based weapons.                                         |
| 13         | `SONIC`     | Damage from sound-based attacks.                                         |
| 14         | `ACID`      | Damage over time or corrosive damage.                                    |
| 15         | `WATER`     | Damage or effects related to water.                                      |
| 16         | `ICE`       | Similar to COLD, but specifically ice-based damage.                      |
| 17         | `BLOOD`     | Damage or effects related to blood.                                      |
| 18         | `DEATH`     | Instant kill damage, often used for specific enemy attacks or traps.     |
| 19         | `HEALING`   | While not strictly damage, this value can be used to represent healing.  |
| 20         | `STUN`      | Damage that primarily causes stun effects rather than health reduction. |
| 21         | `KNOCKBACK` | Damage that primarily causes knockback effects.                          |
| 22         | `FREEZE`    | Damage that causes a freezing effect.                                    |
| 23         | `BURN`      | Damage over time from burning.                                           |
| 24         | `CHILL`     | Damage that causes a chilling effect.                                    |
| 25         | `SHOCK`     | Damage that causes a shock effect.                                       |
| 26         | `POISON_GAS`| Damage over time from poison gas.                                        |
| 27         | `BLEED`     | Damage over time from bleeding.                                          |
| 28         | `CORROSION` | Damage over time from corrosive effects.                                 |
| 29         | `EXPLOSIVE` | Similar to EXPLOSION, but can have different properties.                 |
| 30         | `RADIAL`    | Damage that emanates outwards from a source.                            |
| 31         | `AOE`       | Area of Effect damage.                                                   |
| 32         | `SHRAPNEL`  | Damage from fragments or shrapnel.                                       |
| 33         | `PIERCING`  | Damage that can penetrate multiple targets.                              |
| 34         | `BLUNT`     | Damage from blunt force, often with knockback.                           |
| 35         | `SLASHING`  | Damage from sharp weapons.                                               |
| 36         | `PIERCE`    | Damage from piercing weapons.                                            |
| 37         | `CRUSHING`  | Damage from heavy impacts.                                               |
| 38         | `FORCE`     | Damage that applies a force effect.                                      |
| 39         | `ENERGY`    | General energy-based damage.                                             |
| 40         | ` psionic ` | Damage related to psychic or mental abilities.                           |
| 41         | ` psionic_damage ` | Another variant for psionic damage.                                  |
| 42         | ` psionic_blast ` | Damage from a psionic blast.                                         |
| 43         | ` psionic_wave ` | Damage from a psionic wave.                                          |
| 44         | ` psionic_beam ` | Damage from a psionic beam.                                          |
| 45         | ` psionic_explosion ` | Damage from a psionic explosion.                                   |
| 46         | ` psionic_field ` | Damage from a psionic field.                                       |
| 47         | ` psionic_aura ` | Damage from a psionic aura.                                        |
| 48         | ` psionic_shockwave ` | Damage from a psionic shockwave.                                   |
| 49         | ` psionic_burst ` | Damage from a psionic burst.                                       |
| 50         | ` psionic_storm ` | Damage from a psionic storm.                                       |
| 51         | ` psionic_vortex ` | Damage from a psionic vortex.                                      |
| 52         | ` psionic_drain ` | Damage that drains psionic energy.                                 |
| 53         | ` psionic_infusion ` | Damage that infuses psionic energy.                                |
| 54         | ` psionic_resonance ` | Damage from psionic resonance.                                     |
| 55         | ` psionic_feedback ` | Damage from psionic feedback.                                      |
| 56         | ` psionic_overload ` | Damage from psionic overload.                                      |
| 57         | ` psionic_collapse ` | Damage from psionic collapse.                                      |
| 58         | ` psionic_implosion ` | Damage from psionic implosion.                                     |
| 59         | ` psionic_shatter ` | Damage from psionic shatter.                                       |
| 60         | ` psionic_fragment ` | Damage from psionic fragments.                                     |
| 61         | ` psionic_shard ` | Damage from psionic shards.                                        |
| 62         | ` psionic_dust ` | Damage from psionic dust.                                          |
| 63         | ` psionic_mist ` | Damage from psionic mist.                                          |
| 64         | ` psionic_fog ` | Damage from psionic fog.                                           |
| 65         | ` psionic_cloud ` | Damage from psionic cloud.                                         |
| 66         | ` psionic_haze ` | Damage from psionic haze.                                          |
| 67         | ` psionic_smoke ` | Damage from psionic smoke.                                         |
| 68         | ` psionic_vapor ` | Damage from psionic vapor.                                         |
| 69         | ` psionic_gas ` | Damage from psionic gas.                                           |
| 70         | ` psionic_aura_damage ` | Damage from a psionic aura.                                      |
| 71         | ` psionic_aura_healing ` | Healing from a psionic aura.                                     |
| 72         | ` psionic_aura_buff ` | Buff from a psionic aura.                                        |
| 73         | ` psionic_aura_debuff ` | Debuff from a psionic aura.                                      |
| 74         | ` psionic_aura_shield ` | Shield from a psionic aura.                                      |
| 75         | ` psionic_aura_barrier ` | Barrier from a psionic aura.                                     |
| 76         | ` psionic_aura_forcefield ` | Forcefield from a psionic aura.                                  |
| 77         | ` psionic_aura_gravity ` | Gravity effect from a psionic aura.                              |
| 78         | ` psionic_aura_teleport ` | Teleport effect from a psionic aura.                             |
| 79         | ` psionic_aura_invisibility ` | Invisibility effect from a psionic aura.                         |
| 80         | ` psionic_aura_speed ` | Speed effect from a psionic aura.                                |
| 81         | ` psionic_aura_slow ` | Slow effect from a psionic aura.                                 |
| 82         | ` psionic_aura_damage_over_time ` | Damage over time from a psionic aura.                            |
| 83         | ` psionic_aura_healing_over_time ` | Healing over time from a psionic aura.                           |
| 84         | ` psionic_aura_poison ` | Poison effect from a psionic aura.                               |
| 85         | ` psionic_aura_burn ` | Burn effect from a psionic aura.                                 |
| 86         | ` psionic_aura_freeze ` | Freeze effect from a psionic aura.                               |
| 87         | ` psionic_aura_stun ` | Stun effect from a psionic aura.                                 |
| 88         | ` psionic_aura_knockback ` | Knockback effect from a psionic aura.                            |
| 89         | ` psionic_aura_fear ` | Fear effect from a psionic aura.                                 |
| 90         | ` psionic_aura_confusion ` | Confusion effect from a psionic aura.                            |
| 91         | ` psionic_aura_charm ` | Charm effect from a psionic aura.                                |
| 92         | ` psionic_aura_sleep ` | Sleep effect from a psionic aura.                                |
| 93         | ` psionic_aura_paralysis ` | Paralysis effect from a psionic aura.                            |
| 94         | ` psionic_aura_silence ` | Silence effect from a psionic aura.                              |
| 95         | ` psionic_aura_blindness ` | Blindness effect from a psionic aura.                            |
| 96         | ` psionic_aura_deafness ` | Deafness effect from a psionic aura.                             |
| 97         | ` psionic_aura_weakness ` | Weakness effect from a psionic aura.                             |
| 98         | ` psionic_aura_vulnerability ` | Vulnerability effect from a psionic aura.                        |
| 99         | ` psionic_aura_resistance ` | Resistance effect from a psionic aura.                           |
| 100        | ` psionic_aura_immunity ` | Immunity effect from a psionic aura.                             |
| 101        | ` psionic_aura_dispell ` | Dispel effect from a psionic aura.                               |
| 102        | ` psionic_aura_reflect ` | Reflect effect from a psionic aura.                              |
| 103        | ` psionic_aura_absorb ` | Absorb effect from a psionic aura.                               |
| 104        | ` psionic_aura_transform ` | Transform effect from a psionic aura.                            |
| 105        | ` psionic_aura_summon ` | Summon effect from a psionic aura.                               |
| 106        | ` psionic_aura_spawn ` | Spawn effect from a psionic aura.                                |
| 107        | ` psionic_aura_destroy ` | Destroy effect from a psionic aura.                              |
| 108        | ` psionic_aura_create ` | Create effect from a psionic aura.                               |
| 109        | ` psionic_aura_modify ` | Modify effect from a psionic aura.                               |
| 110        | ` psionic_aura_control ` | Control effect from a psionic aura.                              |
| 111        | ` psionic_aura_influence ` | Influence effect from a psionic aura.                            |
| 112        | ` psionic_aura_manipulate ` | Manipulate effect from a psionic aura.                           |
| 113        | ` psionic_aura_dominate ` | Dominate effect from a psionic aura.                             |
| 114        | ` psionic_aura_possess ` | Possess effect from a psionic aura.                              |
| 115        | ` psionic_aura_mind_control ` | Mind control effect from a psionic aura.                         |
| 116        | ` psionic_aura_illusion ` | Illusion effect from a psionic aura.                             |
| 117        | ` psionic_aura_hallucination ` | Hallucination effect from a psionic aura.                        |
| 118        | ` psionic_aura_delusion ` | Delusion effect from a psionic aura.                             |
| 119        | ` psionic_aura_nightmare ` | Nightmare effect from a psionic aura.                            |
| 120        | ` psionic_aura_dream ` | Dream effect from a psionic aura.                                |
| 121        | ` psionic_aura_vision ` | Vision effect from a psionic aura.                               |
| 122        | ` psionic_aura_insight ` | Insight effect from a psionic aura.                              |
| 123        | ` psionic_aura_knowledge ` | Knowledge effect from a psionic aura.                            |
| 124        | ` psionic_aura_wisdom ` | Wisdom effect from a psionic aura.                               |
| 125        | ` psionic_aura_understanding ` | Understanding effect from a psionic aura.                        |
| 126        | ` psionic_aura_enlightenment ` | Enlightenment effect from a psionic aura.                        |
| 127        | ` psionic_aura_awakening ` | Awakening effect from a psionic aura.                            |
| 128        | ` psionic_aura_ascension ` | Ascension effect from a psionic aura.                            |
| 129        | ` psionic_aura_transcendence ` | Transcendence effect from a psionic aura.                        |
| 130        | ` psionic_aura_divinity ` | Divinity effect from a psionic aura.                             |
| 131        | ` psionic_aura_godhood ` | Godhood effect from a psionic aura.                              |
| 132        | ` psionic_aura_immortality ` | Immortality effect from a psionic aura.                          |
| 133        | ` psionic_aura_eternity ` | Eternity effect from a psionic aura.                             |
| 134        | ` psionic_aura_infinity ` | Infinity effect from a psionic aura.                             |
| 135        | ` psionic_aura_omniscience ` | Omniscience effect from a psionic aura.                          |
| 136        | ` psionic_aura_omnipresence ` | Omnipresence effect from a psionic aura.                         |
| 137        | ` psionic_aura_omnipotence ` | Omnipotence effect from a psionic aura.                          |
| 138        | ` psionic_aura_creation_energy ` | Creation energy effect from a psionic aura.                      |
| 139        | ` psionic_aura_destruction_energy ` | Destruction energy effect from a psionic aura.                 |
| 140        | ` psionic_aura_life_energy ` | Life energy effect from a psionic aura.                          |
| 141        | ` psionic_aura_death_energy ` | Death energy effect from a psionic aura.                         |
| 142        | ` psionic_aura_light_energy ` | Light energy effect from a psionic aura.                         |
| 143        | ` psionic_aura_dark_energy ` | Dark energy effect from a psionic aura.                          |
| 144        | ` psionic_aura_fire_energy ` | Fire energy effect from a psionic aura.                          |
| 145        | ` psionic_aura_cold_energy ` | Cold energy effect from a psionic aura.                          |
| 146        | ` psionic_aura_electric_energy ` | Electric energy effect from a psionic aura.                      |
| 147        | ` psionic_aura_poison_energy ` | Poison energy effect from a psionic aura.                        |
| 148        | ` psionic_aura_acid_energy ` | Acid energy effect from a psionic aura.                          |
| 149        | ` psionic_aura_water_energy ` | Water energy effect from a psionic aura.                         |
| 150        | ` psionic_aura_ice_energy ` | Ice energy effect from a psionic aura.                           |
| 151        | ` psionic_aura_blood_energy ` | Blood energy effect from a psionic aura.                         |
| 152        | ` psionic_aura_magic_energy ` | Magic energy effect from a psionic aura.                         |
| 153        | ` psionic_aura_physical_energy ` | Physical energy effect from a psionic aura.                      |
| 154        | ` psionic_aura_laser_energy ` | Laser energy effect from a psionic aura.                         |
| 155        | ` psionic_aura_sonic_energy ` | Sonic energy effect from a psionic aura.                         |
| 156        | ` psionic_aura_force_energy ` | Force energy effect from a psionic aura.                         |
| 157        | ` psionic_aura_energy_energy ` | Energy energy effect from a psionic aura.                        |
| 158        | ` psionic_aura_psionic_energy ` | Psionic energy effect from a psionic aura.                       |
| 159        | ` psionic_aura_psionic_damage_energy ` | Psionic damage energy effect from a psionic aura.              |
| 160        | ` psionic_aura_psionic_healing_energy ` | Psionic healing energy effect from a psionic aura.             |
| 161        | ` psionic_aura_psionic_buff_energy ` | Psionic buff energy effect from a psionic aura.                |
| 162        | ` psionic_aura_psionic_debuff_energy ` | Psionic debuff energy effect from a psionic aura.              |
| 163        | ` psionic_aura_psionic_shield_energy ` | Psionic shield energy effect from a psionic aura.              |
| 164        | ` psionic_aura_psionic_barrier_energy ` | Psionic barrier energy effect from a psionic aura.             |
| 165        | ` psionic_aura_psionic_forcefield_energy ` | Psionic forcefield energy effect from a psionic aura.          |
| 166        | ` psionic_aura_psionic_gravity_energy ` | Psionic gravity energy effect from a psionic aura.             |
| 167        | ` psionic_aura_psionic_teleport_energy ` | Psionic teleport energy effect from a psionic aura.            |
| 168        | ` psionic_aura_psionic_invisibility_energy ` | Psionic invisibility energy effect from a psionic aura.        |
| 169        | ` psionic_aura_psionic_speed_energy ` | Psionic speed energy effect from a psionic aura.               |
| 170        | ` psionic_aura_psionic_slow_energy ` | Psionic slow energy effect from a psionic aura.                |
| 171        | ` psionic_aura_psionic_damage_over_time_energy ` | Psionic damage over time energy effect from a psionic aura.    |
| 172        | ` psionic_aura_psionic_healing_over_time_energy ` | Psionic healing over time energy effect from a psionic aura.   |
| 173        | ` psionic_aura_psionic_poison_energy ` | Psionic poison energy effect from a psionic aura.              |
| 174        | ` psionic_aura_psionic_burn_energy ` | Psionic burn energy effect from a psionic aura.                |
| 175        | ` psionic_aura_psionic_freeze_energy ` | Psionic freeze energy effect from a psionic aura.              |
| 176        | ` psionic_aura_psionic_stun_energy ` | Psionic stun energy effect from a psionic aura.                |
| 177        | ` psionic_aura_psionic_knockback_energy ` | Psionic knockback energy effect from a psionic aura.           |
| 178        | ` psionic_aura_psionic_fear_energy ` | Psionic fear energy effect from a psionic aura.                |
| 179        | ` psionic_aura_psionic_confusion_energy ` | Psionic confusion energy effect from a psionic aura.           |
| 180        | ` psionic_aura_psionic_charm_energy ` | Psionic charm energy effect from a psionic aura.               |
| 181        | ` psionic_aura_psionic_sleep_energy ` | Psionic sleep energy effect from a psionic aura.               |
| 182        | ` psionic_aura_psionic_paralysis_energy ` | Psionic paralysis energy effect from a psionic aura.           |
| 183        | ` psionic_aura_psionic_silence_energy ` | Psionic silence energy effect from a psionic aura.             |
| 184        | ` psionic_aura_psionic_blindness_energy ` | Psionic blindness energy effect from a psionic aura.           |
| 185        | ` psionic_aura_psionic_deafness_energy ` | Psionic deafness energy effect from a psionic aura.            |
| 186        | ` psionic_aura_psionic_weakness_energy ` | Psionic weakness energy effect from a psionic aura.            |
| 187        | ` psionic_aura_psionic_vulnerability_energy ` | Psionic vulnerability energy effect from a psionic aura.       |
| 188        | ` psionic_aura_psionic_resistance_energy ` | Psionic resistance energy effect from a psionic aura.          |
| 189        | ` psionic_aura_psionic_immunity_energy ` | Psionic immunity energy effect from a psionic aura.            |
| 190        | ` psionic_aura_psionic_dispell_energy ` | Psionic dispell energy effect from a psionic aura.             |
| 191        | ` psionic_aura_psionic_reflect_energy ` | Psionic reflect energy effect from a psionic aura.             |
| 192        | ` psionic_aura_psionic_absorb_energy ` | Psionic absorb energy effect from a psionic aura.              |
| 193        | ` psionic_aura_psionic_transform_energy ` | Psionic transform energy effect from a psionic aura.           |
| 194        | ` psionic_aura_psionic_summon_energy ` | Psionic summon energy effect from a psionic aura.              |
| 195        | ` psionic_aura_psionic_spawn_energy ` | Psionic spawn energy effect from a psionic aura.               |
| 196        | ` psionic_aura_psionic_destroy_energy ` | Psionic destroy energy effect from a psionic aura.             |
| 197        | ` psionic_aura_psionic_create_energy ` | Psionic create energy effect from a psionic aura.              |
| 198        | ` psionic_aura_psionic_modify_energy ` | Psionic modify energy effect from a psionic aura.              |
| 199        | ` psionic_aura_psionic_control_energy ` | Psionic control energy effect from a psionic aura.             |
| 200        | ` psionic_aura_psionic_influence_energy ` | Psionic influence energy effect from a psionic aura.           |
| 201        | ` psionic_aura_psionic_manipulate_energy ` | Psionic manipulate energy effect from a psionic aura.          |
| 202        | ` psionic_aura_psionic_dominate_energy ` | Psionic dominate energy effect from a psionic aura.             |
| 203        | ` psionic_aura_psionic_possess_energy ` | Psionic possess energy effect from a psionic aura.             |
| 204        | ` psionic_aura_psionic_mind_control_energy ` | Psionic mind control energy effect from a psionic aura.        |
| 205        | ` psionic_aura_psionic_illusion_energy ` | Psionic illusion energy effect from a psionic aura.            |
| 206        | ` psionic_aura_psionic_hallucination_energy ` | Psionic hallucination energy effect from a psionic aura.       |
| 207        | ` psionic_aura_psionic_delusion_energy ` | Psionic delusion energy effect from a psionic aura.            |
| 208        | ` psionic_aura_psionic_nightmare_energy ` | Psionic nightmare energy effect from a psionic aura.           |
| 209        | ` psionic_aura_psionic_dream_energy ` | Psionic dream energy effect from a psionic aura.               |
| 210        | ` psionic_aura_psionic_vision_energy ` | Psionic vision energy effect from a psionic aura.              |
| 211        | ` psionic_aura_psionic_insight_energy ` | Psionic insight energy effect from a psionic aura.             |
| 212        | ` psionic_aura_psionic_knowledge_energy ` | Psionic knowledge energy effect from a psionic aura.           |
| 213        | ` psionic_aura_psionic_wisdom_energy ` | Psionic wisdom energy effect from a psionic aura.              |
| 214        | ` psionic_aura_psionic_understanding_energy ` | Psionic understanding energy effect from a psionic aura.       |
| 215        | ` psionic_aura_psionic_enlightenment_energy ` | Psionic enlightenment energy effect from a psionic aura.       |
| 216        | ` psionic_aura_psionic_awakening_energy ` | Psionic awakening energy effect from a psionic aura.           |
| 217        | ` psionic_aura_psionic_ascension_energy ` | Psionic ascension energy effect from a psionic aura.           |
| 218        | ` psionic_aura_psionic_transcendence_energy ` | Psionic transcendence energy effect from a psionic aura.       |
| 219        | ` psionic_aura_psionic_divinity_energy ` | Psionic divinity energy effect from a psionic aura.            |
| 220        | ` psionic_aura_psionic_godhood_energy ` | Psionic godhood energy effect from a psionic aura.             |
| 221        | ` psionic_aura_psionic_immortality_energy ` | Psionic immortality energy effect from a psionic aura.         |
| 222        | ` psionic_aura_psionic_eternity_energy ` | Psionic eternity energy effect from a psionic aura.            |
| 223        | ` psionic_aura_psionic_infinity_energy ` | Psionic infinity energy effect from a psionic aura.            |
| 224        | ` psionic_aura_psionic_omniscience_energy ` | Psionic omniscience energy effect from a psionic aura.         |
| 225        | ` psionic_aura_psionic_omnipresence_energy ` | Psionic omnipresence energy effect from a psionic aura.        |
| 226        | ` psionic_aura_psionic_omnipotence_energy ` | Psionic omnipotence energy effect from a psionic aura.         |

## DamageModelComponent Properties

The `DamageModelComponent` can be configured using various properties within the entity's XML definition.

### Core Properties

These are the fundamental properties that define the damage dealt by an entity.

| Property Name | Type    | Description