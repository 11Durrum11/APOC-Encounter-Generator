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
- Per-table entries: Open Wastes=23, Plains=22, Forest=22, Hills=22, Mountains=22, Desert=22, Swamp/Marsh=22, River/Lake/Coast=22, Underground=22, Ruins=23, Bastion=22, Road/Trail (generic — any terrain)=20, Bastion Streets=20, Bastion Districts / Interior=18, Underground — Deep Dark=20, Underground — Dungeon / Interior=20, Ruins Interior=21, River/Lake/Coast — Shoreline=18, River/Lake/Coast — Open Water=18

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
- The table is renamed **Open Wastes** (data, dropdown, filters, chart sources, and `verify.py`'s checks all follow), and its table note now leads with the framing: it is the general table for the open blighted wastes of the Badlands, and every other table but the Bastion's is another place within the Badlands.
- A framing section now heads `ENCOUNTER-TABLES.md` ("The Badlands — the world outside the cities," in Shaun's definition), the roller page carries the same line under its title, and the README is reworded to match.
- The screening rule now reads as canon: hatestorms rage across the whole Badlands; inside the Bastion only regular fog applies. The lore text now has the unclaimed living in their own corners of the Badlands.
- Verification: `verify.py` OVERALL PASS (bands still sum 100 and contiguous on the renamed table; Saint James still only at its 100-band, now on Open Wastes / Ruins / Ruins Interior) and `test3`/`test4`/`test5`/`test6` PASS.

**Sharpening (same day, Shaun's exact words via the hub): "in the generator, you have it as the Badlands as one particular landscape, and that's just not true."** The landscapes are all IN the Badlands; the Badlands itself is not one of them. So the entry's name drops "Badlands" entirely: the landscape is **Open Wastes** — first in the list as the Badlands' general table for its open blighted country, with the table note stating outright that the Badlands is not one landscape among the others and that every table but the Bastion's is a place within it. No table in the set is named for the Badlands anymore; the Badlands stands over the whole list as the world it all lies in. Contents and math unchanged again (23 entries, bands 1–100; Saint James still only at the 100-band).

---

## The Badlands layer — an on/off additive over the landscapes — v1.9 (2026-11-11) — Shaun, via the AI DM hub

Shaun's refinement: "Maybe Badlands can be an additive. On and off additive to all the landscapes." Built exactly so. The roller now carries a **Badlands layer** toggle (in the Roller piece, movable like every button; state persists per device). It is not a table and not a landscape — it is the Badlands itself, layered over whichever landscape is rolled. The Open Wastes table stays a landscape (the Badlands' general table); the additive is the layer above all of them.

**What the layer does when ON (all effects taken from Shaun's canon on file — his World-and-City-Canon: "The Badlands," "The twisting," "Constant war"; the screening rules; the claimed/unclaimed lore):**
- It applies to the 16 landscape tables and never to the 3 Bastion tables — the city is the exception (when a Bastion table is selected, the toggle's note says the layer does not reach inside the walls, and no layer block or history mark is produced).
- Every landscape result is produced as a Badlands encounter and carries the layer block with the canon conditions for that country: **surface landscapes** (Open Wastes, Plains, Forest, Hills, Mountains, Desert, Swamp/Marsh, River/Lake/Coast, Road/Trail, Ruins, Ruins Interior, Shoreline, Open Water) — one grey sky, Fog of Life on the surface, hatestorms rage in this country, the permanent war runs through it, the unclaimed walk here; **underground landscapes** (Underground, Deep Dark, Dungeon/Interior) — no Fog of Life underground, but the blight soaked deep, the war runs through the dark, the unclaimed walk here.
- The layer block also carries the twisting: the land's own life in defiled country may be twisted — warped in body, wrong in habit; no demon, and no servant of demons — with Shaun's Twisted template named as applying where the DM calls it.
- Roll history marks layered rolls "[Badlands layer]". Table contents and math are untouched either way.

**Flagged, not guessed (needs Shaun, per the order's own instruction):**
1. **Twisted application.** Canon says the land's creatures "sometimes" come out twisted — no frequency is given anywhere on file, and the mechanical Twisted template is Shaun's Doc #4 version, which is not among the generator's sources (his canon document carries the story, not stat changes). The layer therefore presents the twisting and names the template; it does not roll a probability or apply stat changes. Give me the template (or a chance) and the layer will apply it for real.
2. **Pool blending.** The layer does not blend the Open Wastes general pool into landscape rolls — no canon rate for that exists. If Shaun wants badlands-grade pressure mixed into landscape rolls, the rate is his to set.
- Verification: `test3.mjs` extended (toggle exists and defaults OFF, persists per device, layer block on a surface landscape roll, underground variant line, no layer on the Bastion, exception note, history marking) — full suite PASS.

---

## One design: the Badlands layer on a d1000 scale — v1.10 (2026-11-11) — Shaun, via the AI DM hub

Shaun's order, in the flow of the additive work: "In light of the fact that we're talking about all the different landscapes — maybe you should make it one to a thousand." The tables now run **1–1000**, brought in together with the Badlands layer as one design: the layer keys on landscapes, not numbers, so it rides over the new scale unchanged (still the 16 landscape tables, still never the Bastion's three, still marking history).

**The conversion is exact scaling — proportions honest, nothing padded or invented.** Every band in every table was multiplied by ten (low' = (low−1)×10+1, high' = high×10; 399 entries, machine-checked: all 19 tables contiguous 1–1000 and summing exactly 1000). Every creature keeps precisely the share of its table it had at d100 — no creature added, removed, or re-weighted. Saint James is still the last 1% of Open Wastes / Ruins / Ruins Interior, now the 991–1000 band. The roller throws d1000, results and previews read on the new scale, and the Chart Generator now builds and rolls d1000 charts (weights still proportional to the source tables).

- **Scope call, stated plainly:** all 19 tables were scaled, the Bastion's three included, so the roller throws one die throughout — Shaun's words named the landscape rolls; if he wants the city kept at d100 as part of its exception, the three Bastion tables revert in one move.
- **Twisted flag, updated by canon during this build:** Shaun settled that the twisting happens RANDOMLY — chance, not a fixed rate or schedule (now recorded in the Twisted canon entry). The mechanism is settled; the rate is still stated nowhere on file, and Shaun's Doc #4 template is still not among the generator's sources. The layer therefore still presents the twisting without rolling it. One number from Shaun (or Doc #4) and the layer rolls the chance per eligible creature, as canon now directs.
- Verification: `verify.py` OVERALL PASS on the new scale (Saint James tail check moved to ≥991); `test3` (roll 1000 still lands Saint James; Badlands layer assertions), `test4` (d1000 chart generate/roll/load), `test5`, `test6` PASS.

---

## The Steampunk overlay — the second additive — v1.11 (2026-11-11) — Shaun, via the AI DM hub

Shaun's addition to the d1000/Badlands design: "Make steampunk also an overlay." Built as a second toggle in the Roller beside the Badlands layer — **independent, combinable in any state** (four combinations, all working; history marks stack: [Badlands layer] [Steampunk]). State persists per device (`apocEncSteampunk`), default OFF, movable like every button.

**What it does, from the campaign's established steampunk canon (Shaun's World-and-City-Canon + standing canon), nothing invented:**
- It layers over **all 19 tables** — steampunk is the age's own technology and belongs in the city as much as out of it; unlike the Badlands layer it has no city exception (Shaun's wording: "over whatever landscape and roll comes up").
- On any roll with the overlay ON, the result carries the Steampunk block. **Landscape variant:** war-machines crawl out of the enclaves (canon: the demon enclaves raise steampunk war-machines), constructs work the fields and ruins, steamcraft gear turns up in ready hands, elemental workings are fed through steampunk apparatus (canon: elemental magic limps unless fed through alchemical components or steampunk apparatus). **Bastion variant:** the city runs on steam — cannoneer towers along the wall, the walking constructs on their rounds, steamcraft in the workshops.
- **Made manifest:** when the roll itself produces a construct-type creature (35 such entries are on the tables, placed by their published environments — Clockwork Horrors, Gear Wyrms, golems, the Warforged among them), the block names it the element itself: a machine of the age, met in the field. That is the entry's own published type, stated — not a weighting change.
- No table contents and no math change in any state.

**Flagged, not guessed:** (1) **Population weighting** — making machines/constructs more likely while the overlay is on would need a canon rate; none exists, so none was applied. (2) **Steamcraft gear generation** — the overlay does not produce steamcraft items; the generator has no canon gear tables or rates for it (the Warforged/War-Torn/Steamcraft shared equipment pool is Blendcrafter-side canon, not a drop table). Either is buildable the moment Shaun sets the terms.
- Verification: `test3.mjs` extended (toggle/default/persistence, landscape block + war-machine line, construct manifestation on a known Warforged band, Bastion city variant, both overlays stacked with dual history marks) — full suite PASS.

---

## The Steampunk rewrite — the overlay rewrites the creature — v1.12 (2026-11-11) — Shaun's spec, via the AI DM hub

Shaun's spec: "And if utilized, it rewrites the creature into a steampunk version." Built to the letter and to the roster guardrail: **the creature's published record underneath stays verbatim and untouched; the rewrite is the overlay's layer on top, shown as the version in play; the base creature stays identifiable; toggle OFF = the creature exactly as published.**

**How the rewrite works (roller results):** with the overlay ON, a rewrite panel leads the result — **Steamwork [creature]**, "the steampunk version in play," with the base creature named and its CR, and its published record (picture, APOC note, stat block) standing below untouched. The rewrite's description and build are reworked in the campaign's steampunk idiom **from the creature's own published lines** — its size and frame, how it moves (brass-pinioned flight, screw-driven swimming, auger-limbed burrowing, from its printed Speed), its natural weapons rebuilt in steel (from its printed attack lines) — closing on the canon truth that what it was shows through the work. The build line states the rule in play: steamwork construction over the published form; run the block exactly as printed — **the overlay reworks the form, not the numbers** (no stat, CR, or number-appearing change is made or implied anywhere).

**Collision classes — flagged, handled conservatively, per Shaun's instruction to flag rather than guess:**
- **Constructs, the Warforged among them (42 construct-typed entries):** already machines of the age — a "steampunk version" of a machine is no rewrite at all. The overlay states that and changes nothing. (The Warforged edge of this is canon-loaded: they were CREATED whole, and the overlay does not blur that line.)
- **Persons — the NPC cast and Saint James:** NOT rewritten into machines. Rebuilding a person into a machine is precisely the making of a War-Torn, and the overlay does not take that step on anyone. Persons are presented **kitted in the idiom** — steamcraft gear, apparatus, firearms — and themselves unchanged. If Shaun wants persons handled otherwise, that's his call to make, not the overlay's.
- **Undead:** the rewrite proceeds in idiom form (form only, numbers untouched). Noted for the record: Shaun's homebrew carries a Steampunk-Augmented Undead template — if he wants the overlay to apply that template's actual mechanics to undead rolls, the template text is the one source needed; it is not among the generator's files.
- Scope: the rewrite acts on the roller's rolls (where the overlay toggles live). The Encounter Builder and Chart Generator present creatures as published; extending the rewrite into them is a separate call.
- Verification: `test3.mjs` extended (Steamwork Toad with the verbatim record below it; Warforged "already a machine," never Steamwork Warforged; Bram Holt and Saint James kitted, never rewritten; overlay OFF restores exactly-as-published) — full suite PASS.

---

## The rulings release — bleed, weighting, gear drops, the Twisted overlay — v1.13 (2026-11-11)

Shaun ruled on every standing flag (AI DM voice call, recorded in canon), and this release builds the rulings in. **Closed by ruling:** the d1000 scope — Shaun confirmed all tables including the Bastion's ("I think D1000 are right"); no change needed. **City boundary holds:** the Bastion tables stay city populations only — nothing from outside rolls inside the walls on any overlay; the bleed and the weighting below draw only from each table's own population.

- **Badlands bleed (Shaun's settled rate, 1 in 20):** with the layer ON, a landscape roll (never the Open Wastes itself, which IS the pool; never the Bastion) has a 1-in-20 chance to come out of the Open Wastes general pool instead, shown with a "The Open Wastes bleed in" note and marked in history. Saint James is never displaced by the bleed.
- **Steampunk weighting (Shaun's ruling, machines 7 out of 10):** with the overlay ON, a non-machine result bends to the current table's own machine population at the rate that makes machines seven in ten in expectation (bend chance = (0.7 − p)/(1 − p), where p is the table's machine share by band width), the machine drawn in proportion to its band. Machines are construct-typed entries; 7 of 19 tables hold any (Bastion 53%, Bastion Streets 51%, Bastion Districts 38%, Deep Dark 12%, Underground 9%, Swamp/Marsh 6%, Ruins Interior 6%) — on the other 12 the published population has no machines to bend to, and the weighting simply cannot fire. Saint James is never displaced by the weighting either.
- **Steamcraft gear drops (Shaun's ruling: YES):** every roll under the Steampunk overlay carries one steamcraft gear drop, named plainly from the age's canon vocabulary (steampunk apparatus, steamcraft tools, alchemical components, a firearm, gearwork prosthetic components, brass fittings and boiler plate, a clockwork mechanism, pressure valves and copper piping) — names only; no prices or stats invented. If Shaun wants a drop rate other than every roll, or a specific gear list, both swap in one move.
- **The Twisted overlay (third toggle):** the twisting moves out of the Badlands layer's text into its own independent overlay, as canon now has it. With it ON, the land's own living life on a roll is presented **Twisted [creature]** — warped in body, wrong in habit, no demon and no servant of demons — over its published block. Not eligible: the undead, constructs, demons, and persons (named people are Shaun's story calls, not the overlay's). Still open, unchanged: Shaun's Doc #4 template carries the mechanics and is not among the generator's sources, so the overlay presents the form in canon's words and changes no numbers.
- Verification: `test3.mjs` extended (Twisted toggle/persistence, Twisted Toad, undead excluded, bleed fired on a queued random sequence landing the Open Wastes pool's first entry, weighting bending a Raven roll to the Swamp's Warforged with the gear drop on the same roll, Saint James undisplaced under full overlay state) — full suite PASS.

---

## The templates are on file — real template application — v1.14 (2026-11-11)

The consolidated spec from the hub carried the pointer this project had been missing: Shaun's Twisted template "is his Doc #4 material — the Blendcrafter library carries it." It does. Both house templates stand in the Blendcrafter library's homebrew records (`src/data/homebrew/templates.ts`), and this release applies them for real. **Correction to the earlier flags:** v1.12/v1.13 said the templates were "not among the generator's sources" — true of the generator's own folder, but the texts were on file in the library the whole time. The flags close with sources in hand, not with new rulings.

- **Twisted overlay — Doc #4 applied.** The panel now applies Shaun's "Twisted (House)" template (Misc Other House Rules, doc #4) in full: Str +4, Con +4, Cha −2, Intelligence at least 3; natural armor improves by +2; alignment becomes evil; Smite Good (Su) 1/day (+HD, max +20, vs good); Disruptive Attack (Su) +1 vile damage on touch vs uncorrupted living corporeal nonoutsiders; two claw attacks as primary natural weapons (damage by the template's printed sizes — 1d2 Small, 1d3 Medium, 1d4 Large; other sizes stated generically, the ladder not extended by invention); darkvision 60 ft; DR 5/cold iron; natural weapons count as magic vs DR; immunity to electricity and poison; resistance 10 acid/cold/fire; animals and vermin become magical beasts, other types unchanged. **No CR adjustment — the document gives none, so CR stands as published.** The application is the overlay's layer over the verbatim published block (the separation the spec itself prescribes). Eligibility unchanged from v1.13 (the land's living life; undead, constructs, demons, persons out) — noted against the template: the document itself places no restriction on the base creature, and the overlay's narrower scope is the campaign-canon read (twisting is what demon-passage does to the land's life), flagged here for Shaun to widen if he wants the template's full reach.
- **Steampunk overlay — the Augmented template applied.** Corporeal undead rolls now take Shaun's actual **Steampunk-Augmented Undead** template (same homebrew file) instead of the generic idiom rewrite: CR +1; Str +4, Dex −2; natural armor +4; Undead type kept, Construct subtype gained; Piston Slam (Ex, +1d6, slam die steps up if it has one); Steam Charge (Ex); Alchemical Fortification (Ex); Boiler Explosion (Ex) at 0 hp (2d6 fire, 10 ft, Reflex DC 13 half); vulnerability to electricity (+50%); land speed −5 ft. Incorporeal undead (no corporeal frame to rebuild — the template's own prerequisite) keep the v1.12 idiom-form rewrite.
- Verification: `test3.mjs` extended (Twisted panel carries Smite Good, DR 5/cold iron, the magical-beast shift, and the ability adjustments on the Toad roll; the Desiccator exclusion re-checked against the new panel text; Steampunk-Augmented Desiccator on a queued roll with Piston Slam, CR +1, and Boiler Explosion asserted) — full suite PASS.

---

## Framing grounding — v1.14.1 (2026-11-11)

Shaun's grounding for the Twisted overlay, same call, carried into the panel's framing line verbatim in substance: the twisting is demon-defilement — "when demons move through the environment and they defile the environment, the creatures in the environment sometimes get twisted." The Twisted panel now opens: "one of the land's own creatures, twisted where the demons moved through and defiled the country around it." Text only; no mechanics changed.

---

## Feature toggles — v1.15 (2026-11-11) — Shaun: "Make them toggles too"

Shaun's ruling (AI DM voice call, recorded in canon): the Badlands bleed, the Steampunk machine weighting, and the steamcraft gear drops each get their own on/off toggle beside the overlay switches. Built exactly so: three feature toggles under the overlay toggles in the Roller — **Badlands bleed**, **Machine weighting**, **Gear drops** — each defaulting **ON** (they are his rulings), each persisting per device (`apocEncBleed` / `apocEncWeight` / `apocEncGear`), each gating **only its own feature**: the bleed toggle off means landscape rolls never bleed (the Badlands layer's conditions still show); the weighting toggle off means Steampunk rolls stand as rolled (the rewrite and drops still apply); the gear toggle off means no drop line (the rewrite and weighting still apply). A feature still needs its overlay on to do anything at all. All three are ordinary buttons under the platform treatment — movable, nestable, persistent — like every other switch on the page.
- Verification: `test3.mjs` extended (toggles exist and default ON; bleed queued-sequence suppressed with its toggle off, marks absent; Swamp roll stands as the Raven with weighting off; drop line absent with gear off; states persisted and restored) — full suite PASS.

---

## The city tables rebuilt + the scenario layer — v1.16 (2026-11-11) — Shaun: "The city encounters have to have more city encounters" + scenarios for encounters in general + the crowding amendment

Shaun's finding was exact: the three Bastion tables were 22/20/18 entries, every one of them carrying kinds ['construct'] — a city of machines, with a Hawk (a flyer, barred by the Melairshield) sitting at the head of all three. Rebuilt from the canonical pools:

- **Bastion (26 entries):** 22 person/city entries (4 crowd generics + 18 named NPCs), 3 grounded constructs, 1 animal. Composition: Street Crowd (160 wide), Gate Queue (100), Watch Patrol (110), Consortium Porters and Carters (70), Warforged (60), then the Watch and wall officers and citizens by record — Bram Holt, Tilda Ironfoot, Rivet, Vessa Kade, Unit Rook-9, Unit Bastion-4 "Bast", Ser Corvin Hale, Derek Windsfire, Ser Caspian Thorvald, Tells, Captain Rulathon, Xale, Helve Urtrace, Marshal Ezekiel Thorn, Inara Steelhand, Ser Ilya Vane — with Anvil-7 and Tomas Reyne, the Last Marshal at the 991–1000 tail.
- **Bastion Streets (23 entries):** 18 person/city, 2 constructs, 3 street creatures (Kenku, Moonrat, Mule — all flightless). Crowds lead: Street Crowd (130), Market Crowd (120), Watch Patrol (100), Queue (90); the street cast follows — Bram Holt, Pippa Underbough, Wrenna Caladrel, Tilda Cogspring, Fenwick Aldous, Jasker, Kailee Restinan, Mira Voss, Aldric Vane, Rodelik Karneth, PIP-9, Nyx Shadowveil, Sibil Thistledown, Derek Windsfire.
- **Bastion Districts / Interior (35 entries):** 29 person/city, 4 grounded interior constructs (Tin Golem, Animated Object, Caryatid Column, Runic Guardian), 2 others (Farrow, Kenku). Tenement Crowd (118), Market Crowd (90), Consortium Hall in Full Session (80), Queue (70), Watch Patrol (60), then the district cast — Sella Turgran, Thaloril Fenwick, Brin Odo, Kazrik Emberhand, Ingrid Hollowdelve, Bram Tallowick, Pell Underbough, Sylvaris Lonn, Seraphine Cole, Professor Ostwick Hale, Durgan Ironvein, Vespera Thorn, Grath Ironjaw, Brother Cadmus Vale, Mira Cogwheel, Durgan Stonevein, Mirella Voss, Fenwick Loam, Zareth the Pale, Dagna Stoneveil, Selune-Marra Vael, Forge Father, Elowen Thistledown — with Naronen Monroe at the tail.
- **Every named NPC entry** carries its ALL-150 section verbatim as the full stat block (heading hash stripped, as the existing NPC entries do), CR = its class levels / ECL from its own section, number "Solitary" as published, and a scenario seed (Faction / Role / Motivation) extracted from its own section text only. Portraits copied from the ts-spaces NPC assets under the same slugs; every city entry — NPC, generic, creature — is pictured.
- **Removed from the city tables** (no business as routine Bastion rolls): Hawk (flyer — Melairshield), Hellfire Engine, Blackstone Gigant, Scouring Slinger, Thoon Elder Brain, Mind Flayer, Nightmare, and the rest of the old all-construct lists (Bogun, Skorne, Lumi, golem stacks, inevitables, Thoon pieces). Grounded city machines kept: Tin Golem (a published working servant), Clockroach, Clockwork Stallion was NOT kept (streets are crowds now; the Warforged and Mule carry that weight), Caryatid Column and Runic Guardian (interior guardians), Animated Object. Removed creatures remain placed on their other tables where they had them; Bastion-only placements (e.g. Bogun, Skorne, Lumi) leave the placed set with this rebuild and stay in their rosters.
- **Hard screening held:** no undead, no demons, no dragons or half-dragons, no drow, no tieflings, no flyers on any Bastion table — verified by machine check (kinds, names, and every entry's printed Speed line). Excluded by that screen from the NPC cast: Zesskar, Krixx Vane, Zyx'ara Vilethorn, Threnos Ashborn (tieflings); Korvath the Ashen (half-dragon); Lucian Graveborn (vampire); Azgorath the Horned (half-fiend, winged); Queen Seraphine Morvain and Nethrak the Blighted (liches); demon-enclave and Kingdom-of-the-Undead people (Malachi Vane, Tommin Reed, Mother Ysolde Brine, Vasha Rook, Mother Sabeline Roost, Selene Marrow, Sister Thessaly Nightveil, Lord Malachar the Pale, Morvain the Hollow General, Prioress Nocturne, Cinder Queen Vesskara) — living agents of powers the shield bars are not routine city rolls.
- **Held, not guessed (101+ figures):** sections 101–149 marked "statted in life / at her height / historical" were left out — Drago Salvoro, Iriadorm Wintermist, Rector Janus Gilder, Ranressa Shiard, Oth Eltorchul, Ahghairon, Samius Freeman, Kiorn Kester (marked DECEASED), and the dragons Grimnoshtadrano and Gaulauntyr (dragons, barred outright). Also held as not clearly present-day ground-level Bastion people: Halaster, Lord These Eltorchul, Maaril (the Dragon Mage), James Wilkins, Renfroe Skysail (flying corps — flight inside the shield is the corps' own question, not this table's), Aydi Zarastian (weretiger; her section records three Watch dead at her escape). The 101+ figures placed are the tracker people whose sections present them as the city's living, working present: the Freeman clinic, Watch command (Rulathon, Derek Windsfire, Tells), guild and temple people, and their peers.
- **The crowding amendment (Shaun, mid-build): "the city is very, very, very, very, very crowded."** Applied as ordered: crowd generics carry the widest bands on all three tables and large number-appearing (Crowd 20–400, Queue 20–300, Patrol 3–12, Assembly 30–200); named NPCs stay solitary per their records — the crowding around them lives in the table notes and the scenario layer, never in a falsified Organization line. The crowd generics are generator entries (Shaun's city population), honestly labeled as such in their blocks: no published stat line exists for a crowd, none was invented; individuals within a crowd use the city's own NPC records on these tables. Their pictures are scene art from Shaun's own map files (streets, markets, a clerk's office, a barracks street, the Bastion from its walls), credited as scene art.
- **Warforged / Mule kinds on the Bastion copies:** the build-era erroneous kinds marks noted in earlier COVERAGE (a few living creatures carrying ['undead'] / ['demon'] marks) are cleaned on the Bastion copies only — Warforged reads ['construct'], Mule reads [] — because the Bastion ward check reads kinds literally. The marks on other tables' copies stand as previously reported, not rewritten.

**The scenario layer (Shaun: "give me some possible scenarios to go along with these encounters. Who, what, when, where, why, and how" — encounters in general).** Every roll now also presents a **Scenario** panel with six labeled lines. Who = the rolled entry by name and number appearing — for named NPCs their own Faction/Role (and, in Why, their own Motivation) from their ALL-150 sections; when an overlay fired, Who names the version in play (Twisted / Steamwork / Steampunk-Augmented / bled in from the Open Wastes) with the published base named. What/Why/How are drawn from frames keyed by context (city, road, wilderness surface, underground, ruins, water) merged with frames keyed by the creature's kind (person, machine, undead, demon, beast, other); When and Where come from the context. The frames are DM-facing possibilities, phrased as possibilities, and canon-checked: no dawn/sunset/sun/stars anywhere (the grey sky), no Fog in the Bastion or underground, hatestorms only as Badlands weather, no dragon appearances, no summoning or planar arrivals, claimed/unclaimed lore only on undead, Reclamation Item Retrieval as the city's business. City frames default to packed conditions throughout; the one emptiness frame names an emptied Bastion street as the omen it is. The same frames stand as a readable "Possible scenarios" section in ENCOUNTER-TABLES.md.
- Verification: `verify.py` OVERALL PASS (Bastion category whitelist extended for street animals — Animal/Magical Beast — per Shaun's brief); `test7.mjs` added (persons outnumber constructs on all three Bastion tables, no barred kinds, no fly speeds, absurd constructs gone, crowd widest-band and crowd number checks, six scenario lines on city/streets/wilderness/underground rolls, overlay Who naming, Bram Holt's own Faction/Role on his Who line); test3/test4/test5/test6 PASS (test6's pool picture count updated 339 → 358 distinct; test3/test6 DATA extraction moved to the new SCEN delimiter).

---

## The city fills up + scenarios on every roll — v1.16 (2026-11-11)

Shaun's orders, from the voice call: "The city encounters have to have more city encounters"; scenarios to go with the encounters — who, what, when, where, why, and how — first for the city, then for the encounters in general; and the standing fact stated as a rule: "the city is very, very, very, very, very crowded." The city rebuild and the scenario system were built on the call side directly in the project files; the release was then verified, repaired, and shipped from the Encounter Generator chat. What stands:

- **The Bastion tables are city tables now.** Before, they were almost all constructs (60 entries, ~57 of them machines). Now every Bastion table LEADS with the crowd itself: Citizens of the Bastion — Street Crowd (16% of the citywide table), Gate Queue, Market Crowd — At the Crush, Tenement Crowd, queues at fountains/offices/bread lines, Consortium Porters and Carters, a Consortium Hall in full session, and the Watch Patrol — then the named people of the city from Shaun's cast (Bram Holt, Sella Turgran, Tilda Ironfoot, the Warforged citizens Rivet, Unit Rook-9, Unit Bastion-4, Ser Corvin Hale, Captain Rulathon, Xale, and more), the city's constructs, and its working animals. Bastion 26 entries, Streets 22, Districts/Interior 35. Crowd and people entries carry scenario fields (faction/role/motivation) drawn from their own records. The city boundary holds — a ward check in verify.py limits the Bastion tables to patrols/citizens/Warforged/War-Torn/constructs/vermin/animals/NPCs, and nothing the Melairshield bars is inside.
- **Scenarios on every roll.** A Scenario panel closes every result — Who, What, When, Where, Why, How — built from the rolled creature's own records (its scenario fields; a named person's faction, role, and motivation from their section) framed by setting: context banks for city / road / wild / underground / ruins / water crossed with kind banks for person / machine / undead / demon / beast / other. It respects the overlays (a Steamwork or Twisted roll is named as such in the Who line; a bled-in roll says so). The packed-city rule is structural, not decorative: city frames are written inside the crowd — shoulder-to-shoulder streets, queues, stacked tenements — and one frame names the exception that proves it: an emptied street in the Bastion is itself an omen. The tables document (ENCOUNTER-TABLES.md) carries the same scenario frames per table.
- Repairs made at release: the ward check admits domestic/working Animals (the Mule belongs in the wards; the check's purpose is keeping wild threats out); the Moonrat came off Bastion Streets (a magical beast is not a ward animal) and the table was rebanded to 1000. One duplicate scenario implementation (built in parallel in this chat) was removed in favor of the call-side system after comparison — one panel, one system.
- Verification: verify.py OVERALL PASS; test3 (extended: scenario panel on city and landscape rolls, all six questions answered, crowd leads the city table, packed-city frame present, the entry's own motivation used), test4, test5, test6 PASS on staging, the publish copy, and the live bytes.

---

## The twisting happens randomly — v1.17 (2026-11-11)

Shaun's ruling on the flagged chance question: "The twisting happens randomly." Implemented as ruled — the Twisted overlay no longer twists every eligible roll. With the overlay ON, each eligible result rolls its own chance in `doRoll`; on a twist, the Doc #4 template panel, the scenario's Who line, and the history mark all fire together (one per-result outcome, shared by every layer of the presentation); on a miss, the creature stands exactly as published, as if the overlay were off for that roll. The ruling is the randomness itself — chance, not a fixed rate or schedule in the world. The generator's working chance is **1 in 5**, recorded here and in ENCOUNTER-TABLES.md as a build parameter (adjustable in one line), never presented as a canon rate. The second flagged item (Open Wastes pool blending) remains open — Shaun has not ruled on it, and the bleed stands as built.
- Verification: `test3.mjs` extended (chance gate: a 0.9 chance roll under the ON overlay leaves the creature untwisted, panel and history mark absent; the 0.0 roll twists with the full template panel) — full suite PASS. This release carries the v1.16 city/scenario build as its base (separately verified); one push ships both.

---

## Pool blending settled — v1.17.1 (2026-11-11)

Shaun's ruling on the second flagged item: blending happens randomly, at a low rate — lower than one in ten, confirmed at **one in twenty (5%)** for the Open Wastes pool bleeding into another landscape's roll when the Badlands layer is in play. That is the mechanic as built since v1.13.0 and live in v1.17.0 — no change was needed; this entry closes the flag the v1.17 note left open. The readings, stated for correction: the bleed fires only on landscape tables under the layer (never the Bastion tables; the city boundary holds), never displaces Saint James, replaces the landscape roll with the Open Wastes result, and is gated by its feature toggle (default on). Both flags are now settled, and their relation stands as Shaun put it: the twisting's rate (working chance 1 in 5) sits above the blending rate (1 in 20).

---

## Steampunk-Augmented Undead — original kept, draft void (2026-11-11)

Shaun's ruling: "Keep the original." The Steampunk overlay's undead mechanics stand permanently on Shaun's original Steampunk-Augmented Undead template — the text in his Homebrew Wild-Magic Surge Table Doc (section 3), carried verbatim by the Blendcrafter library record, and applied by this generator since v1.14.0. A stand-in draft of the feature texts, produced on the voice call under the mistaken belief that the original was lost, is VOID: never filed, never built to. The generator's files were searched in full for the draft's distinctive text (five fingerprint phrases) — no copy exists anywhere in the project, so nothing required removal. The held item from the finish order is closed with no build change; this note is the record, riding the next push.

---

## Twice as many chart options — v1.18 (2026-11-12)

Shaun's order: "In the encounter generator on the thousand D chart I want twice as many options." The Chart Generator's generated d1000 charts now carry up to **36 options** (bands), doubled from the previous cap of 18. The cap is a maximum — a chart drawn from a source with fewer eligible creatures (a single small table, a narrow EL band) still carries as many as the source holds; a whole-pool chart at a broad EL range fills all 36 (verified). Weights, normalization to exactly 1000, roll-on-chart, and load-into-roller are unchanged. This push also carries the Steampunk-Augmented closure note recorded 2026-11-11.
- Verification: `test4.mjs` extended (whole-pool chart row count asserted >18 and ≤36; the reference run lands exactly 36) — full suite PASS on staging, the publish copy, and the live bytes.

---

## Chart Generator — twice as many options on the d1000 chart (v1.18.0, 2026-11-12)

Shaun's order (voice call, 2026-11-12): twice as many options on the d1000 chart. The Chart Generator's option cap is raised from 18 to 36 (the weighted candidate slice in the chart builder); band normalization to exactly 1000 is unchanged, as are the chart's roll and load-into-roller paths. Verified on the live build: whole-pool charts generate 36 options at default filters and at an EL 5–8 filter; a single-table source remains limited by that table's own candidate pool, as before. Recorded here at verification; rides the next push.

---

## Space — the wildspace environment (v1.19.0, 2026-11-12)

Shaun's order (via the AI DM hub, voice call 2026-11-12; the word was SPACE, not "spacing" — the layout/spacing reading was a misread and is cancelled): a twentieth table, **Space — Wildspace**, built like the other environments (d1000, stat blocks, pictures, scenarios) from his canon only.

**Population (35 entries, 33 new distinct; totals now 20 tables / 458 entries / 391 distinct, pictures 391/391, stat blocks 167 full + 224 partial + 0 missing):**
- **26 spelljamming hulls** from the Blendcrafter Spelljamming records — boxed-set Lorebook hulls (Tradesman, Wasp, Dragonfly, Drakkar, Hammership, Dragonship, Squid Ship, Nautiloid, Neogi Mindspider, Tyrant Ship) and wider-line hulls (Cargo Barge, Goblin Blade, Turtle Ship, Leaf Ship, Eel Ship, Lamprey Ship, Shrike, Swan Ship, Hummingbird, Octopus Ship, Skeleton Ship, Man-o-War Archaic, Monarch Armada, Deathglory, Quad of Thay) — each carrying its published hull record as a partial block. Ships have no published CR; the CR shown is a disclosed generator rating by hull class. Pictures are the hulls' printed deck plans from Shaun's collection (Blendcrafter deck-plan sheets), except the Tyrant Ship (generated, no plan on file).
- **The Enemy Battleship** (Shaun's own homebrew warship; partial from his file's printed header; picture generated).
- **4 Peoples of Space** as encounters (Giff Mercenary Company, Hadozee, Scro War Crew, Dracon) — partial blocks from their converted race records; pictures generated from the published descriptions (no official art on file). The other four peoples (Grommam, Hurwaet, Rastipede, Xixchil) sail as crews within the hull entries' records.
- **2 stations**: the Rock of Bral (picture: Shaun's collection art) and an unnamed waystation (canon: a couple of other stations exist, unnamed; picture generated). Dragon Rock is named in the sphere canon as a separate station of the map; it is not a generator entry (the tables' no-dragons name check is a creature rule, and no encounter record for the Rock as a port exists in his material beyond its map entry).
- **2 demon incursions** (Shadow Demon, Marilith) — the pool records themselves, placed by the sphere canon: demons fly incursions outward from Toril, their home base. These are the table's 2 ecology weak fits (their published Environment lines are planar/terrestrial) — placed by canon, not by those lines, and recorded here as deliberate.
- **The Spelljammer** at the extreme tail (991–1000), picture = its printed plan sheet from Shaun's collection.

**Boundary and overlay treatment (the space form of the city-boundary rule):** the table is the sphere's own population — not a Bastion table, not an overlay. The Badlands layer does not reach it (the layer is the blighted land's condition; wildspace has the Cut instead), the Open Wastes bleed neither enters nor leaves it, hulls (kinds: ship) are never Twisted and under Steampunk take the machine line rather than a Steamwork rewrite, and the machine weighting cannot bend its rolls (its population holds no construct-type entries). Scenarios draw a dedicated wildspace context (the drift between worlds, the Toril run, the lanes, anchorages).

**Name collision resolved:** the wider-line hull "Octopus" is entered as **Octopus Ship** — the plain name already belongs to the animal on Open Water, and the pool is name-keyed (compare Squid Ship / Turtle Ship in the same fleet).
