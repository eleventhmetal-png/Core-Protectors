# Core Protectors — Design Document
**Version 2.3** | A 16-bit JRPG inspired by Final Fantasy IV/V, built in Godot 4

---

## Premise

Long ago, Gaia wasn't rock. She was a single living body — one continent breathing, with her heart at the center: the Core. Four crystals grew from her like organs: fire in the south, water in the east, wind in the north, earth in the west. As long as they pulsed together, the land held.

Then something came up from beneath. Not a god. Not a demon. Older than both. The texts call it the **Hollow King** — a being made of the space between things, the dark that exists where light isn't. It didn't want to rule Gaia. It wanted to unmake her, because a whole world is the one thing it can't exist inside of. Wholeness is its enemy.

It struck the Core. Not with an army — with a single wound. The Core cracked, and the crack spread like ice on a lake. The four crystals tore free and scattered, each carrying a piece of Gaia's mind. Where they landed, the land broke apart and lifted — floating islands over an abyss. The abyss between them is where the Hollow King's influence leaks in, and that's where the monsters come from. Not born. Spilled.

---

## The Party: Core Protectors

Four strangers, each woken one night by a dream. A sigil seared onto their soul, manifesting in the real world as a tattoo. The mark calls them together. They gather in **Rootfall**, the first town on the earth island.

**Leader: Kaladin** — human healer. Leads by keeping everyone alive, not by barking orders. His mark sits over his heart where the light starts.

1. **Kaladin** (Human, Healer) — Mark of Water/Earth. Command: *Oath Guard* — absorbs one hit for the party and cleanses one status. Jobs: Cleric → Tidecaller → Saint.
2. **Sarah** (Witch, Thief-Mage) — Mark of Wind/Fire. Command: *Arcane Steal* — steals an item from an enemy, chance to inflict Burn. Jobs: Rogue → Pyromancer → Spellblade.
3. **Gardok** (Goblin, Tank) — Mark of Earth. Command: *Tremor Stomp* — damages all enemies, chance to Slow. Signature: *Stonebind* — slams his palm mark into the floor; the earth grabs every enemy's attention for three turns. Can't be broken by damage, only time. Jobs: Brawler → Geomancer → Juggernaut.
4. **Dylan** (Human-shaped dragon, Camouflage) — Mark of Wind. Command: *Veil Step* — untargetable for one turn, sets up a guaranteed crit next. Jobs: Assassin → Zephyr Blade → Phantom.

---

## Crystal Marks

Each mark is a permanent CrystalMarkData resource: innate passive, signature command, elemental affinity bonuses. The mark is the seed; the crystal is the amplifier. Marks glow when powers are used (pixel-invisible, but the glow is the visual identity of magic).

Resonance is the resource — not MP. After every battle it recharges. Physical attacks are free. Magic costs resonance. Overcast and you risk backlash: the Hollow King's spill hears loud resonance.

---

## Crystal Jobs (Swappable)

Separate from marks. Equipped outside combat. Stat multipliers + second command slot + abilities unlocked via Crystal Points (CP) earned in battle.

- **Elemental Alignment Bonus:** equip a job sharing your mark's element → +20% resonance generation on that element's abilities.
- **Cross-Element Combo Kits:** opposing element keeps your mark's command while gaining the new element's offense — enabling solo Drenched/Burn setups.

---

## The Four Islands

### Earth Island — Rootfall (starting island)
- **Races:** Rock Biters (normal-sized, quiet majority in deep stone layers; notice cracks first) and Dwarves (mine the tunnels, know the island's bones).
- **Town 1: Rootfall** — biggest stable chunk of earth crystal's island. Inn: cave with fire that never goes out. Shop: general goods. Priest: standard.
- **Town 2: Deepcrag** — dwarf settlement carved into a cliff face, reachable only through mine tunnels. Dwarf elder felt the Core crack in his bones. Inn: longhall with massive hearth. Shop: forge, stone-forged gear only. Priest: dwarf geomancer mapping cracks on a living stone table.
- **Crystal location:** learned from the dwarf elder.
- **Side Quests:**
  1. Escort a Rock Biter caravan through a cracked tunnel.
  2. Rescue dwarves trapped in a cave-in.
  3. Find the dwarf elder's lost hammer.

### Fire Island — Cinderreach
- **Races:** Ashborn (humans scarred by the crystal's fall, don't fear heat) and Emberkin (small flame spirits, like Cosmere spren made of living fire; bind to Ashborn as living spells).
- **Town 1: Ashhollow** — inside the hollow of a dead volcano. Inn: lava tube, beds carved in warm rock. Shop: flame-tongued blades, cindermail. Priest: blind Ashborn woman who reads heat instead of seeing.
- **Town 2: Emberdeep** — on the lip of an active vent. The inn IS the fire; you sleep in pockets of cool air. Gear: lighter, faster, hit-and-run.
- **Side Quests:**
  1. Help an Ashborn child find her family in the ash plains.
  2. Bind a runaway Emberkin before it burns down Emberdeep.
  3. Deliver a sealed ember to Emberdeep's priest before it cools.
  4. Hunt down an Ashwraith that's been mimicking villagers.

### Water Island — Tidecall
- **Races:** Tidalfolk (amphibious humans with gills, farm kelp forests) and Deepkin (whale-sized leviathans, elders of the abyss, surface only to speak).
- **Town 1: Saltmere** — stilts above shifting tides. Inn: flipped ship hull, beds from rafters. Shop: coral blades, pearl armor that hardens when wet. Priest: pours seawater over your mark — stings, but resonance returns faster.
- **Town 2: Leviathan's Rest** — natural grotto where Deepkin beach themselves. Carved stone ledges, rope bridges. Heavy, slow gear that hits like a falling anchor.
- **Town 3: Kelpmarket** — Tidalfolk trading post inside a sunken shipwreck. Deepkin come to barter.
- **Side Quests:**
  1. Recover a Deepkin elder's lost tooth from a Drowned nest.
  2. Translate a kelp-scroll that hints at the Core's original shape.
  3. Mediate a trade dispute between Tidalfolk and a Deepkin that could turn violent.

### Wind Island — Skyreach (last, hardest)
- **Races:** Zephyri (tall, hollow bones, never touch ground) and Stormwrens (giant birds, riders double as mount and weapon platform).
- **Town 1: Galehaven** — rope bridges and hanging platforms between three peaks. Inn: nest of woven branches. Shop: wind-cut daggers, glider cloaks. Priest: reads the wind, tells you which way Hollow King influence moves.
- **Town 2: Rookery** — breeding grounds. Loud, chaotic, screeching. Best aerial gear and mounts.
- **Town 3: Cloudstep** — highest peak. Stormwrens refuse to land; air too thin. Only place to see all four other islands at once.
- **Side Quests:**
  1. Race a Stormwren against a Zephyri rival to prove Dylan's worth.
  2. Find a missing hatchling before a Hollow Wing gets it.
  3. Quiet a wind spirit that's been screaming prophecy nobody understands.

---

## Travel: Leyline Bridges

No free flight or sailing. Each crystal reclaimed unlocks a **leyline bridge** — a shimmering path across the abyss, active only while that crystal's resonance holds. Earth → Fire → Water open in sequence. Wind's bridge is unstable until all four crystals are reclaimed. See LeylineBridge.gd in Technical Architecture.

---

## Post-Crystal World State

- Town NPC dialogue shifts via StoryNPC flag system.
- Monsters thin out on reclaimed islands.
- New element-tied gear appears in shops.
- Abyss encounters escalate with a new minion type per crystal (see Abyss Minions below).

---

## Abyss Minions

Extend Combatant.gd with child script AbyssMinion.gd using an @export enum MinionTrait so any abyssal enemy triggers its signature mechanic automatically.

| Minion | Unlock | HP | ATK/MAG | SPD | Affinities | Signature Mechanic |
|---|---|---|---|---|---|---|
| **Grimstone** | Earth Crystal | 380 | 32/10 | 9 | Weak: Wind. Resist: Earth, Fire | Stone Core Regen: heals 10% max HP every 3s unless hit by Wind (cracks core, disables regen 6s). |
| **Ashwraith** | Fire Crystal | 240 | 18/36 | 16 | Weak: Water. Absorb: Fire | Mitosis: at 0 HP, spawns two Ash Sparks (110 HP, 18 MAG, 18 SPD) unless killed by Water. |
| **Drowned** | Water Crystal | 310 | 28/22 | 12 | Weak: Fire, Earth. Absorb: Water | Brine Touch: every physical hit inflicts Drenched (8s), halving party Fire damage. |
| **Hollow Wing** | Wind Crystal | 210 | 12/28 | 22 | Weak: Earth. Resist: Wind | Resonance Siphon: basic attack deals 0 HP damage, drains 20 from party Resonance meter. |

### AbyssMinion.gd (core logic)

```gdscript
class_name AbyssMinion extends Combatant

enum Trait { NONE, GRIMSTONE_REGEN, ASHWRAITH_SPLIT, DROWNED_TOUCH, HOLLOW_SIPHON }
@export var minion_trait: Trait = Trait.NONE
@export var ash_spark_scene: PackedScene

var _regen_timer: float = 0.0
var _regen_suppressed_timer: float = 0.0
var _last_hit_element: BattleTypes.Element = BattleTypes.Element.NONE

func _process(delta: float) -> void:
	super._process(delta)
	if current_hp <= 0:
		return
	if minion_trait == Trait.GRIMSTONE_REGEN:
		if _regen_suppressed_timer > 0.0:
			_regen_suppressed_timer -= delta
			return
		_regen_timer += delta
		if _regen_timer >= 3.0:
			_regen_timer = 0.0
			current_hp = min(max_hp, current_hp + int(max_hp * 0.10))

func calculate_and_apply_damage(raw_power: int, element: BattleTypes.Element) -> Dictionary:
	_last_hit_element = element
	if minion_trait == Trait.GRIMSTONE_REGEN and element == BattleTypes.Element.WIND:
		_regen_suppressed_timer = 6.0
	var result: Dictionary = super.calculate_and_apply_damage(raw_power, element)
	if current_hp <= 0 and minion_trait == Trait.ASHWRAITH_SPLIT and element != BattleTypes.Element.WATER:
		_trigger_ash_split()
	return result

func _trigger_ash_split() -> void:
	if ash_spark_scene == null:
		return
	for i in range(2):
		var spark: Combatant = ash_spark_scene.instantiate()
		get_parent().add_child(spark)
		spark.position = position + Vector2(0, -24 if i == 0 else 24)
```

Drowned's Brine Touch hooks into Combatant's execute_action path: on any physical hit from a Drowned, call `target.apply_status(BattleTypes.StatusEffect.DRENCHED, 8.0)`.

Hollow Wing's Resonance Siphon hooks into BattleManager: on Hollow Wing basic attack, skip HP damage and call `battle_ui.add_resonance(-20.0)`.

---

## Island Bosses

Each island boss tests whether the player has mastered that island's element and the party's Mark commands. **Every boss has a non-Mark fallback** so a player missing an unlocked command is never stuck. All four use a single reusable `IslandBoss.gd` subclass with an @export enum BossType and telegraph signals so players can counter.

### Earth Boss — The Core-Scarred Wyrm (Deepcrag Chasm)
Curls into an **Obsidian Shell** periodically: halves physical damage and charges a party-wide quake. Preferred solution: Gardok's Stonebind to tank the quake, or Wind magic to break its posture. **Fallback:** any hero can simply step out of the quake's blast radius (telegraphed by screen shake) or use a basic-attack focus to break the shell's posture over two consecutive hits.

### Fire Boss — Cinder Sovereign (Emberdeep Caldera)
Summons two Emberkin wisps that buff its attack every turn. Preferred: Sarah's Arcane Steal strips the Flame Mantle; Water abilities extinguish wisps permanently. **Fallback:** any hero can destroy the wisps with two basic attacks each, or focus the Sovereign directly — wisps despawn when it hits 50% HP.

### Water Boss — Abyssal Leviathan (Sunken Trench)
Alternates **Submerged** (untargetable by melee; weak to Wind/Earth shockwaves) and **Tidal Surge** (party-wide Drenched, requiring cleanse). Preferred: Kaladin's Oath Guard. **Fallback:** Drenched is cleansable by any healing item or Kaladin's base Cleric heal; Submerged phase can be skipped by simply waiting it out — the Leviathan surfaces on its own after two turns.

### Wind Boss — Gale Archon (Cloudstep Peak)
Casts Tailwind (permanent Haste on itself) and knocks a hero's ATB gauge to zero on hit. Preferred: Dylan's Veil Step dodges the reset and crits through its evasion aura. **Fallback:** Haste can be removed by any Slow-inflicting basic ability or item; the ATB reset is a one-turn setback, not a death sentence — the party simply acts in whatever order remains. **Soft cap:** no hero's ATB gauge can be reduced below 10, so repeated Archon hits cannot fully brick a character's turn order.

### IslandBoss.gd (core logic)

```gdscript
class_name IslandBoss extends Combatant

enum BossType { CORE_WYRM, CINDER_SOVEREIGN, ABYSSAL_LEVIATHAN, GALE_ARCHON }
@export var boss_type: BossType = BossType.CORE_WYRM
@export var add_scene: PackedScene

var turn_counter: int = 0
var is_shelled: bool = false
var is_submerged: bool = false

signal boss_telegraph(message: String)
signal drain_hero_atb(target: Combatant)

func execute_boss_ai(party: Array[Combatant]) -> Dictionary:
	turn_counter += 1
	var living: Array[Combatant] = party.filter(func(h): return h.current_hp > 0)
	if living.is_empty():
		return {}
	match boss_type:
		BossType.CORE_WYRM:
			return _ai_core_wyrm(living)
		BossType.CINDER_SOVEREIGN:
			return _ai_cinder_sovereign(living)
		BossType.ABYSSAL_LEVIATHAN:
			return _ai_abyssal_leviathan(living)
		BossType.GALE_ARCHON:
			return _ai_gale_archon(living)
	return {}

# 1. EARTH BOSS: Curls into Obsidian Shell every 3rd turn; Wind breaks it
func _ai_core_wyrm(living: Array[Combatant]) -> Dictionary:
	if is_shelled:
		is_shelled = false
		emit_signal("boss_telegraph", "Core-Scarred Wyrm unleashes Tectonic Slam!")
		return { "type": "AOE_DAMAGE", "power": 45, "element": BattleTypes.Element.EARTH }
	elif turn_counter % 3 == 0:
		is_shelled = true
		emit_signal("boss_telegraph", "Wyrm curls into an Obsidian Shell! (Physical resisted)")
		return { "type": "BUFF_SELF" }
	return { "type": "SINGLE_HIT", "target": living.pick_random(), "power": 30, "element": BattleTypes.Element.EARTH }

# 2. FIRE BOSS: Summons Emberkin adds and buffs self (countered by Sarah's Arcane Steal)
func _ai_cinder_sovereign(living: Array[Combatant]) -> Dictionary:
	if turn_counter % 3 == 1 and add_scene:
		var ember: Combatant = add_scene.instantiate()
		get_parent().add_child(ember)
		emit_signal("boss_telegraph", "Cinder Sovereign kindles an Emberkin!")
		return { "type": "SUMMON" }
	return { "type": "SINGLE_HIT", "target": living.pick_random(), "power": 34, "element": BattleTypes.Element.FIRE }

# 3. WATER BOSS: Alternates Submerge (melee immune) and Tidal Surge (party Drenched)
func _ai_abyssal_leviathan(living: Array[Combatant]) -> Dictionary:
	if is_submerged:
		is_submerged = false
		emit_signal("boss_telegraph", "Leviathan breaches with Tidal Surge!")
		return { "type": "AOE_STATUS", "power": 36, "element": BattleTypes.Element.WATER, "status": BattleTypes.StatusEffect.DRENCHED }
	elif turn_counter % 2 == 0:
		is_submerged = true
		emit_signal("boss_telegraph", "Leviathan dives beneath the trench!")
		return { "type": "SUBMERGE" }
	return { "type": "SINGLE_HIT", "target": living.pick_random(), "power": 32, "element": BattleTypes.Element.WATER }

# 4. WIND BOSS: Permanent Haste + Gale Knockback resets a hero's ATB to 0
func _ai_gale_archon(living: Array[Combatant]) -> Dictionary:
	if turn_counter == 1:
		apply_status(BattleTypes.StatusEffect.HASTE, 999.0)
	var target: Combatant = living.pick_random()
	emit_signal("boss_telegraph", "Gale Archon blasts %s back!" % target.combatant_name)
	emit_signal("drain_hero_atb", target)
	return { "type": "SINGLE_HIT", "target": target, "power": 28, "element": BattleTypes.Element.WIND }

func calculate_and_apply_damage(raw_power: int, element: BattleTypes.Element) -> Dictionary:
	if is_shelled and element == BattleTypes.Element.WIND:
		is_shelled = false
		emit_signal("boss_telegraph", "Wind magic shattered the Obsidian Shell!")
	elif is_shelled and element == BattleTypes.Element.NONE:
		raw_power = int(raw_power * 0.25)
	return super.calculate_and_apply_damage(raw_power, element)
```

---

## The Quest & Finale

A relay across the floating islands: begin on Earth (slowest to die), touch the crystal to wake it and reveal the path to Fire (burns brightest when desperate), then Water, then Wind. Each crystal seals its island's spill and strengthens the party's pacts.

**Final Battle: The Hollow King (3 Phases)** — deep in the abyss at the Core. Controlled by HollowKingEncounter.gd state machine.

1. **Phase 1 — The Unmaking:** The King is completely immune to standard HP reduction (0 damage popups). Each party member must channel their Crystal Mark onto one of four floating Core Pedestals while surviving abyssal minion waves. Pedestals glow as each mark lands.
2. **Phase 2 — Resonance Inversion:** Once all four pedestals glow, the King becomes vulnerable — but reverses Resonance rules: spending Resonance heals the King. The party fights with basic attacks, Mark commands, and items while Hollow Wings try to forcibly inject stolen Resonance into the boss.
3. **Phase 3 — Wholeness:** At 25% HP, the King begins a 4-turn cast (Unravel Gaia). All four party members must reach 100% ATB and trigger a synchronized Quad-Resonance Seal simultaneously to press the four crystals back into the Core.

The Hollow King cannot be killed by force — it isn't solid. Only pushed back by wholeness.

### HollowKingEncounter.gd (core logic)

```gdscript
class_name HollowKingEncounter extends Node

enum Phase { PHASE_1_PEDESTALS, PHASE_2_INVERSION, PHASE_3_WHOLENESS, VICTORY }
var current_phase: Phase = Phase.PHASE_1_PEDESTALS

# Tracks which crystal pedestals have been channeled: { Element: bool }
var lit_pedestals: Dictionary = {
	BattleTypes.Element.EARTH: false,
	BattleTypes.Element.FIRE: false,
	BattleTypes.Element.WATER: false,
	BattleTypes.Element.WIND: false
}

var unravel_countdown: float = 20.0 # Seconds to align all 4 ATB bars in Phase 3
@export var hollow_king: Combatant
@export var party: Array[Combatant]

signal phase_changed(new_phase: Phase)
signal core_sealed_victory

func channel_pedestal(element: BattleTypes.Element) -> void:
	if current_phase != Phase.PHASE_1_PEDESTALS:
		return
	lit_pedestals[element] = true
	if not lit_pedestals.values().has(false):
		current_phase = Phase.PHASE_2_INVERSION
		emit_signal("phase_changed", current_phase)

func _process(delta: float) -> void:
	if current_phase == Phase.PHASE_2_INVERSION and hollow_king.current_hp <= int(hollow_king.max_hp * 0.25):
		current_phase = Phase.PHASE_3_WHOLENESS
		emit_signal("phase_changed", current_phase)
	if current_phase == Phase.PHASE_3_WHOLENESS:
		unravel_countdown -= delta
		_check_quad_resonance_alignment()

func _check_quad_resonance_alignment() -> void:
	for hero in party:
		if hero.current_hp <= 0 or not hero.is_ready:
			return
	current_phase = Phase.VICTORY
	emit_signal("core_sealed_victory")
```

---

## Encounter Tables

`EncounterTable.gd` is a Resource that dynamically injects unlocked abyss minions based on GameState.story_flags. Each region gets base_packs of enemy scene arrays; the roll function appends the highest-unlocked minion type.

```gdscript
class_name EncounterTable extends Resource

@export var region_name: String = "Fire Bridge Abyss"
@export var base_packs: Array[Array] = []

func roll_encounter_pack() -> Array[PackedScene]:
	var pack: Array[PackedScene] = base_packs.pick_random().duplicate()
	if GameState.story_flags.get("wind_crystal_restored", false):
		pack.append(preload("res://enemies/HollowWing.tscn"))
	elif GameState.story_flags.get("water_crystal_restored", false):
		pack.append(preload("res://enemies/Drowned.tscn"))
	elif GameState.story_flags.get("fire_crystal_restored", false):
		pack.append(preload("res://enemies/Ashwraith.tscn"))
	elif GameState.story_flags.get("earth_crystal_restored", false):
		pack.append(preload("res://enemies/Grimstone.tscn"))
	return pack
```

---

## Combat Systems (Godot 4)

### ATB Loop
- Real-time gauges governed by Speed stat. Gauge fills: `speed * delta * 2.5`. At 100, turn ready.
- **Wait Mode:** global `BattleState.is_paused` freezes gauges in submenus.
- Turn cycling: tab/shoulder swaps active character in ready queue.
- **ATB Floor:** no hero's gauge can drop below 10 (Gale Archon soft cap).

### Resonance
- Party-shared meter (0–100). Normal actions build +15. Resonance command costs full bar.
- Recharges after battle. Overcast at zero = Hollow King encounter risk.
- Weakness hits award double resonance (2x bonus).

### Elements & Affinities
- Fire, Water, Wind, Earth. Weak 2.0x / Neutral 1.0x / Resist 0.5x / Absorb -1.0x.
- Combos: Drenched + Fire = 0.5x. Statuses: Burn (DoT 5% HP/2s), Drenched, Haste, Slow, Petrify (ATB freeze).
- Damage popups: WEAK (gold, 1.4x scale), RESIST (slate, 0.85x), ABSORB (green, heals).

### Data-Driven Abilities
- `AbilityData` resources: name, power, element, status chance, resonance bonus. .tres files per spell.
- `HeroProfile` persists marks, jobs, CP, mastered abilities across scenes.
- `Combatant.initialize_from_profile()` merges stats, affinities, command lists.

### Battle UI
- Top: shared ResonanceBar. Bottom: CommandPanel (Attack/Magic/Item/Resonance) + PartyStatusPanel (name, HP, ATB bar per row).
- SNES blue windows (#001870 bg, white 2px border, 4px radius). Nearest texture filter.
- Keyboard-driven: ui_up/down/accept. Cursor SFX on focus/press.
- Target selection: arrow keys cycle living enemies, lunge animation, damage popup, hit flash (0.08s modulate 3x).

### Overworld Loop
- `GameState` autoload: party profiles, story flags, opened chests, inventory, last scene/position.
- 16x16 grid movement with tweened interpolation. RayCast2D interaction.
- `TreasureChest`, `StoryNPC` (flag-reactive dialogue), `DialogueBox` (typewriter, queues lines, freezes player).
- Random encounters via step counter → BattleScene → restore position on victory.

---

## Visual & Audio Direction

### Pixel Art Style Guide
- **Tile Grid:** 16x16 pixel tiles with strict per-island color palettes:
  - **Earth:** Browns and grays with one gold accent for crystal glow.
  - **Fire:** Deep reds and charcoal with bright orange highlights.
  - **Water:** Teals and deep navy with pearl white accents.
  - **Wind:** Sky blue and crisp white with silver highlights.
- **Character Sprites:** 32x32 pixels with chunky 16-bit proportions and distinct, readable silhouettes.
- **Boss Sprites:** 64x64 canvas for the four Island Bosses and the Hollow King.
- **UI Style:** Clean pixel serif font in crisp white over classic royal blue (#001870) PanelContainer windows with 2px white borders. Nearest texture filter in project settings.

### Aseprite Production Pipeline
1. **Tilesets:** 16x16 grid; organize each island into a single 128x128 atlas (ground, walls, cliffs, props, animated_water_lava).
2. **Characters & Monsters:** 32x32 canvas for party sprites and standard enemies; 64x64 for bosses.
3. **Animation Frame Budget (minimum viable):**
   - Overworld Heroes: 2-frame idle/walk cycle per direction (Down, Up, Side — flip for Left/Right) = 6 frames per character.
   - Battle Heroes: Idle (2), Attack Lunge (1), Cast/Mark Glow (2, bright palette-swapped tattoo pixels), Hurt (1), KO (1) = 7 frames per character.
4. Godot import: Default Texture Filter set to Nearest in Project Settings > Rendering > Textures.

### Music Direction
- **Format:** 4-channel SNES-inspired chiptune. Compose in FamiStudio, DefleMask, or Furnace Tracker; export to .ogg loops at 120 BPM (World Theme) and 60 BPM (Hollow King Theme).
- **Core Motif (4 notes):** D4 – F4 – A4 – E5 (D Dorian, hopeful yet ancient).
- **Channel 1 — Earth (Triangle/Sub-Bass):** steady quarter-note root ostinato (D2 – D2 – C2 – A1).
- **Channel 2 — Fire (25% Pulse Wave):** fast 16th-note broken chord arpeggios over the bass pulse.
- **Channel 3 — Water (50% Pulse Wave):** slow half-note counter-melody (A4 – G4 – F4 – E4 – D4) with soft vibrato.
- **Channel 4 — Wind (Noise + High Lead):** crisp hi-hat groove plus octave-doubled high melody (D5 – F5 – A5 – E6).
- **Hollow King Inversion:** same four-note motif inverted downward (D4 – B3 – G3 – C3), halved tempo at 60 BPM, Channel 3 drenched in detuned reverb. Players physically hear the world healing as crystals return.
- **MusicManager.gd:** four synchronized AudioStreamPlayers, all start at 0.0s to stay in phase. `start_world_theme()` plays all; `refresh_channel_volumes()` fades each channel from -80dB to 0dB over 1.5s when its crystal flag unlocks.

---

## Playtest Balance Pass: Resonance & CP Progression

| Metric | Target Value | Design Rationale |
|---|---|---|
| Starting Resonance | 30 / 100 | Lets players cast one starter spell immediately without trivializing turn 1. |
| Basic Attack Gain | +15 Resonance | 4–5 basic attacks across the party fills a full 100 bar for an ultimate. |
| Elemental Weakness Hit | +30 Resonance (2x) | Rewards matching crystal elements; fills the bar in ~3 turns. |
| Tier 1 Spell Cost | 20 Resonance | Sustainable every 1–2 turns in normal fights. |
| Tier 2 / AoE Spell Cost | 40 Resonance | Requires intentional setup or weakness chaining. |
| Resonance Ultimate Cost | 100 Resonance | Full-bar payoff; resets meter to 0 (triggering Overcast tension). |
| CP per Trash Battle | 10 – 15 CP | Unlocks the first Job skill (30 CP) after 2–3 fights on Earth Island. |
| CP per Island Boss | 100 CP | Guarantees a major tier unlock right as a new Leyline Bridge opens. |

---

## Technical Architecture (Godot 4)

### Global Autoloads
- `GameState.gd` — party_profiles, story_flags, opened_chests, inventory, last_overworld_scene, last_player_position.
- `DialogueBox.gd` — typewriter CanvasLayer queue that freezes OverworldPlayer during conversations.
- `BattleTypes.gd` — shared enums: Element (NONE/FIRE/WATER/WIND/EARTH), Affinity (WEAK/NEUTRAL/RESIST/ABSORB), StatusEffect (NONE/BURN/DRENCHED/HASTE/SLOW/PETRIFY).
- `MusicManager.gd` — four synchronized AudioStreamPlayers (EarthBass, FireArp, WaterMelody, WindHarmony), all start at 0.0s to stay in phase. `start_world_theme()` plays all; `refresh_channel_volumes()` fades each channel from -80dB to 0dB over 1.5s when its crystal flag unlocks. Hollow King theme swaps in on inversion.
- `SaveManager.gd` — save/load wrappers around ResourceSaver/ResourceLoader.

### Overworld Loop
- `OverworldPlayer.gd` — 16x16 tweened grid movement with directional RayCast2D (InteractRay) calling on_interact() on TreasureChest and StoryNPC nodes.
- `TreasureChest.gd` — persistent via GameState.opened_chests, swaps closed/open texture.
- `StoryNPC.gd` — flag-reactive dialogue, optional flag-setting on talk.
- `LeylineBridge.gd` — Area2D + TileMapLayer gate. @export required_flags array and target_island_scene. Bridge visuals and monitoring toggle on flag check. On body_entered (OverworldPlayer): save spawn position to GameState, change_scene_to_file target island.

### Battle Loop (BattleScene.tscn)
- `BattleManager.gd` — state machine (IDLE, SELECTING_TARGET, EXECUTING_ACTION) coordinating BattleUI, TargetCursor, enemy AI, DamagePopup feedback. Hooks Hollow Wing resonance drain and Ashwraith spawn triggers.
- `Combatant.gd` — real-time ATB (speed * delta * 2.5), status timers, elemental damage multipliers, initialize_from_profile().
- `AbyssMinion.gd` — extends Combatant with MinionTrait enum and signature mechanics (see Abyss Minions).
- `IslandBoss.gd` — extends Combatant with BossType enum, telegraph signals, and per-boss AI (see Island Bosses).
- `HollowKingEncounter.gd` — final battle phase state machine (see The Quest & Finale).
- `EncounterTable.gd` — Resource-driven encounter packs with dynamic minion escalation (see Encounter Tables).
- `BattleUI.gd` — ResonanceBar, CommandPanel, PartyStatusPanel, keyboard nav, advance_to_next_turn().
- `DamagePopup.gd` — launch_elemental() with WEAK/RESIST/ABSORB visual tags.
- `HeroProfile.gd` / `CrystalMarkData.gd` / `JobData.gd` / `AbilityData.gd` — modular .tres resources driving stats, affinities, CP progression, command menus.

### Save System & Title Screen
- `SaveGameData.gd` (Resource): party_profiles, story_flags, opened_chests, inventory, current_scene, player_position. Serialized via ResourceSaver to user://save_slot_1.tres.
- `TitleScreen.tscn`: dark abyss backdrop, four glowing crystal icons at cardinal points, pixel serif title CORE PROTECTORS, three keyboard buttons (New Game, Continue — auto-disabled if save file missing, Quit).

### Scene Transitions
- Save current scene path + player coordinates to GameState before battle; restore on victory return.

---

## Open Items

1. Implement SaveManager.gd + TitleScreen.gd scripts (template).
2. Build first Aseprite-to-Godot TileMapLayer scene for Rootfall.
3. Write BattleManager hooks for Hollow Wing resonance drain and Ashwraith spawning.
4. Prototype HollowKingEncounter phase transitions in a test scene.
5. Compose the four-note core motif in FamiStudio and test channel layering.
6. First playtest pass on Earth Island vertical slice: Rootfall → Deepcrag → Core-Scarred Wyrm.

---

*Last updated: 2026-11-13. Version 2.3 adds IslandBoss.gd, HollowKingEncounter.gd, EncounterTable.gd, chiptune composition specs, Aseprite pipeline, balance tables, and the Gale Archon ATB soft cap.*