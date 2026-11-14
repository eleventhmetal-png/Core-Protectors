# Core Protectors — Design Document
**Version 2.1** | A 16-bit JRPG inspired by Final Fantasy IV/V, built in Godot 4

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

No free flight or sailing. Each crystal reclaimed unlocks a **leyline bridge** — a shimmering path across the abyss, active only while that crystal's resonance holds. Earth → Fire → Water open in sequence. Wind's bridge is unstable until all four crystals are reclaimed.

---

## Post-Crystal World State

- Town NPC dialogue shifts via StoryNPC flag system.
- Monsters thin out on reclaimed islands.
- New element-tied gear appears in shops.
- Abyss encounters escalate with a new minion type per crystal:
  - **Earth:** Grimstone — rock golems that regenerate unless broken fast.
  - **Fire:** Ashwraiths — split into two weaker copies on death.
  - **Water:** Drowned — bloated corpses that inflict Drenched on hit.
  - **Wind:** Hollow Wing — bat-like, steals resonance instead of dealing damage.

---

## The Quest

Relay across islands. Start on earth (slowest to die). Touch the crystal, it wakes, points to the next. Fire (burns brightest when desperate), then water, then wind.

Each crystal reclaimed: seals that island's spill + grants a new pact.

**Final fight:** at the Core, down in the abyss. The Hollow King can't be killed by force — it isn't solid. Only pushed back by wholeness. The four crystals pressed back into the Core at the same moment, party holding them while Gaia heals.

---

## Combat Systems (Godot 4)

### ATB Loop
- Real-time gauges governed by Speed stat. Gauge fills: `speed * delta * 2.5`. At 100, turn ready.
- **Wait Mode:** global `BattleState.is_paused` freezes gauges in submenus.
- Turn cycling: tab/shoulder swaps active character in ready queue.

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
- **UI Style:** Clean pixel serif font in crisp white over classic royal blue (#001870) PanelContainer windows with 2px white borders. Nearest texture filter in project settings.

### Music Direction
- **Format:** 4-channel SNES-inspired chiptune.
- **Dynamic Crystal Motif:** One core musical motif that layers in a new channel as each crystal is restored:
  1. Earth: Low, steady bass pulse.
  2. Fire: Adds a fast, driving arpeggio.
  3. Water: Layers in a rising, lyrical melody.
  4. Wind: Fullest four-channel harmonic arrangement.
- **Hollow King Theme:** Uses the exact same four notes, inverted and slowed down — players physically hear the world healing as crystals return.

---

## Technical Architecture (Godot 4)

### Global Autoloads
- `GameState.gd` — party_profiles, story_flags, opened_chests, inventory, last_overworld_scene, last_player_position.
- `DialogueBox.gd` — typewriter CanvasLayer queue that freezes OverworldPlayer during conversations.
- `BattleTypes.gd` — shared enums: Element (NONE/FIRE/WATER/WIND/EARTH), Affinity (WEAK/NEUTRAL/RESIST/ABSORB), StatusEffect (NONE/BURN/DRENCHED/HASTE/SLOW/PETRIFY).

### Overworld Loop
- `OverworldPlayer.gd` — 16x16 tweened grid movement with directional RayCast2D (InteractRay) calling on_interact() on TreasureChest and StoryNPC nodes.
- `TreasureChest.gd` — persistent via GameState.opened_chests, swaps closed/open texture.
- `StoryNPC.gd` — flag-reactive dialogue, optional flag-setting on talk.

### Battle Loop (BattleScene.tscn)
- `BattleManager.gd` — state machine (IDLE, SELECTING_TARGET, EXECUTING_ACTION) coordinating BattleUI, TargetCursor, enemy AI, DamagePopup feedback.
- `Combatant.gd` — real-time ATB (speed * delta * 2.5), status timers, elemental damage multipliers, initialize_from_profile().
- `BattleUI.gd` — ResonanceBar, CommandPanel, PartyStatusPanel, keyboard nav, advance_to_next_turn().
- `DamagePopup.gd` — launch_elemental() with WEAK/RESIST/ABSORB visual tags.
- `HeroProfile.gd` / `CrystalMarkData.gd` / `JobData.gd` / `AbilityData.gd` — modular .tres resources driving stats, affinities, CP progression, command menus.

### Scene Transitions
- Save current scene path + player coordinates to GameState before battle.
- Restore position on victory return to overworld.

---

## Open Items

- [ ] Boss designs per island
- [ ] Final boss choreography (Hollow King)
- [ ] Save system
- [ ] Title screen
- [ ] Hollow King minion scripts (Grimstone regen, Ashwraith split, Hollow Wing resonance theft)
- [ ] 4-channel dynamic music & leyline bridge controller
- [ ] Abyss minion full stat blocks

---

*Built with Ben Ryan & son. Godot 4 / GDScript. Inspired by FF4, FF5, Cosmere (Sanderson), WoW elemental systems.*