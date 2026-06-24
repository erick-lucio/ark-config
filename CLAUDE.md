# ARK Survival Evolved Dedicated Server — Project Context

## Server Overview
- **Game:** ARK: Survival Evolved (ASE) — latest version
- **Config files:** `configs/Game.ini`, `configs/GameUserSettings.ini`
- **Max players:** 10
- **Difficulty:** 6 (OverrideOfficialDifficulty=6)
- **Mode:** PvP

## Active Mods (ActiveMods line in GameUserSettings.ini)
| Mod ID | Name |
|---|---|
| 861066940 | — |
| 731604991 | — |
| 1701679918 | — |
| 622665004 | — |
| 2693727499 | — |
| 1295978823 | — |
| 1931415003 | — |
| 902616446 | — |
| 730794403 | — |
| 924933745 | — |
| 1404697612 | — |
| 569786012 | — |
| 633215081 | — |
| 2140170832 | — |
| **1443404076** | **Human NPCs** (primary mod being configured) |

## Human NPCs Mod (ID: 1443404076)
- **Steam Workshop:** https://steamcommunity.com/sharedfiles/filedetails/?id=1443404076
- **Config goes in:** `GameUserSettings.ini` (NOT Game.ini)
- **Documentation links:**
  - https://steamcommunity.com/workshop/filedetails/discussion/1443404076/1733210552645207209 (main INI guide)
  - https://steamcommunity.com/workshop/filedetails/discussion/1443404076/1633040337748250577 (loot config)
  - https://steamcommunity.com/workshop/filedetails/discussion/1443404076/3423311880029813624 (villages & base attack)

### INI Sections (all in GameUserSettings.ini)
- `[Human_NPCs]` — core behavior, aggression, spawns, turrets
- `[Human_NPCs_Settings]` — stat multipliers (Health_x, Melee_Damage_x, etc.)
- `[Human_NPCs_Clothing]` — armor tier and role-specific outfit types (0-10)
- `[Human_NPCs_Villages]` — village count, NPC count, spacing
- `[Human_NPCs_Base_Attack]` — raid waves, timing, mounts, flyers
- `[Human_NPCs_Loot]` — item quality, chances, hut loot
- `[Human_NPCs_Loot_Array]` — blueprint paths for Loot_Array and Single_Loot_Array

---

## Full Plugin Reference (from official docs)

### [Human_NPCs]
| Key | Default | Range | Description |
|---|---|---|---|
| `Total_NPCs` | map-dependent | any | Number of NPCs on the map |
| `Nude_NPCs` | 0 | 0/1 | Remove underwear (ASE only) |
| `NoTames` | 0 | 0/1 | Prevent NPC taming |
| `TamingMode` | 0 | 0/1/2 | 0=walk+knockout, 1=walk only, 2=knockout only |
| `Start_Clothing` | 0 | 0-10 | Starting clothing tier (0=biome-based) |
| `NoHuts` | 0 | 0/1 | Disable hut construction |
| `HomeOwnerChance` | 50 | 1-100 | % chance NPCs build huts |
| `NoBuildDistance` | 250 | 20-250 | Meters from player structures NPCs won't build |
| `NoCorpseHarvest` | 0 | 0/1 | Disable corpse harvesting |
| `NoItemCollecting` | 0 | 0/1 | Disable item collection from victims |
| `NoResourceManagement` | 0 | 0/1 | Disable container item placement |
| `StorageItemsSearchRadius` | 50 | any | Meters to search for storage |
| `StasisDelayTime` | 0 | any | Seconds NPCs harvest while player away |
| `HarvestDamage` | 3 | 0-100 | Harvest damage multiplier |
| `DeliveryDelay` | 120 | any | Seconds between item deposit checks |
| `HarvestSearch` | 3 | any | Cycles before heading to storage |
| `StartFriendly` | 0 | -1/0/1 | -1=disable wave, 0=hostile, 1=friendly |
| `EveryThingUpsetsNPCs` | 0 | 0/1 | 1=any damage triggers hostility |
| `AngryCoolDown` | 300 | any | Seconds NPCs stay hostile after provocation |
| `NoFireArrow` | 0 | 0/1 | Disable fire arrows for on-foot NPCs |
| `RandomNames` | 1 | 0/1 | 1=randomized NPC names |
| `ShowNoMercy` | 0 | 0/1 | 1=always kill knocked out players |
| `NoAutoFire` | 0 | 0/1 | Disable automatic campfire/forge management |
| `PlayerHutDistance` | 25 | 25-250 | Min meters from player to place hut |
| `TurretDistance` | 75 | any | Spacing between X-Plant turrets |
| `TurretsAllowed` | 0 | 0/1 | Enable NPC X-Plant turrets |
| `DamageTurretAmount` | 1.0 | 1-100 | X-Plant strength (1=strongest, 100=weakest) |
| `DenyInventoryAccess` | 0 | 0-100 | % of wild NPCs with locked inventory |
| `MaxWeightRiddenDino` | 1000 | 80-1000 | Max drag weight for NPC-ridden dinos |

### [Human_NPCs_Settings]
All multipliers — default 0.0 (uses mod default). Setting 2.0 = double.

| Key | Effect |
|---|---|
| `Health_x` | Health multiplier |
| `Weight_x` | Carry weight multiplier |
| `Stamina_x` | Stamina multiplier |
| `Food_x` | Food multiplier |
| `Melee_Damage_x` | Damage output multiplier |
| `Speed_x` | Movement speed multiplier |
| `Torpidity_x` | Knockout resistance multiplier |

### [Human_NPCs_Clothing]
| Key | Default | Range | Description |
|---|---|---|---|
| `Clothing_Quality` | 0 | 0-100 | Starting quality adjustment |
| `Archer` / `Bowman` / `Hacker` / `Chopper` / `Scrapper` / `Brawler` / `Huntress` / `Hunter` / `Sentry` / `Guard` / `Trapper` / `Catcher` / `Thumper` / `Clubber` | 0 | 0-10 | Clothing type per role (0=random) |

**Clothing type values:** 1=Cloth, 2=Leather, 3=Fur, 4=Ghillie, 5=Desert, 6=Chitin, 7=Metal (Flak), 8=Riot, 9=Hazard, 10=Mammoth Leather

### [Human_NPCs_Villages]
| Key | Default | Description |
|---|---|---|
| `Total_Villages` | 5 | Max villages on the map at a time |
| `Village_NPCs` | 30 | NPCs each village tries to maintain |
| `Village_Distance` | 3000 | Min meters between villages |

### [Human_NPCs_Base_Attack]
| Key | Default | Range | Description |
|---|---|---|---|
| `BaseAttackNotAllowed` | 0 | 0/1 | 1=disable all base attacks |
| `AttackBaseAmount` | 3 | any | Attack waves per raid |
| `AttackerNumbers` | 15 | any | NPCs per wave |
| `AttackLoot` | 0 | 0-100 | % chance raider drops loot on death |
| `AttackHutRange` | 120 | any | Spawn radius for raiding NPCs (meters) |
| `StartAttackDelay` | 3600 | any | Seconds before first raid is allowed |
| `AttackerPower` | 50 | 10-150 | % of stats vs normal NPCs (10=weak, 150=strong) |
| `MinimumStructures` | 16 | any | Min player structures in range to trigger raid |
| `AttackChance` | 60 | 0-100 | % chance raid triggers each cycle (100=always) |
| `AttackDogs` | 20 | -1 to 100 | % of raiders that ride dinos (-1=disable riding) |
| `AttackDinos` | — | blueprint paths | Comma-separated ground dino blueprints for raiders |
| `AttackFlyers` | — | blueprint paths | Comma-separated flyer blueprints for raiders (6 NPC types use flyers) |

### [Human_NPCs_Loot]
| Key | Default | Range | Description |
|---|---|---|---|
| `Item_Chance` | 50 | -1 to 100 | % chance each Loot_Array item appears (-1=disable crates) |
| `Single_Item_Chance` | 5 | 0-100 | % chance each Single_Loot_Array item appears (1 per item) |
| `Loot_Max` | 20 | any | Max random stack quantity per item |
| `Hut_Loot_Chance` | 50 | 0-100 | % chance a hut contains a loot crate |
| `Default_Array_Replace` | 0 | 0/1 | 0=default+custom, 1=custom only |
| `Default_Single_Array_Replace` | 0 | 0/1 | Same for Single_Loot_Array |
| `Item_Quality` | 1.5 | -1 to 10 | -1=random, 0=normal, 10=ascendant |

### [Human_NPCs_Loot_Array]
| Key | Format | Description |
|---|---|---|
| `Loot_Array` | comma-separated blueprint paths | Stackable items (resources, ammo, consumables) |
| `Single_Loot_Array` | comma-separated blueprint paths | 1-of-each items (weapons, armor, saddles) |

### Default NPC Counts by Map (ASE)
| Map | Default |
|---|---|
| Island | 1000 |
| Genesis / Genesis 2 | 1000 |
| Ragnarok / Valguero | 1500 |
| Crystal Isles | 1000 |
| Scorched Earth | 1200 |
| Extinction | 1000 |
| The Center / Aberration | 500 |
| Other maps | 500 |

### Current Configuration Intent
- **Aggression:** Always hostile (`StartFriendly=0`, `EveryThingUpsetsNPCs=1`, `ShowNoMercy=1`, `AngryCoolDown=0`)
- **No taming:** `NoTames=1`
- **Total NPCs:** 1500
- **Hut building:** 100% chance (`HomeOwnerChance=100`)
- **Health:** 15x (`Health_x=15.0`)
- **Damage:** 250x (`Melee_Damage_x=250.0`)
- **Armor:** Tier 10, quality 100, all roles set to type 7
- **Turrets:** X-Plants enabled, `TurretDistance=5`, `DamageTurretAmount=1` (max strength)
- **Raids:** 5 waves, 15 NPCs/wave, `StartAttackDelay=5`, `AttackChance=100`, `AttackerPower=150`, `MinimumStructures=10`
- **Ground mounts (80%):** Rex, Giganotosaurus, Shadowmane, Stegosaurus
- **Flying mounts:** Pteranodon, Argentavis, Lightning Wyvern, Poison Wyvern, Fire Wyvern, Desmodus
- **Loot:** Random quality (`Item_Quality=-1`), beacon-tier items, `Hut_Loot_Chance=100`

### Do Not Attack Sign — Disabled
Engram hidden via Game.ini:
```ini
OverrideNamedEngramEntries=(EngramClassName="EngramEntry_ZKs_Sign_C",EngramHidden=true)
```
Engram blueprint: `Blueprint'/Game/Mods/Human_NPCs/Objects/ZKs_Sign/EngramEntry_ZKs_Sign.EngramEntry_ZKs_Sign'`

## Confirmed Blueprint Paths (from arkids.net)
### Creatures
| Creature | Class |
|---|---|
| Rex | `Rex_Character_BP_C` |
| Giganotosaurus | `Gigant_Character_BP_C` |
| Shadowmane | `LionFishLion_Character_BP_C` |
| Stegosaurus | `Stego_Character_BP_C` |
| Pteranodon | `Ptero_Character_BP_C` |
| Argentavis | `Argent_Character_BP_C` |
| Lightning Wyvern | `Wyvern_Character_BP_Lightning_C` |
| Poison Wyvern | `Wyvern_Character_BP_Poison_C` |
| Fire Wyvern | `Wyvern_Character_BP_Fire_C` |
| Desmodus | `Desmodus_Character_BP_C` |

### Items
| Item | Class |
|---|---|
| Pump-Action Shotgun | `PrimalItem_WeaponMachinedShotgun_C` |
| Assault Rifle | `PrimalItem_WeaponRifle_C` |
| Fabricated Sniper Rifle | `PrimalItem_WeaponMachinedSniper_C` |
| Fabricated Pistol | `PrimalItem_WeaponMachinedPistol_C` |
| Rocket Launcher | `PrimalItem_WeaponRocketLauncher_C` |
| Longneck Rifle | `PrimalItem_WeaponOneShotRifle_C` |
| Crossbow | `PrimalItem_WeaponCrossbow_C` |
| Compound Bow | `PrimalItem_WeaponCompoundBow_C` |
| Tek Turret | `PrimalItemStructure_TurretTek_C` |
| Heavy Auto Turret | `PrimalItemStructure_HeavyTurret_C` |
| Flak Chestpiece | `PrimalItemArmor_MetalShirt_C` |
| Tek Chestpiece | `PrimalItemArmor_TekShirt_C` |

## DinoRaids Mod
- Config split between `Game.ini` (`[DinoRaids]` section) and `GameUserSettings.ini` (`[DinoRaids]` section)
- `TimeBetweenRaids` set to `7200` in Game.ini (2 hours)

## General Notes
- Always verify blueprint paths against https://arkids.net before adding new creatures or items
- Human NPCs mod config docs should be checked at the Steam discussion links above for exact key names
- The `[Human_NPCs]` turrets (`TurretsAllowed`) control X-Plants, NOT actual Tek/Heavy turrets — those cannot be assigned to NPC bases via INI
