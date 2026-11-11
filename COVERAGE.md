# Encounter Generator — Coverage & Verification

## Canonical roster totals (file truth)
- Demons roster: **361** unique demons (DEMON-ROSTER.md states FINAL 361 = 247 types + 114 lords). The build order said 355 — superseded by file truth, noted here.
- Undead roster: **346** unique undead (+2 borderline).
- Sentient Constructs roster: **92** unique entries.
- NPCs cast: **150** (141 headings parsed automatically; 9 headings use variant formatting and were not machine-parsed — named gap).
- APOC-VTT monster registry: **1,486** (seed-vtt_monsters.json, value.monsters; Monsternomicon I at 2002-original values).

## Extraction (work/build.py)
- Raw stat-block sections parsed: demons batches 244, undead batches 408, constructs batches 103.
- Distinct creatures after dedup across all sources: **2096**.
- Full published Environment + Organization extracted: **380**.
- Type-mapped only (no env/org line recovered; Organization shown as "Solitary (see source book)" — no group numbers invented): **1716**.
- Pool after screening: 2031 as originally built (2033 after the 2026-11-09 correction pass restored the two substring false positives to eligibility).

## Exclusions (APOC screening)
- **Dragons: 56 excluded entirely** — Dragon-type, any name containing "dragon", dracolich (undead dragon — excluded too, per correction). Shaun (2026-11-09): "Dragons haven't been seen in a thousand years." No rollable dragon entry, no deep-underground tail, no named sub-roll. Flavor note only in table headers. Excluded names (first 200): Dragonflesh Golem, Glass Dragonfly, Angel, Astral Deva, Angel, Planetar, Angel, Solar, Dragon Turtle, Dragon, Black, Dragon, Blue, Dragon, Brass, Dragon, Bronze, Dragon, Copper, Dragon, Gold, Dragon, Green, Dragon, Red, Dragon, Silver, Dragon, White, Dragonne, Half-Dragon, Lammasu, Golden Protector, Pseudodragon, Wyvern, Dragon, Amethyst, Dragon, Crystal, Dragon, Emerald, Dragon, Sapphire, Dragon, Topaz, Crested Felldrake, Spitting Felldrake, Horned Felldrake, Golem, Dragonflesh, Hellfire Wyrm, Linnorm, Gray, Linnorm, Dread, Corpse Tearer, Ashnephos, Charsaug, Ambush Drake, Dracotaur, Dragon Eel, Rage Drake, Fiendish Rage Drake, Ssvaklor, Greater Ssvaklor, Sea Drake, Sunwyrm, Chorranathau the Inscrutable, Morlicantha, Dragon Fish, Scaefang, Blighterghast, Halfaug, Dragonspawn, Korvath the Ashen, Grimnoshtadrano, Gaulauntyr, Maaril
- Drow / tiefling: 7 excluded (Elf, Drow, Planetouched, Tiefling, Drow Priestess, Lolth-Touched Drow Ranger, Zesskar, Krixx Vane, Threnos Ashborn — the last three are tiefling-named NPC/monster records caught by the type/race line).
- **False positives reversed (correction pass 2026-11-09):** the original substring filter (`'drow' in name`) also excluded two non-drow: **Drowned** — a Medium Undead, Monster Manual III p.46; restored to the tables (see Correction Pass below) — and **Tirbana Drowser** — a Monster Manual V magical beast (a tirbana hive caste; "drowser" = drowsy caste, no relation to drow elves); restored to the eligible pool, not placed on any table in this pass. The filter in build.py and the check in verify.py are now word-boundary (`\bdrow\b` / `\btiefling\b`): genuine drow (Elf, Drow; Drow Priestess; Lolth-Touched Drow Ranger) and tiefling entries remain excluded and verification confirms zero on any table.
- Celestials (Angel/Planetar/Solar) also removed from the pool under the no-planar-arrivals rule (folded into the dragon-exclusion count line in code — see build.py is_dragon()).

## Placement
- Tables: **19** — 11 terrain tables + Road/Trail generic, Bastion Streets, Bastion Districts/Interior, Underground Deep Dark, Underground Dungeon/Interior, Ruins Interior, River/Lake/Coast Shoreline, River/Lake/Coast Open Water.
- Distinct creatures placed across all tables: **341** (346 as originally built; −5 net in the 2026-11-09 correction pass: renames merged four artifact-duplicates into names already on the tables — Mohrg, Vampire Spawn, Caryatid Column, Zodar — and the Drowned took the slots of Corrupture and Desmodu, which left the tables, for a net −1 there; Squid, Giant stays on Open Water).
- Per-table entries: Badlands — Open Wastes=23, Plains=22, Forest=22, Hills=22, Mountains=22, Desert=22, Swamp/Marsh=22, River/Lake/Coast=22, Underground=22, Ruins=23, Bastion=22, Road/Trail (generic — any terrain)=20, Bastion Streets=20, Bastion Districts / Interior=18, Underground — Deep Dark=20, Underground — Dungeon / Interior=20, Ruins Interior=21, River/Lake/Coast — Shoreline=18, River/Lake/Coast — Open Water=18

## Gaps — named honestly
- Only 380 of 2096 distinct creatures yielded a machine-readable Environment+Organization pair from the batch files; the rest are type/description-mapped and flagged in encounters.json (environment field reads "Type-mapped").
- 9 of 150 NPC headings not auto-parsed (variant heading format).
- ~~Some roster batch entries cite the batch file rather than a book~~ — RESOLVED in the 2026-11-09 correction pass: all batch-file citations were replaced with book citations from the roster indexes / batch entry headings (62 source fixes; zero remain, zero unresolved).
- Bastion flying-creature screening: Bastion pools are restricted by category (Humanoid/Construct/Giant/Vermin/NPC/Warforged) — a per-creature flight check was not possible for VTT-only entries lacking speed lines; category restriction is the control used.

- Known duplicate: Underground — Deep Dark carries Mohrg in two slots (bands 01–07 and 16–24) — two extractions of the same MM I creature with different published Organization lines (type-mapped vs the full MM I line); left as two slots, named here rather than silently merged.

## Correction Pass — 2026-11-09

### Drowned restored
Published data (undead roster BATCH-3-MM2-5-FF, Monster Manual III p.46): Medium Undead, CR 9, Environment "Any aquatic and underground", Organization "Solitary, pair, or crew (3–12)", swim 30 ft.; APOC adjustment: max hp 260, turn resistance +4 re-rolled per round. Placed by replacing a type-mapped CR 9 slot at the identical band in each table its Environment supports (bands unchanged, tables still sum to 100):
- **River/Lake/Coast, band 84–87** — replaced Squid, Giant (CR 9, type-mapped).
- **River/Lake/Coast — Open Water, band 82–86** — replaced Corrupture (CR 9, type-mapped).
- **Underground, band 82–85** — replaced Desmodu (CR 9, type-mapped).
Not placed on any Bastion table (undead — Melairshield-barred); verification checks this explicitly.

### Extraction-noise cleanup (before → after)
Renames (name artifacts): Badlands 46–50: "10 Gravetouched Ghoul Harpy" → "Gravetouched Ghoul Harpy"; Badlands 56–60: "23 Bloodmote Cloud" → "Bloodmote Cloud"; Badlands 71–74: "22 Mohrg" → "Mohrg"; Plains 37–42: "Published stat block" → "Carrionette"; Plains 64–67: "CARYATID COLUMN [3.0-format as published]" → "Caryatid Column"; Plains 92–94: "5B-5. The Lord Of Blades" → "The Lord Of Blades"; Plains 98–98: "HELLFIRE GOLEM [3.0-format as published]" → "Hellfire Golem"; Forest 61–65: "2b. Avvite" → "Avvite"; Forest 66–70: "Sample: CADAVER LORD" → "Cadaver Lord"; Hills 66–70: "Sample: CADAVER LORD" → "Cadaver Lord"; Swamp/Marsh 53–57: "12 Sample" → "Kobold Wraith"; Swamp/Marsh 85–88: "5 Doru, Infectious Blasheme" → "Doru, Infectious Blasheme"; Bastion 53–58: "Sample Incarnate Construct" → "Incarnate Construct (sample)"; Bastion 98–98: "BLACKSTONE GIGANT [3.0-format as published]" → "Blackstone Gigant"; Bastion Streets 32–38: "MAUG [3.0-format as published]" → "Maug"; Bastion Streets 57–62: "CARYATID COLUMN [3.0-format as published]" → "Caryatid Column"; Underground — Deep Dark 1–7: "22 Mohrg" → "Mohrg"; Underground — Deep Dark 48–53: "BRAIN GOLEM [3.0-format as published]" → "Brain Golem"; Underground — Deep Dark 77–80: "As published" → "Death Centaur (Bone Golem)"; Underground — Deep Dark 85–87: "5B-7. Sample 15Th-Level Npc Artificer" → "Sample 15th-Level NPC Artificer (Warforged)"; Underground — Deep Dark 91–92: "ZODAR [3.0-format as published]" → "Zodar"; Underground — Dungeon / Interior 50–55: "2b. Avvite" → "Avvite"; Ruins Interior 22–28: "2a. Gibborite" → "Gibborite"; Ruins Interior 35–40: "4 Vampire Spawn" → "Vampire Spawn"; Ruins Interior 93–95: "As published" → "Death Centaur (Bone Golem)"; Plains 92–94: "The Lord Of Blades" → "The Lord of Blades"; Hills 91–93: "Aspect Of Vecna" → "Aspect of Vecna"; Ruins 76–79: "Mob Of Zombies" → "Mob of Zombies"; Bastion Districts / Interior 56–62: "Stormcloud Of Thoon" → "Stormcloud of Thoon".
- The Plains "Published stat block" was the Carrionette (Dragon Magazine #339, constructs BATCH-6-WEB §1 — its stat-block subheading was parsed as the creature name); the two "As published" slots were the Death Centaur (Bone Golem) (Constructs: It Is Alive p.15 — the book's only CR 13 full creature); Swamp/Marsh's "12 Sample" was the Kobold Wraith (Savage Species p.138, §2.12 sample); "Sample: CADAVER LORD" (×2) is the Cadaver Lord, sample of the Undead Lord template (Tome of Horrors II App. B).

Organization lines truncated where they bled into other stat fields: Plains / Schir: "Solitary or pack (3–8), Challenge Rating: 4, Treasure: Standard, Alignment: Always chaotic…" → "Solitary or pack (3–8)"; Forest / Sythyss: "Solitary or gang (2–5). Challenge Rating: Same as base creature +1. Alignment: Always lawf…" → "Solitary or gang (2–5)"; Forest / Avvite: "Solitary or pack (1 avvite dire wolf and 4–7 followers); Challenge Rating: 5; Treasure: No…" → "Solitary or pack (1 avvite dire wolf and 4–7 followers)"; Underground / Swordwraith: "Solitary, company (2–8), or squadron (11–20 plus 1 leader of 6th–9th level) (sample; the t…" → "Solitary, company (2–8), or squadron (11–20 plus 1 leader of 6th–9th level)"; Underground — Dungeon / Interior / Avvite: "Solitary or pack (1 avvite dire wolf and 4–7 followers); Challenge Rating: 5; Treasure: No…" → "Solitary or pack (1 avvite dire wolf and 4–7 followers)"; Ruins Interior / Gibborite: "Solitary or squadron (one gibborite with 3d6 humanoid barbarians, fighters, or warriors of…" → "Solitary or squadron (one gibborite with 3d6 humanoid barbarians, fighters, or warriors of 1st to 3rd level)".
Environment lines with the same bleed were likewise truncated (Avvite ×2, Gibborite, Brine Zombie ×2, Apparition, Skeleton Warrior).

Source citations: **62 batch-file citations replaced with book citations** (from the undead/demon roster indexes, constructs master Source lines, and batch entry headings), including six hand-verified after the automated pass: Lifespark Construct → Advanced Bestiary; The Lord of Blades → Five Nations; Avvite and Gibborite → Anger of Angels; Clockwork Mender Swarm → Monster Manual IV; and ten "Monster Manual" results specified to Monster Manual I (Mohrg, Mummy, Devourer, Vampire Spawn, Bodak, Marilith). **Unresolved source citations remaining: none.**

## Verification (work/verify.py)
```
PASS — Badlands: bands sum 100, contiguous 1–100 (23 entries)
PASS — Plains: bands sum 100, contiguous 1–100 (22 entries)
PASS — Forest: bands sum 100, contiguous 1–100 (22 entries)
PASS — Hills: bands sum 100, contiguous 1–100 (22 entries)
PASS — Mountains: bands sum 100, contiguous 1–100 (22 entries)
PASS — Desert: bands sum 100, contiguous 1–100 (22 entries)
PASS — Swamp/Marsh: bands sum 100, contiguous 1–100 (22 entries)
PASS — River/Lake/Coast: bands sum 100, contiguous 1–100 (22 entries)
PASS — Underground: bands sum 100, contiguous 1–100 (22 entries)
PASS — Ruins: bands sum 100, contiguous 1–100 (23 entries)
PASS — Bastion: bands sum 100, contiguous 1–100 (22 entries)
PASS — Road/Trail (generic — any terrain): bands sum 100, contiguous 1–100 (20 entries)
PASS — Bastion Streets: bands sum 100, contiguous 1–100 (20 entries)
PASS — Bastion Districts / Interior: bands sum 100, contiguous 1–100 (18 entries)
PASS — Underground — Deep Dark: bands sum 100, contiguous 1–100 (20 entries)
PASS — Underground — Dungeon / Interior: bands sum 100, contiguous 1–100 (20 entries)
PASS — Ruins Interior: bands sum 100, contiguous 1–100 (21 entries)
PASS — River/Lake/Coast — Shoreline: bands sum 100, contiguous 1–100 (18 entries)
PASS — River/Lake/Coast — Open Water: bands sum 100, contiguous 1–100 (18 entries)
PASS — Zero drow / tiefling entries in any table (word-boundary check — Drowned is not a drow)
PASS — Drowned present in River/Lake/Coast, Open Water, Underground: ['River/Lake/Coast', 'Underground', 'River/Lake/Coast — Open Water']
PASS — Drowned NOT on any Bastion table (Melairshield bars undead)
PASS — Zero generic-artifact names ('Published stat block' / 'As published') and zero leading-number or bracketed names
PASS — No Organization field contains 'Challenge Rating:'/'Treasure:'/'Alignment:'/'Advancement:' bleed
PASS — No batch-file (.md) source citations remain in any table
PASS — Zero dragon / dracolich entries in any table (Shaun 2026-11-09: unseen in a thousand years)
PASS — Zero Dragon-type entries in any table
PASS — Bastion: no demons/undead/dragons []
PASS — Bastion: only ward-allowed categories (patrols/citizens/Warforged/War-Torn/constructs/vermin/NPCs)
PASS — Bastion Streets: no demons/undead/dragons []
PASS — Bastion Streets: only ward-allowed categories (patrols/citizens/Warforged/War-Torn/constructs/vermin/NPCs)
PASS — Bastion Districts / Interior: no demons/undead/dragons []
PASS — Bastion Districts / Interior: only ward-allowed categories (patrols/citizens/Warforged/War-Torn/constructs/vermin/NPCs)
PASS — Saint James only at tail of Badlands/Ruins tables: [('Badlands', 100), ('Ruins', 100), ('Ruins Interior', 100)]
Tail (99–100) entries across tables: Aspect of Dispater, Brammin Ironroot, Crawling Head, Dry Lich, Elite Demon War Mount, Giant, Death, Giant, Eldritch, Hellfire Engine, Isitwalangcengce, Kumbhakarna, Lucent Worm, Ocean Strider, Prismatic Golem, Ragewind, Saint James, Scouring Slinger, Teratomorph, The Black Duke, Titan

OVERALL: PASS
```

---

## Improvement pass (2026-11-09) — stat blocks, pictures, ecology audit

### Stat blocks — merged onto every entry (encounters.json `statblock`, roller result card, STATBLOCKS.md)
- Coverage (339 distinct placed creatures): **125 full, 214 partial, 0 missing.** Full = complete published stat block verbatim from the roster (APOC notes kept separate). Partial = VTT-registry type line + CR + published description, labeled partial — nothing invented. Saint James stays partial-by-design (established facts only).
- Staging validation: the staged file held 326 blocks for 341 placed names (111 full / 215 partial); my own count against encounters.json agreed, and the 15 staged-missing were then recovered by hand (below), and 3 ecology/hand swaps displaced artifact names (Steel Kraken / '2b. Avvite' / Water Elemental), landing at 339 distinct.
### Manual recovery — all 15 flagged blocks recovered as FULL (none truly missing)
- **Avvite** — full — Roster — BATCH-6-THIRD-PARTY.md (manual recovery, improvement pass; 12 stat fields)
- **Gibborite** — full — Roster — BATCH-6-THIRD-PARTY.md (manual recovery, improvement pass; 11 stat fields)
- **Cerebrilith** — full — Roster — BATCH-4-PLANAR-ETC.md (manual recovery, improvement pass; 12 stat fields)
- **Curst** — full — Roster — BATCH-6B-LEOF-TOM-FINISHER.md (manual recovery, improvement pass; 12 stat fields)
- **Incarnate Construct (sample)** — full — Roster — BATCH-5A-REST-OF-LIBRARY.md (manual recovery, improvement pass; 11 stat fields)
- **Carrionette** — full — Roster — BATCH-6-WEB.md (manual recovery, improvement pass; 12 stat fields)
- **Tin Golem** — full — Roster — BATCH-6-WEB.md (manual recovery, improvement pass; 12 stat fields)
- **Lifespark Construct** — full — Roster — BATCH-6-WEB.md (manual recovery, improvement pass; 12 stat fields)
- **Clockwork Horror** — full — Roster — BATCH-3A-MM2-MM3.md (manual recovery, improvement pass; 10 stat fields)
- **Raggamoffyn** — full — Roster — BATCH-3A-MM2-MM3.md (manual recovery, improvement pass; 9 stat fields)
- **Death Centaur (Bone Golem)** — full — Roster — BATCH-4-IT-IS-ALIVE.md (manual recovery, improvement pass; 10 stat fields)
- **The Lord of Blades** — full — Roster — BATCH-5B-EBERRON-REST.md (manual recovery, improvement pass; 9 stat fields)
- **Sample 15th-Level NPC Artificer (Warforged)** — full — Roster — BATCH-5B-EBERRON-REST.md (manual recovery, improvement pass; 9 stat fields)
- **Dire Maggot** — full — Roster — BATCH-1-LIBRIS-MORTIS.md (manual recovery, improvement pass; 6 stat fields)
- **Doru, Infectious Blasheme** — full — Roster — BATCH-7-WEB-SAVAGE-RAVENLOFT.md (manual recovery, improvement pass; 9 stat fields)
- Dire Maggot's block is the Undead roster's compact one-line published form (Libris Mortis p.95; the roster itself flags its size line as garbled in the source mirror — reproduced as filed). Doru's block is Expedition to Castle Ravenloft's compact tactical format, cross-referenced to the Blaspheme's primary Libris Mortis printing.
- Also upgraded during the merge: 27 entries had their table Environment replaced with the published Environment line from their stat block, and 34 entries had number-appearing upgraded from the block's published Organization line.

### Pictures — matched per Shaun's roster picture law (that creature's own art only; no substitutes, no placeholders, nothing generated in this pass)
- **119 of 339 distinct placed creatures have a picture on file** (copied to `pictures/`, slug-named, credited per the roster indexes; GENERATED pictures keep their GENERATED credit). By source pool: Undead roster pictures: 64; Demons roster pictures: 23; Saint James file (approved winged picture): 1; Constructs roster pictures: 24; NPC portraits (NPCs page assets): 7.
- APOC-VTT picture gap (honest): the VTT seed references portrait/token paths (`vtt-monsters/<slug>.png`), but those image files are **not in the workspace** (they live in the VTT site's storage) — so VTT-only creatures without a roster picture are 'none on file' rather than borrowed art.
- **No appropriate picture on file (220 of the 339 placed):** Abeil Queen, Aboleth Mage, Air Weird, Alchemical Golem, Animated Object, Arkamoi, Armand, Aspect of Dispater, Automaton Hammerer, Avvite, Beholder, Gauth, Belker, Blackspawn Stalker, Bladerager Troll, Blood Ape, Bluespawn Ambusher, Bluespawn Burrower, Bluespawn Stormlizard, Boar, Boatman, Bog Trog, Boggle, Breathdrinker, Bronze Serpent, Brood Keeper Larva Swarm, Bugbear, Camel, Cataphract Beetle, Catoblepas, Cerebral Symbiont, Mind Leech, Chain Golem, Chaos Beast, Chelicera, Chimera, Chuul, Cinder Swarm, Clockroach, Clockwork Horror, Adamantine, Clockwork Mender Swarm, Clockwork Stallion, Crocodile, Giant, Cullenrock Barnacle, Cyclonic Ravager, Cyclops, Darktentacles, Darkweaver, Demon, Kastighur, Demon, Zovvut, Desert Hydra (5-headed), Devil Rat Swarm, Dinosaur, Bloodstriker, Dinosaur, Cryptoclidus, Dinosaur, Deinonychus, Dinosaur, Triceratops, Dire Bear, Dire Elephant, Dire Maggot, Dolomite, Doru, Infectious Blasheme, Eagle, Earth Weird, Elder Spawn of Juiblex, Elemental, Earth, Elf, Aquatic, Elf, Gray, Elite Demon War Mount, Ethergaunt, Black, Ethon, Ettercap, Farrow, Fiendish Cleric of Yeenoghu, Fiendish Symbiont, Fiendish Familiar, Fire Bat, Gargoyle, Gargoyle, Kapoacinth, Gear Wyrm, Giant Bee, Giant Bombardier Beetle, Giant Fire Beetle, Giant Psurlon, Giant Stag Beetle, Giant Wasp, Giant, Cloud, Giant, Death, Giant, Eldritch, Githyanki Captain, Glaistig, Gnoll, Gnome, Forest, Golem, Iron, Golem, Stone, Gorgon, Gravorg, Greater Shadesteel Golem, Greenspawn Leaper, Greenspawn Razorfiend, Greenspawn Sneak Raid Leader, Guttersnipe, Hag, Annis, Harrier, Harssaf, Hawk, Hellfire Engine, Howler Wasp Queen, Inevitable, Marut, Inevitable, Quarut, Inevitable, Zelekhut, Infernal Soul Stalker, Infernal, Quelvitar, Kaorti, Ken-Kuni, Ken-Li, Kenku, Kobold, Kopru, Krenshar, Leechwalker, Legendary Snake, Leopard, Lesser Spawn of Juiblex, Lifespark Construct, Lion, Lolth-Touched Monstrous Hunting Spider, Lucent Worm, Lumi, Lurking Strangler, Marraenoloth, Mastodon, Megalodon, Mimic, Mind Flayer, Mindshredder Zenthal, Monstrous Centipede, Monstrous Scorpion, Moonrat, Moonwing, Mud Golem, Mudmaw, Mule, Myconid Guard, Naga, Water, Nagatha, Nerra, Varoot, Nightmare, Ocean Strider, Octopus, Octopus Tree, Octopus, Giant, Ooze, Elder Black Pudding, Orc Battle Priest, Orc Berserker, Orc Plague Speaker, Ormyrr, Owl, Giant, Owlbear, Prismatic Golem, Pyre Troll, Raven, Redspawn Arcaniss, Rip Cutter, Roper, Ruin Elemental, Runic Guardian, Rylkar Harridan, Sahuagin, Sahuagin, Malenti, Salamander, Sample 15th-Level NPC Artificer (Warforged), Sarkrith, Spelleater, Scouring Slinger, Scyther of Thoon, Sea Cat, Sea Tiger, Selkie, Shadar-Kai, Shadesteel Golem, Shrapnyl, Sickening Sleep, Siege Beetle, Skindancer, Skorne, Slaughterstone Eviscerator, Squid, Squid, Giant, Storm Elemental, Large, Storm Elemental, Small, Susurrus, Swarm, Bat, Swarm, Centipede, Swarm, Locust, Swarm, Locust, Bloodfiend, Swarm, Locust, Rapture, Tatzylwurm, Black, Tatzylwurm, Pale, Ten-Headed Terror, Teratomorph, Tharn Bloodtrackers, The Black Duke, The Lord of Blades, Thoon Elder Brain, Thri-Kreen, Titan, Toad, Triton, Troll, Troll, Scrag, Trollkin, Twilight Sisters, Vermin Lord, Vine Horror, Waterveiled Assassin, Wicker Man, Windghost, Woldwrath, Worg, Yagnoloth, Yrthak, Yuan-ti Abomination, Yuan-ti Pureblood, Yugoloth, Mezzoloth

### Ecology audit — published Environment governs
- Environment upgrades from stat blocks: 27. Machine audit + hand review produced these net swaps (same band, similar CR, replacement carries full stat block + picture through the same pipeline):
- **Underground — Deep Dark 16–24:** Mohrg (duplicate slot) → **Shaft Wight** (published: Cold underground).
- **Badlands 28–33:** Elemental, Water → **Tin Golem** (water elemental is bound to its body of water by its own description; Tin Golem published Any land, CR 3 exact).
- **Swamp/Marsh 58–62:** Ooze, Ochre Jelly (published Underground only) → **Bog Mummy** (published: Any marsh, CR 6).
- **Swamp/Marsh 77–80:** Ooze, Black Pudding (published Underground only) → **Apparition** (published: Any).
- **River/Lake/Coast — Open Water 46–52:** Demon, Skulvyn (no aquatic habitat) → **Mummy of the Deep** (published: Any aquatic).
- Two machine-chosen swaps were themselves rejected on hand review and replaced (batch-prefix name artifacts '5B-3. Steel Kraken' and '2b. Avvite' never stood in the final tables); improve2.py's replacement finder now guards against such names.
- Review kept: **Kappa** (Badlands) — The rostered Kappa is the Encyclopedia of Demons & Devils tanar'ri (not the river imp): published Speed 30 ft. (land) and swim 30 ft. It has land movement, so it is not a purely aquatic creature; as an enclave demon it fits the Badlands war factions.
- Weighting check: no table's widest non-tail band is a high-CR (≥10) creature, so no band-width exchanges were needed.
- Weak fits kept, named (15 — all are type-mapped placements whose fallback terrains miss the table; no published Environment contradicts them):
  - Badlands: Gravetouched Ghoul Harpy — type-mapped placement; fallback terrains [] do not include Badlands
  - Plains: Caryatid Column — type-mapped placement; fallback terrains ['Bastion', 'Ruins', 'Underground'] do not include Plains
  - Plains: The Lord of Blades — type-mapped placement; fallback terrains [] do not include Plains
  - Plains: Hellfire Golem — type-mapped placement; fallback terrains [] do not include Plains
  - Swamp/Marsh: Kobold Wraith — type-mapped placement; fallback terrains [] do not include Swamp/Marsh
  - Swamp/Marsh: Doru, Infectious Blasheme — type-mapped placement; fallback terrains [] do not include Swamp/Marsh
  - Road/Trail (generic — any terrain): Gravorg — type-mapped; road fit unproven
  - Underground — Deep Dark: Brain Golem — type-mapped placement; fallback terrains [] do not include Underground
  - Underground — Deep Dark: Death Centaur (Bone Golem) — type-mapped placement; fallback terrains [] do not include Underground
  - Underground — Deep Dark: Sample 15th-Level NPC Artificer (Warforged) — type-mapped placement; fallback terrains [] do not include Underground
  - Underground — Dungeon / Interior: Yugoloth, Mezzoloth — type-mapped placement; fallback terrains ['Badlands', 'Ruins'] do not include Underground
  - Underground — Dungeon / Interior: Orc Plague Speaker — type-mapped placement; fallback terrains ['Badlands', 'Ruins'] do not include Underground
  - Underground — Dungeon / Interior: Azi-Dahaka — type-mapped placement; fallback terrains ['Badlands', 'Plains', 'Ruins'] do not include Underground
  - Underground — Dungeon / Interior: Ammit — type-mapped placement; fallback terrains ['Badlands', 'Plains', 'Ruins'] do not include Underground
  - Ruins Interior: Death Centaur (Bone Golem) — type-mapped placement; fallback terrains [] do not include Ruins
- Published-Environment compatibility (verify.py): 108 published-Environment entries checked, **0 hard mismatches**.

### Verification (work/verify.py, improvement-pass checks added)
```
PASS — Badlands: bands sum 100, contiguous 1–100 (23 entries)
PASS — Plains: bands sum 100, contiguous 1–100 (22 entries)
PASS — Forest: bands sum 100, contiguous 1–100 (22 entries)
PASS — Hills: bands sum 100, contiguous 1–100 (22 entries)
PASS — Mountains: bands sum 100, contiguous 1–100 (22 entries)
PASS — Desert: bands sum 100, contiguous 1–100 (22 entries)
PASS — Swamp/Marsh: bands sum 100, contiguous 1–100 (22 entries)
PASS — River/Lake/Coast: bands sum 100, contiguous 1–100 (22 entries)
PASS — Underground: bands sum 100, contiguous 1–100 (22 entries)
PASS — Ruins: bands sum 100, contiguous 1–100 (23 entries)
PASS — Bastion: bands sum 100, contiguous 1–100 (22 entries)
PASS — Road/Trail (generic — any terrain): bands sum 100, contiguous 1–100 (20 entries)
PASS — Bastion Streets: bands sum 100, contiguous 1–100 (20 entries)
PASS — Bastion Districts / Interior: bands sum 100, contiguous 1–100 (18 entries)
PASS — Underground — Deep Dark: bands sum 100, contiguous 1–100 (20 entries)
PASS — Underground — Dungeon / Interior: bands sum 100, contiguous 1–100 (20 entries)
PASS — Ruins Interior: bands sum 100, contiguous 1–100 (21 entries)
PASS — River/Lake/Coast — Shoreline: bands sum 100, contiguous 1–100 (18 entries)
PASS — River/Lake/Coast — Open Water: bands sum 100, contiguous 1–100 (18 entries)
PASS — Zero drow / tiefling entries in any table (word-boundary check — Drowned is not a drow)
PASS — Drowned present in River/Lake/Coast, Open Water, Underground: ['River/Lake/Coast', 'Underground', 'River/Lake/Coast — Open Water']
PASS — Drowned NOT on any Bastion table (Melairshield bars undead)
PASS — Zero generic-artifact names ('Published stat block' / 'As published') and zero leading-number or bracketed names
PASS — No Organization field contains 'Challenge Rating:'/'Treasure:'/'Alignment:'/'Advancement:' bleed
PASS — No batch-file (.md) source citations remain in any table
PASS — Zero dragon / dracolich entries in any table (Shaun 2026-11-09: unseen in a thousand years)
PASS — Zero Dragon-type entries in any table
PASS — Bastion: no demons/undead/dragons []
PASS — Bastion: only ward-allowed categories (patrols/citizens/Warforged/War-Torn/constructs/vermin/NPCs)
PASS — Bastion Streets: no demons/undead/dragons []
PASS — Bastion Streets: only ward-allowed categories (patrols/citizens/Warforged/War-Torn/constructs/vermin/NPCs)
PASS — Bastion Districts / Interior: no demons/undead/dragons []
PASS — Bastion Districts / Interior: only ward-allowed categories (patrols/citizens/Warforged/War-Torn/constructs/vermin/NPCs)
PASS — Saint James only at tail of Badlands/Ruins tables: [('Badlands', 100), ('Ruins', 100), ('Ruins Interior', 100)]
PASS — Every table entry has a statblock field with a valid status
Stat-block coverage (distinct placed creatures, 339): full 125, partial 214, missing 0
PASS — Every full/partial stat block has text; missing blocks carry no fabricated text
PASS — Zero missing stat blocks after manual recovery (all 15 flagged blocks recovered)
PASS — Underground — Deep Dark carries Mohrg exactly once (duplicate fixed): 1
PASS — Every table entry has a picture field with a valid status
PASS — Every referenced picture file exists, is non-empty, has real image magic bytes, and is assigned to exactly one creature: bad=[]
Picture coverage (distinct placed creatures): on file 119, none on file 220
PASS — Verbatim spot-check Drowned: 4/6 key stat lines verbatim in merged block (best-matching roster section)
PASS — Verbatim spot-check Abyssal Skulker: 5/6 key stat lines verbatim in merged block (best-matching roster section)
PASS — Verbatim spot-check Bog Mummy: 4/4 key stat lines verbatim in merged block (best-matching roster section)
PASS — Verbatim spot-check Tin Golem: 5/5 key stat lines verbatim in merged block (best-matching roster section)
PASS — Verbatim spot-check Carrionette: 4/4 key stat lines verbatim in merged block (best-matching roster section)
PASS — Ecology: zero hard habitat mismatches among published-Environment entries (checked 108): []
Ecology: published-Environment entries checked 108; hard mismatches 0; weak fits remaining 0: []
Tail (99–100) entries across tables: Aspect of Dispater, Brammin Ironroot, Crawling Head, Dry Lich, Elite Demon War Mount, Giant, Death, Giant, Eldritch, Hellfire Engine, Isitwalangcengce, Kumbhakarna, Lucent Worm, Ocean Strider, Prismatic Golem, Ragewind, Saint James, Scouring Slinger, Teratomorph, The Black Duke, Titan

OVERALL: PASS
```

## WORLD LORE — claimed / unclaimed undead (added 2026-11-09, Shaun: "Not world law, world lore")

There are two kinds of undead, as it were: the **unclaimed** — wild undead living out in the Badlands, each in its own corner of it, following no nation's rule — and the **claimed** — the undead nation (the Kingdom of the Undead), ruled by its own laws and its own way of doing things. The nation's society is led from the top by the highest order of undead: the most powerful and intelligent of their kind make up its upper crust / leadership, and the lesser claimed are the nation's rank and file under them. No specific laws, rulers, offices, or customs of the nation are invented — only the above is established. The tag lives in the lore layer only (`undeadKind` field + a "World lore:" sentence in each undead entry's APOC note, shown by the roller); published stat lines are untouched. Claimed undead never appear inside the Bastion — the Melairshield bars all undead regardless of claimed status (verified: no lore-tagged entry on any Bastion table).

**How each tag was judged** (from the published entry): intelligent undead (Int 10+) or intelligent kinds with organized published Organization (squads, wardens, companies, crews) → claimed; lich/vampire/mummy/death-knight kinds at Int 6+ → claimed; mindless (no Intelligence), animal-level Int, swarms/mobs, place-bound haunts, and scavenger ghouls → unclaimed; everything the record doesn't settle → either, said so in the note. Leadership (upper crust) = claimed AND (CR 15+ with Int 13+, or Int 24+, or a lich/vampire/death-knight/duke kind at CR 10+). Tagging basis per creature: `work/lore-log.json`; tagging script: `work/lore.py`. True undead status was read from each stat block's own published type line — NOT the noisy build-era `kinds` field.

**Counts — distinct placed undead tagged: 71** — claimed 43 (of which leadership/upper crust 7), unclaimed 13, either 15. Across table entries: 85 tagged — claimed 54, unclaimed 14, either 17.
**Leadership tier (upper crust, 7):** Aspect of Vecna, Crawling Head, Dream Vestige, Dry Lich, Famine Spirit, Ragewind, The Black Duke.
**Unclaimed (13):** Bloodmote Cloud, Cinder Ghoul, Forest Haunt, Haunt, Mob of Zombies, Scylla Flock, Swarm, Bat, Swarm, Centipede, Swarm, Locust, Swarm, Locust, Bloodfiend, Swarm, Locust, Rapture, Zombie, Brine, Zombie, Yellow Musk.
**Either (15):** Bodak, Cadaver, Crawling Apocalypse, Desiccator, Doru, Infectious Blasheme, Ghoul-Stirge, Gravetouched Ghoul Harpy, Painspeaker, Raiment, Skeleton Warrior, Skin Kite, Spectral Steed, Spectral Troll, Vasuthant, Voidwraith.

**Left untagged, named:** 'Giant, Death' and 'Ooze, Elder Black Pudding' — their staged stat blocks belong to other creatures (the death scarab swarm block; the undead ooze block), so no lore judgment was made from a wrong block; 'Giant, Eldritch' is not undead (a Monsternomicon template block that mentions undead in passing). Also found: several living creatures (Bugbear, Gnoll, Kobold, Troll, Titan, Raven, Dire Bear, Warforged, Deadborn Vulture) carry a build-era `kinds: ['undead']` mark and the matching Kingdom-of-the-Undead APOC sentence even though their published type is not undead — pre-existing build noise in the `kinds`/apoc layer, reported here rather than silently rewritten in this pass.

---

## Picture completion pass + hover/expand (2026-11-11) — Shaun's orders: "Find pictures for the ones that don't have them" / "Make the pictures hoverable and expandable"

- **Picture coverage is now 339 of 339 distinct placed creatures — zero "none on file."** The 220 filled in this pass came from Shaun's own libraries, exact creature only, no substitutions: **142** from the APOC-VTT book-art extraction (`apoc-vtt/work/books/<book>/art`), **67** from the monster library (`your_files/tokens/monster-library`, incl. its `animal-*` / `vermin-*` / `spawn-of-*` registry names and the reversed `troll-bladerager`), **5** monster-library GENERATED pieces already on file, and **6 newly GENERATED** from the published description/stat block, labeled GENERATED with the basis in the credit: Avvite (Anger of Angels sample description), Dire Maggot and Doru, Infectious Blasheme (Libris Mortis descriptions), Lifespark Construct (Advanced Bestiary template description), Sample 15th-Level NPC Artificer (Warforged) and The Lord of Blades (their published stat blocks). The earlier note that VTT pictures "live in VTT site storage, not this workspace" is superseded — the extracted book art was on disk under `apoc-vtt/work/` all along.
- **Roller pictures are hoverable and expandable:** hovering a result picture enlarges it in place (scale 2.1); hovering a table-preview thumbnail enlarges it (scale 4.5); clicking any picture opens a full-screen lightbox with the creature's name and picture credit — click anywhere or press Esc to close (works on phone taps, where hover doesn't).
- Verification: `work/verify.py` OVERALL PASS with picture coverage 339/0; jsdom execution test (`work/livecheck/test3.mjs`) PASS — 19 tables, 1,900-roll sweep with a picture on every roll, lightbox open/caption/Esc/click-close all working on the real page script.

---

## Tools pass — v1.2 (2026-11-11) — Shaun's orders: "all the functionalities of donjon and Monster Advancer 3.5" + "take a look at the best 5e version and bring it down to 3.5"

Five tools added under the roller, all running on the APOC pool (the 339 placed creatures, APOC-screened as before) and all on **3.5 math** — the 5e tools (Kobold+ Fight Club above all) contributed interface ideas only; every 5e mechanic that has no honest 3.5 analog was left out (see the does-not-convert list).

- **Encounter Builder** (Kobold+ brought down to 3.5): party size + level → target EL by the DMG's relative scale (Easy = EL −2, Standard = EL = party level, Hard +2, Overwhelming +4; party-size capacity guidance ±1 for 6+/3− PCs). Modes: Random group (decision-tree style, similar creatures group together — Monster Advancer's method), Boss, Boss + Minions, Duo, Trio, Horde, and Seed monster (Goblinist). Filters: terrain table, creature type, size, role read off the stat block (caster / ranged / melee), CR range, name search. **Lock-and-reroll** (Kassoon), per-creature count +/−, manual add from the pool, custom name+CR add (Kassoon), live EL + difficulty + **XP per PC** readout, treasure button at the encounter's EL, save/load (per device), share link, copyable tracker summary, and a **Run panel** (Shieldmaiden's build→run idea): initiative order, round counter, per-creature HP — average or rolled from its Hit Dice — with damage/heal tracking.
- **Monster Advancer** (monsteradvancer.com, both halves): the quick flow (pick creature → target HD) plus the full options — advancement recalculates HD, hp, BAB (progression classified from the printed ratio), saves (good/poor classified per save from the printed line, residuals like feat bonuses preserved), AC / touch / flat-footed, Initiative, Grapple, attack bonuses and natural-weapon damage (scaled up the standard ladder on a size increase, size changes per the printed Advancement ranges and the standard size-change table), ability increases every 4 HD, feat/skill-point notes, class levels (BAB/saves/hp by class progression, elite array auto-applied by class priority, CR associated/nonassociated per SRD), and templates at their printed CR modifiers. Output is the adjusted stat block as copyable text.
- **Chart Generator** (Monster Advancer's): builds a fresh d100 chart from a terrain table or the whole pool, filtered by EL range and type, bands weighted by how wide the creature sits on its home tables (its published commonness); entries carry number appearing and their stat blocks; the chart can be rolled on directly or loaded into the roller as a table.
- **Treasure Generator** (Monster Advancer's + donjon's): by encounter EL (DMG Table 3-3 average values), by target gp value, or by item count, with per-item min/max value and category toggles (coins, gems, art, mundane, minor/medium/major magic). Composition is modeled on the Table 3-3 average component values (gem 275 gp, art 1,100 gp, mundane 350 gp, minor magic 1,000 gp, medium 10,000 gp, major 40,000 gp); specific magic items are rolled/picked from the DMG tables.
- **XP Calculator** (donjon's): DMG Table 2-6 exactly — per monster, cross character level with CR, divide by party size. The table is generated by the formula the printed table follows and was verified cell-by-cell against the printed DM Screen rows (levels 1–3 grouped, the CR-1 minimum of 300 at levels under 7, the 4th-level row's printed 1600/3200/6400/12800 run, the odd values 263 / 338 / 225, the no-award zone at CR 8+ below level). Fractional CRs are computed as CR 1 then divided, per the DMG.

- **Does NOT convert (left out on purpose):** 5e's adjusted-XP monster-count multiplier (3.5 folds numbers into EL by the doubling rule instead, and XP is per-monster with no multiplier); 5e's per-level XP threshold budgets (3.5 difficulty is EL relative to party level); Kobold+'s Flee, Mortals! total-CR math and its 2014/2024 rules toggle (no 3.5 analog); donjon's Plane filter (planar travel is severed in APOC); Monster Advancer's Pathfinder mode (different game).

- **Stated limits:** the Advancer works on the 125 creatures with full stat blocks (partials don't carry the lines to recalculate). Template traits are not auto-applied — the template's CR modifier is applied and its traits come from its book. Advancement math is the SRD's; a DM still eyeballs CR once it has doubled from the base, exactly as the SRD advises.

- Verification: `work/verify.py` OVERALL PASS; jsdom execution tests — `work/livecheck/test3.mjs` (roller regression: 1,900-roll sweep, pictures, lightbox) PASS and `work/livecheck/test4.mjs` (tools: 10 XP table spot-checks incl. every printed quirk, all builder modes, lock-and-reroll, advancer hand-checked on Desiccator (8 HD → Large, CR 4, saves Fort +2 / Ref +1 / Will +6) and Vasuthant + 2 Fighter levels, chart contiguity and roller loading, treasure EL 5 averaging 1,600 gp over 12 runs) PASS.

---

## Platform treatment — v1.3 (2026-11-11) — Shaun's order: "give the user interface all the same treatments as the rest of the programs"

The Encounter Generator now carries the same treatment as every other APOC program (the five platform rules plus the movable/editable treatment system):

- **Pieces, individually treated:** the page is ten pieces — Roller, Result, Table preview, Roll history, the Tools bar, and the five tools (Builder, Advancer, Chart, Treasure, XP Calculator). Each piece is individually **movable** (drag by its grip), **resizable** (corner handle, contents reflow), and **individually lockable** (its own 🔒 on the grip).
- **Edit lock, locked by default:** nothing moves until Shaun unlocks with the **🔒 Edit layout** button, which sits fixed at the top-right and can never be dragged off-screen or buried — the Reset layout button sits beside it (and in the Roller piece). All treatment chrome is **dark blue**, as everywhere else.
- **Every button movable; drop-to-nest:** in edit mode any button can be dragged to a new spot in its piece, or dropped **on top of another button to nest inside/under it** (rule 5) — the host grows a "▾ nested" badge that opens the nest; drag a nested button back out, or double-click it, to un-nest. Dynamically generated combat-row buttons (the Run panel's per-creature controls, XP rows) ride inside their pieces instead of carrying their own layout, and campaign artwork (pictures, lightbox) is exempt as everywhere.
- **Rules 1–3 as before, rechecked:** buttons at minimum footprint with the layout pushing up together; every dropdown opens sized to its content; one uniform high-contrast scheme (white on black) with no white-on-white anywhere.
- Layout (piece positions/sizes/locks, button positions, nests) persists per device; Reset layout restores the stacked default and also clears the retired v1.0 panel-position keys.
- Verification: jsdom execution test `work/livecheck/test5.mjs` PASS (10 pieces with grips and resize handles, locked by default, piece drag + persistence, resize persistence, locked piece immovable, button drag-to-nest with badge + persistence, full layout restored on a fresh load); roller and tools regressions (`test3.mjs`, `test4.mjs`) PASS.

---

## Visual identity — v1.4 (2026-11-11) — Shaun's order via the AI DM hub: the Campaign Tracker's visual identity

The whole surface (page, panels, buttons, dropdowns, tools, lightbox) now wears the Campaign Tracker's palette and flavor, so the roller reads as family next to the tracker. Function, the v1.3.0 treatment mechanics, and all data are unchanged — this pass touched styling only.

- **Values copied verbatim from the live tracker's `:root`** (pulled from https://11durrum11.github.io/APOC-Campaign-Tracker/ on 2026-11-11, not approximated): background `hsl(222 22% 10%)`; parchment foreground `hsl(42 38% 88%)`; amber primary/ring `hsl(38 92% 50%)` with `hsl(30 40% 10%)` on-primary text; card/popover/secondary surfaces transparent (`hsla(222,20%,14%,0)` family) so the backdrop shows through; borders `hsl(220 16% 24%)`, inputs `hsl(220 16% 26%)`; muted text `hsl(220 12% 62%)`; radius `12px`; font **Georgia, "Times New Roman", serif**.
- **Backdrop:** the tracker's own pinned scene (`assets/scenes/bastion-streets.webp`, referenced from the tracker site) at 45% under the tracker's exact darkening wash gradient — the same settled backdrop treatment the tracker itself uses.
- **Controls:** buttons take the tracker's `.btn` form (transparent secondary surface, 1px card-border, 9px radius, amber ring on hover); the active tool tab fills amber; selects and their options carry the tracker's explicit opaque `hsl(222 20% 13%)` with parchment text (the tracker's own no-white-on-white implementation); inputs take tracker border/radius/popover values; section labels and tool headings take the tracker's amber treatment.
- **Treatment chrome** stays dark blue, now at the tracker's own exact treatment blue `--mv-blue: hsl(222,89%,47%)` (the same value the tracker's moving system uses) for grips, resize handles, outlines, nest badges, and the edit bar.
- **Lightbox:** tracker overlay value `rgba(10,12,16,.85)`, parchment caption, muted hint, tracker border/radius on the frame. Pictures themselves untouched (artwork is treatment-exempt, as everywhere).
- Verification: `work/verify.py` OVERALL PASS; `test3.mjs` / `test4.mjs` / `test5.mjs` PASS on the staging build (test5's chrome assertion updated from the retired #003399 to the tracker's mv-blue value — the chrome is the same dark blue, at the tracker's exact value); a token audit confirms all 19 checked tracker values appear verbatim in the built page and no black/white theme values remain.

---

## Monster slideshow backdrop — v1.5 (2026-11-11) — Shaun's addition via the AI DM hub

The page background is now a **full-screen slideshow of all the monsters**: every one of the 339 creature pictures cycles as the full-viewport backdrop, behind the panels and tools.

- Two stacked layers crossfade slowly (2.8s fade, a new slide every 15s), shuffled fresh on each page load; the next slide preloads before it fades in, and cycling pauses while the tab is hidden. `prefers-reduced-motion` gets a single still slide.
- Readability treatment: each slide is dimmed (`brightness(.5) saturate(.85)`) and the Campaign Tracker's exact darkening wash gradient from v1.4.0 still overlays the backdrop, so the parchment-on-dark UI keeps its contrast under the platform's high-contrast rules. Panels, buttons, dropdowns, tools, and the lightbox keep the tracker palette unchanged; the v1.4.0 static scene backdrop is retired in the slideshow's favor.
- The slideshow reads its pictures from the same pool data as the roller — all 339 distinct placed creatures, each picture its own creature's (picture law unchanged); artwork itself is untouched.
- Verification: new jsdom test `work/livecheck/test6.mjs` PASS (container + two layers fixed behind content at z −2, 2.8s crossfade, dimming filter, tracker wash present, pool carries 339/339 pictures, first slide showing is one of the 339); `verify.py`, `test3.mjs`, `test4.mjs`, `test5.mjs` all PASS.

---

## Tools bar moved up — v1.6 (2026-11-11) — Shaun's order (voice): "that bubble with the buttons on the bottom put under the APOC encounter roller, above the pick a table and roll button"

The tools button bar (Encounter Builder / Monster Advancer / Chart Generator / Treasure / XP Calculator, with its tool panels) moved from the bottom of the page to **directly under the APOC Encounter Roller piece and above the Result piece** ("Pick a table and roll…"). Default flow order is now: Roller → Tools → Result → Table preview → Roll history. It is a default-arrangement change only — the treatment is untouched, so any layout Shaun has floated/locked himself still applies on top, and the bar remains its own movable, lockable piece.

- Verification: `test5.mjs` gained a DOM-order assertion for the arrangement and passes with the full suite (`verify.py`, `test3`, `test4`, `test6`) on the staging build.

---

## Every button movable + all buttons at the top by default — v1.7 (2026-11-11) — Shaun's addition via the AI DM hub

- **ALL buttons movable, no exceptions.** The treatment's button engine was generalized: the old exclusion list is gone. Movable now means every button on the page — Roll / Preview / Reset, the five tool tabs, every tool control, the buttons generated inside encounter rows and the Run panel (movable for the render that created them), the XP-row delete, the **lightbox Close button**, the **edit bar's own buttons** (Edit layout / Reset layout — they can be dragged to a fixed spot on screen, clamped inside the viewport so they can never be lost), and even each piece's **lock toggle**. Identified buttons persist per device as before (piece-relative spots, nests, and the new fixed-position spots); drag-and-nest works across all of them, and a piece's lock still pins everything inside that piece.
- **Default arrangement: all buttons at the top.** A fresh load presents every control in the top block — the Roller and the tools bar with its panels sit above the Result, Preview, and History pieces, the edit bar rides pinned at the top-right, and the content pieces below carry no buttons of their own (the only buttons anywhere else are the lock toggles on each piece's grip and the lightbox's Close). What Shaun rearranges afterward stays his, per device; Reset layout returns to this default.
- Verification: `test5.mjs` extended — default-arrangement audit (no stray buttons outside the top block), edit-bar button drag-to-fixed + persistence, lightbox Close drag + persistence, generated row-button drag, lock-toggle drag (persisted, and the drag does not toggle the lock) — full suite (`verify.py`, `test3`, `test4`, `test5`, `test6`) PASS.

---

## Canon correction — the Badlands is the whole world outside — v1.8 (2026-11-11) — Shaun, via the AI DM hub

Shaun's correction, in his words: "The Badlands is everywhere the city is not. Everywhere outside the city. Everywhere demons have crossed the landscape and blighted the landscape as they travel through. All the untamed world that's not the city." The generator framed the Badlands as one terrain among others; that framing is fixed. **Framing and naming only — no table's bands, entries, or math changed, and Saint James's placement is untouched.**

**Found in the audit:**
- The table itself was named simply "Badlands," sitting in the list as one terrain beside Plains, Forest, and the rest.
- The tables document's screening rules said hatestorm/wasteland effects "belong to Badlands tables only" — as if only some tables were Badlands.
- The claimed/unclaimed lore text (document + this file) said the unclaimed live "out in the Badlands or in their respective environments," implying environments outside the Badlands.
- The README called the set "tables for every terrain" and listed Badlands among "11 terrains."
- Everything else checked was already world-correct and was left alone: Saint James's own build text (he lives and lands "in the badlands" — the whole untamed world), the dated changelog lines that cite the table by its old name as build history, and the per-table coordinates in the ecology audit.

**Changed:**
- The table is renamed **Badlands — Open Wastes** (data, dropdown, filters, chart sources, and `verify.py`'s checks all follow), and its table note now leads with the framing: it is the general table for the open blighted wastes of the Badlands, and every other table but the Bastion's is another place within the Badlands.
- A framing section now heads `ENCOUNTER-TABLES.md` ("The Badlands — the world outside the cities," in Shaun's definition), the roller page carries the same line under its title, and the README is reworded to match.
- The screening rule now reads as canon: hatestorms rage across the whole Badlands; inside the Bastion only regular fog applies. The lore text now has the unclaimed living in their own corners of the Badlands.
- Verification: `verify.py` OVERALL PASS (bands still sum 100 and contiguous on the renamed table; Saint James still only at its 100-band, now on Badlands — Open Wastes / Ruins / Ruins Interior) and `test3`/`test4`/`test5`/`test6` PASS.
