# APOC Survival — Random Encounter Tables (d100)

Built 2026-11-09 from canonical sources only: Demons roster (361 in file — the build order said 355; file truth 361 governs), Undead roster (346), Sentient Constructs roster (92), NPCs cast (150), APOC-VTT monster registry (1,486, Monsternomicon I at 2002-original values).

**Stat blocks & pictures:** every creature on these tables carries its full stat block and its picture in the roller (`index.html`) and in [STATBLOCKS.md](STATBLOCKS.md) / `encounters.json` — roll on the page to see the rolled creature's block and picture. This document stays the quick-reference table set.

## The Badlands — the world outside the cities (Shaun, canon correction 2026-11-11)
**The Badlands is everywhere the city is not.** It is all the untamed world outside the held cities — everywhere the demons crossed the landscape and blighted it as they travelled through. Every table in this set except the Bastion's own describes a place WITHIN the Badlands: its plains, forests, hills, mountains, deserts, swamps, waters, ruins, roads, and deep places are regions of the Badlands, not lands beside it. The **Badlands — Open Wastes** table is the general table for the open blighted country of the Badlands, between and beyond those regions. Only the Bastion tables are inside a held city.

## APOC screening rules (hard)
- No summoning, no planar arrivals. Demons are mortal enclave demons already here; undead are the Kingdom of the Undead and local undead.
- Fog of Life is surface-only — it does not apply underground or inside the Bastion. Hatestorms rage across the Badlands — the whole untamed world outside the held cities; inside the Bastion only regular fog applies.
- The Bastion's Melairshield bars undead, demons, dragons and flying creatures. Bastion-interior tables are Watch/Guard patrols, citizens, consortium people, Warforged, War-Torn, sentient constructs, vermin and NPCs.
- Drow do not appear (folded into the demons) and tieflings do not appear (they were taken) — both excluded entirely.
- **Dragons haven't been seen in a thousand years** (Shaun, 2026-11-09) — a legend under the Council of Wyrms. NO dragon is rollable on any table, including dracolich and any Dragon-type creature; excluded and counted in COVERAGE.md.
- Undead entries carry Shaun's house rules in their APOC note: maximized hp, +4 turning/control resistance re-rolled every round, zombie-type bite infects.

## WORLD LORE — claimed and unclaimed undead (Shaun, 2026-11-09: "Not world law, world lore")
There are two kinds of undead, as it were. The **unclaimed** are wild undead, living out in the Badlands — each in its own corner of it — following no nation's rule. The **claimed** are the undead nation — the Kingdom of the Undead — ruled by its own laws and its own way of doing things. The nation's society is led from the top: the highest order of undead — its most powerful and intelligent — make up the society's upper crust and leadership, and the lesser claimed are its rank and file under them. Every undead entry carries a lore tag (`undeadKind`: claimed / unclaimed / either) in the APOC layer only; published stat lines are untouched, and no specific laws, rulers, or customs of the nation are invented — only the above is established. Claimed undead still never appear inside the Bastion: the Melairshield bars all undead regardless of claimed status.

- Correction pass 2026-11-09: the Drowned (Monster Manual III) restored — it is an undead, not a drow; the drow exclusion is word-boundary (the Tirbana Drowser, a Monster Manual V magical beast, was a second substring false positive). Extraction-noise rows cleaned — see COVERAGE.md.

- Improvement pass 2026-11-09: full stat blocks merged onto every entry (see STATBLOCKS.md), pictures matched from the roster picture pools, and an ecology audit applied (published Environment governs; swaps and weak fits logged in COVERAGE.md).

## Area-type layering & folded combinations
- Open country: use the region's table as-is; for the open blighted wastes between regions, use Badlands — Open Wastes, the Badlands' general table.
- Road/trail: roll on Road/Trail generic, or the terrain table — road travellers are drawn from humanoid/giant/animal stock, so a separate per-terrain road matrix is FOLDED into the one generic Road/Trail table (reason: roads cross terrains; duplicating 11 road tables would repeat the same traveller pool).
- Dungeon/interior: Underground — Dungeon/Interior table (folded from Underground+Ruins pools, reason: built below-ground interiors share both pools).
- City streets/districts: Bastion Streets and Bastion Districts/Interior are separate tables (ward-screened).
- Ruins interior: separate Ruins Interior table.
- River/Lake/Coast is split into Shoreline and Open Water sub-tables (aquatic creatures only in Open Water).
- Per-terrain city and per-terrain dungeon matrices are FOLDED as above — the Bastion is APOC's one great city table-set, and dungeons are terrain-independent interiors. Every named terrain and area type is covered.

## Badlands — Open Wastes (d100)

*The general table for the open blighted wastes of the Badlands — the untamed world outside the held cities; every other table in this set but the Bastion's is another place within it. Dragons haven't been seen in a thousand years — a legend under the Council of Wyrms. Flavor only: no roll ever produces a dragon. Fog of Life lies on this surface terrain.*

| d100 | Encounter | CR | Number appearing | Source |
|---|---|---|---|---|
| 01–07 | Fiendish Symbiont, Fiendish Familiar | 0.125 | Solitary (see source book) | Fiend Folio |
| 08–13 | Nerra, Varoot | 1 | Solitary (see source book) | Fiend Folio |
| 14–20 | Desiccator | 2 | Solitary or gang (2–5) | Libris Mortis |
| 21–27 | Vasuthant | 2 | Solitary | Monster Manual III |
| 28–33 | Tin Golem | 3 | Solitary, pair, or gang (3–4) | Dragon Magazine / Constructs roster (web-sourced entry) |
| 34–39 | Rutterkin | 3 | Solitary (see source book) | Fiendish Codex I, Book of Vile Darkness |
| 40–45 | Flameskull | 4 | Solitary or company (3–12) | Lost Empires of Faerûn |
| 46–50 | Gravetouched Ghoul Harpy | 5 | Solitary (see source book) | Libris Mortis |
| 51–55 | Karina | 5 | Solitary, gang (2-6) | Encyclopedia of Demons & Devils Vol. 1 |
| 56–60 | Bloodmote Cloud | 6 | Solitary, cloud (2–4 swarms), or infestation (7–12 swarms) | Libris Mortis |
| 61–65 | Lesser Spawn of Juiblex | 6 | Solitary (see source book) | Monster Manual V |
| 66–70 | Cinder Ghoul | 7 | Solitary, gang (2–5), or mob (6–11) | Tome of Horrors II |
| 71–74 | Mohrg | 8 | Solitary, gang (2–4), or mob (2–4 plus 5–10 zombies) | Monster Manual I |
| 75–79 | Shadow Demon | 8 | Solitary | Book of Vile Darkness |
| 80–83 | Kappa | 9 | Solitary | Encyclopedia of Demons & Devils Vol. 1 |
| 84–86 | Cerebrilith | 10 | Solitary or gang (2–4) | Expanded Psionics Handbook |
| 87–89 | Demon, Kastighur | 11 | Solitary or pair (Fox Hunt, EL 16: two kastighurs — MM4 p.43; kastighurs typically serve more intelligent and powerful demons as hunters and jailers) | Monster Manual IV |
| 90–92 | Infernal Soul Stalker | 12 | Solitary (see source book) | Monsternomicon Vol. 1 |
| 93–95 | Blood Fiend | 14 | Solitary, pair, or gang (3–5) | Fiend Folio |
| 96–97 | Dream Vestige | 16 | Solitary | Libris Mortis |
| 98 | Lifespark Construct | 18 | Solitary | Advanced Bestiary |
| 99 | Isitwalangcengce | 21 | Solitary | Encyclopedia of Demons & Devils Vol. 1 |
| 100 | Saint James | 15 | 1 (plus sentient telepathic dire crocodile partner and flying tavern ST-JAMES — Booze and Magic; crew of unseen servants / invisible stalkers) | Shaun canon / NPCs #150 — Saint James file |

APOC notes, stat blocks and pictures per entry are in encounters.json / the roller / STATBLOCKS.md (undead house rules, enclave-demon note, named-encounter flags).

## Plains (d100)

*Dragons haven't been seen in a thousand years — a legend under the Council of Wyrms. Flavor only: no roll ever produces a dragon. Fog of Life lies on this surface terrain.*

| d100 | Encounter | CR | Number appearing | Source |
|---|---|---|---|---|
| 01–06 | Toad | 0.1 | Solitary (see source book) | Monster Manual I |
| 07–12 | Kenku | 0.5 | Solitary (see source book) | Monster Manual III |
| 13–18 | Raggamoffyn | 1 | Solitary, pair, or gang (3–6) | Monster Manual II |
| 19–25 | Desiccator | 2 | Solitary or gang (2–5) | Libris Mortis |
| 26–31 | Swarm, Bat | 2 | Solitary, cloud (2–4 swarms), or infestation (7–12 swarms) | Monster Manual I |
| 32–36 | Dinosaur, Deinonychus | 3 | Solitary (see source book) | Monster Manual I |
| 37–42 | Carrionette | 3 | Solitary or pack (2d4) | Dragon Magazine #339 |
| 43–47 | Crocodile, Giant | 4 | Solitary (see source book) | Monster Manual I |
| 48–52 | Schir | 4 | Solitary or pack (3–8) | Book of Fiends |
| 53–57 | Deadly Sin, Gluttony | 5 | Solitary | Encyclopedia of Demons & Devils Vol. 1 |
| 58–63 | Mummy | 5 | Solitary, warden squad (2–4), or guardian detail (6–10) | Monster Manual I |
| 64–67 | Caryatid Column | 6 | Solitary, corbel (2), or colonnade (4–24) | Fiend Folio |
| 68–71 | Tainted Minion | 6 | Solitary or gang (2–5) | Heroes of Horror |
| 72–76 | Groaning Spirit | 7 | Solitary                                        Groaning spirits are the bane of other undead, and | Tome of Horrors Revised (Necromancer Games |
| 77–81 | Black Troll | 8 | Solitary | Monsternomicon Vol. I |
| 82–85 | Shetan | 8 | Solitary, gang (2-6) | Encyclopedia of Demons & Devils Vol. 1 |
| 86–88 | Mastodon | 9 | Solitary (see source book) | Monster Manual III |
| 89–91 | Githyanki Captain | 10 | Solitary (see source book) | Monster Manual IV |
| 92–94 | The Lord of Blades | 12 | Solitary (see source book) | Five Nations |
| 95–97 | Boneyard | 14 | Solitary | Libris Mortis |
| 98 | Hellfire Golem | 17 | Solitary | Fiend Folio |
| 99–100 | Crawling Head | 20 | Solitary | Fiend Folio |

APOC notes, stat blocks and pictures per entry are in encounters.json / the roller / STATBLOCKS.md (undead house rules, enclave-demon note, named-encounter flags).

## Forest (d100)

*Dragons haven't been seen in a thousand years — a legend under the Council of Wyrms. Flavor only: no roll ever produces a dragon. Fog of Life lies on this surface terrain.*

| d100 | Encounter | CR | Number appearing | Source |
|---|---|---|---|---|
| 01–05 | Toad | 0.1 | Solitary (see source book) | Monster Manual I |
| 06–11 | Eagle | 0.5 | Solitary (see source book) | Monster Manual I |
| 12–17 | Trollkin | 0.5 | Solitary (see source book) | Monsternomicon Vol. 1 |
| 18–23 | Mule | 1 | Solitary (see source book) | Monster Manual I |
| 24–29 | Abyssal Skulker | 2 | Solitary, pair, or gang (3–5) | Monster Manual II |
| 30–34 | Greenspawn Leaper | 2 | Solitary (see source book) | Monster Manual IV |
| 35–40 | Sythyss | 2 | Solitary or gang (2–5) | Monsternomicon Vol. I |
| 41–45 | Devil Rat Swarm | 3 | Solitary (see source book) | Monsternomicon Vol. 2 |
| 46–50 | Owl, Giant | 3 | Solitary (see source book) | Monster Manual I |
| 51–55 | Bluespawn Ambusher | 4 | Solitary (see source book) | Monster Manual IV |
| 56–60 | Myconid Guard | 4 | Solitary (see source book) | Monster Manual II |
| 61–65 | Avvite | 5 | Solitary or pack (1 avvite dire wolf and 4–7 followers) | Anger of Angels |
| 66–70 | Cadaver Lord | 5 | Solitary or troupe (cadaver lord plus 1–4 cadavers) | Tome of Horrors II |
| 71–74 | Dinosaur, Bloodstriker | 6 | Solitary (see source book) | Monster Manual III |
| 75–79 | Voidwraith | 6 | Solitary, pair, or gang (3–5) | Libris Mortis |
| 80–83 | Greenspawn Razorfiend | 7 | Solitary (see source book) | Monster Manual IV |
| 84–87 | Deadborn Vulture | 8 | Solitary (see source book) | Monster Manual V |
| 88–90 | Blackspawn Stalker | 9 | Solitary (see source book) | Monster Manual IV |
| 91–93 | Dire Elephant | 10 | Solitary (see source book) | Monster Manual II |
| 94–96 | Tatzylwurm, Black | 11 | Solitary (see source book) | Monsternomicon Vol. 2 |
| 97–99 | Riven | 13 | Solitary | Monsternomicon Vol. II |
| 100 | Elite Demon War Mount | 16 | Solitary (see source book) | Monster Manual III |

APOC notes, stat blocks and pictures per entry are in encounters.json / the roller / STATBLOCKS.md (undead house rules, enclave-demon note, named-encounter flags).

## Hills (d100)

*Dragons haven't been seen in a thousand years — a legend under the Council of Wyrms. Flavor only: no roll ever produces a dragon. Fog of Life lies on this surface terrain.*

| d100 | Encounter | CR | Number appearing | Source |
|---|---|---|---|---|
| 01–05 | Kobold | 0.25 | Solitary (see source book) | Monster Manual I |
| 06–10 | Gnome, Forest | 0.5 | Solitary (see source book) | Monster Manual I |
| 11–18 | Bram Holt | 1 | Solitary | NPCs — ALL-150 (Shaun's cast) |
| 19–24 | Raiment | 1 | Solitary | Libris Mortis |
| 25–30 | Baneguard | 2 | Solitary, pair, or squad (3–10) | Lost Empires of Faerûn |
| 31–36 | Malachi Vane | 2 | Solitary | NPCs — ALL-150 (Shaun's cast) |
| 37–41 | Bile Thrall | 3 | Solitary or troop (6-10); often accompa- | Monsternomicon Vol. II |
| 42–46 | Hoar Spirit | 3 | Pack (2–5) or gang (6–11) | Tome of Horrors II |
| 47–51 | Skin Kite | 3 | Solitary, pair, or flock (5–8) | Libris Mortis |
| 52–56 | Draug | 4 | Solitary or crew (1 draug plus 6-11 brine | Tome of Horrors Revised (Necromancer Games |
| 57–60 | Orc Berserker | 4 | Solitary (see source book) | Monster Manual IV |
| 61–65 | Anvil-7 | 5 | Solitary | NPCs — ALL-150 (Shaun's cast) |
| 66–70 | Cadaver Lord | 5 | Solitary or troupe (cadaver lord plus 1–4 cadavers) | Tome of Horrors II |
| 71–75 | Darnoc | 6 | Solitary or gang (2-4) | Tome of Horrors Revised (Necromancer Games |
| 76–79 | Apparition | 7 | Solitary or gang (2-4)                                                              succeeds, the victim | Tome of Horrors Revised (Necromancer Games |
| 80–83 | Groaning Spirit | 7 | Solitary                                        Groaning spirits are the bane of other undead, and | Tome of Horrors Revised (Necromancer Games |
| 84–86 | Bladerager Troll | 8 | Solitary (see source book) | Monster Manual V |
| 87–90 | Scylla Flock | 8 | Solitary, flight (2–4), or colony (5–10) | Monsternomicon Vol. II |
| 91–93 | Aspect of Vecna | 10 | Solitary | Miniatures Handbook |
| 94–96 | Devourer | 11 | Solitary | Monster Manual I |
| 97–99 | Jarilith | 13 | Solitary, pair, or pride (6–10) | Monster Manual II |
| 100 | Giant, Eldritch | 15 | Solitary | Monster Manual III |

APOC notes, stat blocks and pictures per entry are in encounters.json / the roller / STATBLOCKS.md (undead house rules, enclave-demon note, named-encounter flags).

## Mountains (d100)

*Dragons haven't been seen in a thousand years — a legend under the Council of Wyrms. Flavor only: no roll ever produces a dragon. Fog of Life lies on this surface terrain.*

| d100 | Encounter | CR | Number appearing | Source |
|---|---|---|---|---|
| 01–07 | Moonrat | 0.25 | Solitary (see source book) | Monster Manual II |
| 08–13 | Krenshar | 1 | Solitary (see source book) | Monster Manual I |
| 14–19 | Greenspawn Leaper | 2 | Solitary (see source book) | Monster Manual IV |
| 20–25 | Worg | 2 | Solitary (see source book) | Monster Manual I |
| 26–32 | Hoar Spirit | 3 | Pack (2–5) or gang (6–11) | Tome of Horrors II |
| 33–38 | Yuan-ti Pureblood | 3 | Solitary (see source book) | Monster Manual I |
| 39–43 | Owlbear | 4 | Solitary (see source book) | Monster Manual I |
| 44–48 | Cyclops | 5 | Solitary (see source book) | Monsternomicon Vol. 2 |
| 49–54 | Shaft Wight | 5 | Solitary or small band (2–6) | Monsternomicon Vol. I |
| 55–59 | Bluespawn Stormlizard | 6 | Solitary (see source book) | Monster Manual IV |
| 60–64 | Redspawn Arcaniss | 6 | Solitary (see source book) | Monster Manual IV |
| 65–68 | Chimera | 7 | Solitary (see source book) | Monster Manual I |
| 69–72 | Yuan-ti Abomination | 7 | Solitary (see source book) | Monster Manual I |
| 73–76 | Ken-Kuni | 8 | Solitary (see source book) | Monster Manual V |
| 77–80 | Bluespawn Burrower | 9 | Solitary (see source book) | Monster Manual IV |
| 81–84 | Rylkar Harridan | 9 | Solitary (see source book) | Monster Manual V |
| 85–87 | Ken-Li | 10 | Solitary (see source book) | Monster Manual V |
| 88–90 | Giant, Cloud | 11 | Solitary (see source book) | Monster Manual I |
| 91–93 | Brood Keeper Larva Swarm | 12 | Solitary (see source book) | Monster Manual III |
| 94–96 | Tatzylwurm, Pale | 12 | Solitary (see source book) | Monsternomicon Vol. 1 |
| 97–99 | Deathshrieker | 15 | Solitary | Monster Manual III |
| 100 | Lucent Worm | 17 | Solitary (see source book) | Fiend Folio |

APOC notes, stat blocks and pictures per entry are in encounters.json / the roller / STATBLOCKS.md (undead house rules, enclave-demon note, named-encounter flags).

## Desert (d100)

*Dragons haven't been seen in a thousand years — a legend under the Council of Wyrms. Flavor only: no roll ever produces a dragon. Fog of Life lies on this surface terrain.*

| d100 | Encounter | CR | Number appearing | Source |
|---|---|---|---|---|
| 01–06 | Giant Fire Beetle | 0.333333 | Solitary (see source book) | Monster Manual I |
| 07–12 | Camel | 1 | Solitary (see source book) | Monster Manual I |
| 13–18 | Giant Bee | 1 | Solitary (see source book) | Monster Manual I |
| 19–24 | Moonwing | 1 | Solitary (see source book) | Monsternomicon Vol. 1 |
| 25–30 | Thri-Kreen | 1 | Solitary (see source book) | Monster Manual II |
| 31–35 | Giant Bombardier Beetle | 2 | Solitary (see source book) | Monster Manual I |
| 36–40 | Monstrous Centipede | 2 | Solitary (see source book) | Monster Manual I |
| 41–45 | Armand | 3 | Solitary (see source book) | Monster Manual III |
| 46–50 | Cataphract Beetle | 3 | Solitary (see source book) | Monsternomicon Vol. 2 |
| 51–55 | Giant Wasp | 3 | Solitary (see source book) | Monster Manual I, Monster Manual IV |
| 56–60 | Lolth-Touched Monstrous Hunting Spider | 3 | Solitary (see source book) | Monster Manual IV |
| 61–65 | Swarm, Locust | 3 | Solitary, cloud (2–4 swarms), or infestation (7–12 swarms) | Monster Manual I |
| 66–70 | Giant Stag Beetle | 4 | Solitary (see source book) | Monster Manual I, Monster Manual IV |
| 71–74 | Harssaf | 5 | Solitary (see source book) | Monster Manual III |
| 75–78 | Chelicera | 6 | Solitary (see source book) | Monster Manual III |
| 79–82 | Swarm, Locust, Rapture | 6 | Solitary, cloud (2–4 swarms), or infestation (7–12 swarms) | Fiend Folio |
| 83–86 | Swarm, Locust, Bloodfiend | 8 | Solitary, cloud (2–4 swarms), or infestation (7–12 swarms) | Fiend Folio |
| 87–89 | Ethon | 10 | Solitary (see source book) | Monsternomicon Vol. 2 |
| 90–93 | Sand Dervish | 10 | Solitary | Monsternomicon Vol. II |
| 94–97 | Crawling Apocalypse | 11 | Solitary | Sandstorm |
| 98 | Desert Hydra (5-headed) | 15 | Solitary (see source book) | Monsternomicon Vol. 2 |
| 99–100 | Dry Lich | 18 | Solitary | Sandstorm |

APOC notes, stat blocks and pictures per entry are in encounters.json / the roller / STATBLOCKS.md (undead house rules, enclave-demon note, named-encounter flags).

## Swamp/Marsh (d100)

*Dragons haven't been seen in a thousand years — a legend under the Council of Wyrms. Flavor only: no roll ever produces a dragon. Fog of Life lies on this surface terrain.*

| d100 | Encounter | CR | Number appearing | Source |
|---|---|---|---|---|
| 01–06 | Raven | 0.166667 | Solitary (see source book) | Monster Manual I |
| 07–12 | Warforged | 0.5 | Solitary (see source book) | Monster Manual III |
| 13–18 | Shadar-Kai | 1 | Solitary (see source book) | Fiend Folio |
| 19–24 | Dire Maggot | 2 | Solitary (see source book) | Libris Mortis |
| 25–30 | Sickening Sleep | 2 | Solitary (see source book) | Monster Manual III |
| 31–36 | Boggle | 3 | Solitary (see source book) | Monster Manual II |
| 37–42 | Monstrous Scorpion | 3 | Solitary (see source book) | Monster Manual I |
| 43–47 | Arkamoi | 4 | Solitary (see source book) | Monster Manual V |
| 48–52 | Nagatha | 4 | Solitary (see source book) | Monster Manual IV |
| 53–57 | Kobold Wraith | 5 | Solitary, pair, gang (3–5), or pack (6–11). | Savage Species |
| 58–62 | Bog Mummy | 6 | Solitary, warden squad (2-4), or guard- | Tome of Horrors Revised (Necromancer Games |
| 63–67 | Catoblepas | 6 | Solitary (see source book) | Monster Manual II |
| 68–72 | Redspawn Arcaniss | 6 | Solitary (see source book) | Monster Manual IV |
| 73–76 | Darktentacles | 7 | Solitary (see source book) | Monster Manual II |
| 77–80 | Apparition | 7 | Solitary or gang (2-4)                                                              succeeds, the victim | Tome of Horrors Revised (Necromancer Games |
| 81–84 | Blackwing | 8 | Solitary (see source book) | Monster Manual V |
| 85–88 | Doru, Infectious Blasheme | 9 | Solitary (see source book) | Libris Mortis |
| 89–91 | Forest Haunt | 10 | Solitary (see source book) | Monster Manual V |
| 92–94 | Skindancer | 11 | Solitary (see source book) | Monster Manual III |
| 95–97 | Twilight Sisters | 12 | Solitary (see source book) | Monsternomicon Vol. 2 |
| 98 | Siege Beetle | 16 | Solitary (see source book) | Monster Manual V |
| 99–100 | The Black Duke | 19 | Solitary (see source book) | Monster Manual V |

APOC notes, stat blocks and pictures per entry are in encounters.json / the roller / STATBLOCKS.md (undead house rules, enclave-demon note, named-encounter flags).

## River/Lake/Coast (d100)

*Dragons haven't been seen in a thousand years — a legend under the Council of Wyrms. Flavor only: no roll ever produces a dragon. Fog of Life lies on this surface terrain.*

| d100 | Encounter | CR | Number appearing | Source |
|---|---|---|---|---|
| 01–09 | Cullenrock Barnacle | 0.5 | Solitary (see source book) | Monsternomicon Vol. 2 |
| 10–15 | Bog Trog | 1 | Solitary (see source book) | Monsternomicon Vol. 1 |
| 16–21 | Selkie | 1 | Solitary (see source book) | Fiend Folio |
| 22–28 | Zombie, Brine | 1 | Gang (2-4) or crew (6-11) | Tome of Horrors Revised (Necromancer Games |
| 29–34 | Sahuagin, Malenti | 2 | Solitary (see source book) | Monster Manual I |
| 35–40 | Dinosaur, Cryptoclidus | 3 | Solitary (see source book) | Monster Manual II |
| 41–46 | Fire Bat | 3 | Solitary (see source book) | Monster Manual II |
| 47–51 | Gargoyle, Kapoacinth | 4 | Solitary (see source book) | Monster Manual I |
| 52–56 | Vine Horror | 4 | Solitary (see source book) | Fiend Folio |
| 57–61 | Troll, Scrag | 5 | Solitary (see source book) | Monster Manual I |
| 62–66 | Glaistig | 6 | Solitary (see source book) | Monster Manual III |
| 67–71 | Storm Elemental, Large | 6 | Solitary (see source book) | Monster Manual III |
| 72–75 | Chuul | 7 | Solitary (see source book) | Monster Manual I |
| 76–79 | Naga, Water | 7 | Solitary (see source book) | Monster Manual I |
| 80–83 | Octopus, Giant | 8 | Solitary (see source book) | Monster Manual I |
| 84–87 | Drowned | 9 | Solitary, pair, or crew (3–12) | Monster Manual III |
| 88–90 | Ruin Elemental | 10 | Solitary (see source book) | Monster Manual V |
| 91–93 | Earth Weird | 12 | Solitary (see source book) | Monster Manual II |
| 94–95 | Cinder Swarm | 13 | Solitary (see source book) | Monster Manual III |
| 96–97 | Cyclonic Ravager | 15 | Solitary (see source book) | Monster Manual IV |
| 98 | Aboleth Mage | 17 | Solitary (see source book) | Monster Manual I |
| 99–100 | Ocean Strider | 18 | Solitary (see source book) | Monster Manual II |

APOC notes, stat blocks and pictures per entry are in encounters.json / the roller / STATBLOCKS.md (undead house rules, enclave-demon note, named-encounter flags).

## Underground (d100)

*Dragons haven't been seen in a thousand years — a legend under the Council of Wyrms. Flavor only: no roll ever produces a dragon. No Fog of Life here.*

| d100 | Encounter | CR | Number appearing | Source |
|---|---|---|---|---|
| 01–06 | Cerebral Symbiont, Mind Leech | 0.125 | Solitary (see source book) | Fiend Folio |
| 07–12 | Bram Holt | 1 | Solitary | NPCs — ALL-150 (Shaun's cast) |
| 13–18 | Vasha Rook | 1 | Solitary | NPCs — ALL-150 (Shaun's cast) |
| 19–24 | Lurking Strangler | 2 | Solitary (see source book) | Monster Manual III |
| 25–30 | Automaton Hammerer | 3 | Solitary (see source book) | Monster Manual II |
| 31–37 | Ghoul-Stirge | 3 | Solitary, gang (2-4), or flock (5-8) | Tome of Horrors Revised (Necromancer Games |
| 38–44 | Skulleton | 3 | Solitary | Tome of Horrors Revised (Necromancer Games |
| 45–49 | Gargoyle | 4 | Solitary (see source book) | Monster Manual I |
| 50–54 | Swarm, Centipede | 4 | Solitary, cloud (2–4 swarms), or infestation (7–12 swarms) | Monster Manual I |
| 55–59 | Howler Wasp Queen | 5 | Solitary (see source book) | Monster Manual IV |
| 60–64 | Beholder, Gauth | 6 | Solitary (see source book) | Monster Manual I |
| 65–69 | Mummy Administrator | 6 | Solitary (see source book) | Sandstorm |
| 70–73 | Dire Bear | 7 | Solitary (see source book) | Monster Manual I |
| 74–77 | Swordwraith | 7 | Solitary, company (2–8), or squadron (11–20 plus 1 leader of 6th–9th level) | Fiend Folio |
| 78–81 | Mindshredder Zenthal | 8 | Solitary (see source book) | Monster Manual III |
| 82–85 | Drowned | 9 | Solitary, pair, or crew (3–12) | Monster Manual III |
| 86–88 | Darkweaver | 10 | Solitary (see source book) | Fiend Folio |
| 89–92 | Grimweird | 11 | Solitary, pair, or clique (3–9) | Monster Manual III |
| 93–95 | Slaughterstone Eviscerator | 12 | Solitary (see source book) | Monster Manual III |
| 96–97 | Dolomite | 15 | Solitary (see source book) | Monsternomicon Vol. 1 |
| 98 | Ethergaunt, Black | 17 | Solitary (see source book) | Fiend Folio |
| 99–100 | Brammin Ironroot | 19 | Solitary | NPCs — ALL-150 (Shaun's cast) |

APOC notes, stat blocks and pictures per entry are in encounters.json / the roller / STATBLOCKS.md (undead house rules, enclave-demon note, named-encounter flags).

## Ruins (d100)

*Dragons haven't been seen in a thousand years — a legend under the Council of Wyrms. Flavor only: no roll ever produces a dragon. Fog of Life lies on this surface terrain.*

| d100 | Encounter | CR | Number appearing | Source |
|---|---|---|---|---|
| 01–06 | Cerebral Symbiont, Mind Leech | 0.125 | Solitary (see source book) | Fiend Folio |
| 07–12 | Gnoll | 1 | Solitary (see source book) | Monster Manual I |
| 13–18 | Bugbear | 2 | Solitary (see source book) | Monster Manual I |
| 19–24 | Triton | 2 | Solitary (see source book) | Monster Manual I |
| 25–30 | Ettercap | 3 | Solitary (see source book) | Monster Manual I |
| 31–36 | Salamander | 3 | Solitary (see source book) | Monster Manual I |
| 37–43 | Flameskull | 4 | Solitary or company (3–12) | Lost Empires of Faerûn |
| 44–50 | Vampire Spawn | 4 | Solitary or pack (2–5) | Monster Manual I |
| 51–55 | Ghostly Sorcerer | 5 | Solitary (see source book) | Tome of Magic |
| 56–60 | Troll | 5 | Solitary (see source book) | Monster Manual I, Monsternomicon Vol. 1 |
| 61–65 | Hag, Annis | 6 | Solitary (see source book) | Monster Manual I |
| 66–69 | Chaos Beast | 7 | Solitary (see source book) | Monster Manual I |
| 70–75 | Spectral Troll | 7 | Solitary or gang (2–4) | Tome of Horrors Revised (Necromancer Games |
| 76–79 | Mob of Zombies | 8 | Solitary (see source book) | Exemplars of Evil |
| 80–83 | Eloko | 9 | Solitary | Encyclopedia of Demons & Devils Vol. 1 |
| 84–87 | Yunwi Djunsti | 9 | Solitary, 2-5 (gang) | Encyclopedia of Demons & Devils Vol. 1 |
| 88–90 | Yagnoloth | 10 | Solitary (see source book) | Monster Manual II |
| 91–93 | Abeil Queen | 12 | Solitary (see source book) | Monster Manual II |
| 94–95 | Sarkrith, Spelleater | 13 | Solitary (see source book) | Fiend Folio |
| 96–97 | Thoon Elder Brain | 15 | Solitary (see source book) | Monster Manual V |
| 98 | Vermin Lord | 17 | Solitary (see source book) | Monster Manual III |
| 99 | Aspect of Dispater | 21 | Solitary (see source book) | Fiendish Codex II |
| 100 | Saint James | 15 | 1 (plus sentient telepathic dire crocodile partner and flying tavern ST-JAMES — Booze and Magic; crew of unseen servants / invisible stalkers) | Shaun canon / NPCs #150 — Saint James file |

APOC notes, stat blocks and pictures per entry are in encounters.json / the roller / STATBLOCKS.md (undead house rules, enclave-demon note, named-encounter flags).

## Bastion (d100)

*Dragons haven't been seen in a thousand years — a legend under the Council of Wyrms. Flavor only: no roll ever produces a dragon. No Fog of Life here.*

| d100 | Encounter | CR | Number appearing | Source |
|---|---|---|---|---|
| 01–07 | Hawk | 0.333333 | Solitary (see source book) | Monster Manual I |
| 08–14 | Bogun | 1 | Solitary (see source book) | Monster Manual II |
| 15–21 | Skorne | 1 | Solitary (see source book) | Monsternomicon Vol. 1 |
| 22–28 | Lumi | 2 | Solitary (see source book) | Monster Manual III |
| 29–34 | Clockwork Stallion | 3 | Solitary (see source book) | Monster Manual IV |
| 35–40 | Tin Golem | 3 | Solitary, pair, or gang (3–4) | Dragon Magazine #341 |
| 41–46 | Force Golem | 4 | Solitary (see source book) | Monster Manual V |
| 47–52 | Chain Golem | 5 | Solitary (see source book) | Monster Manual II |
| 53–58 | Incarnate Construct (sample) | 5 | Solitary (alone or with its spellcaster liberator) | Savage Species |
| 59–63 | Caryatid Column | 6 | Solitary, corbel (2), or colonnade (4–24) | Fiend Folio |
| 64–68 | Scyther of Thoon | 6 | Solitary (see source book) | Monster Manual V |
| 69–73 | Shrapnyl | 7 | Solitary (see source book) | Monster Manual II |
| 74–77 | Iron Maiden | 8 | Solitary | Monsternomicon Vol. 1 |
| 78–81 | Clockwork Horror, Adamantine | 9 | Solitary (see source book) | Monster Manual II |
| 82–85 | Bronze Serpent | 10 | Solitary (see source book) | Monster Manual II |
| 86–88 | Alchemical Golem | 11 | Solitary (see source book) | Monster Manual III |
| 89–91 | Wicker Man | 11 | Solitary (see source book) | Fiend Folio |
| 92–94 | Slaughterstone Eviscerator | 12 | Solitary (see source book) | Monster Manual III |
| 95–96 | Inevitable, Marut | 15 | Solitary | Monster Manual I |
| 97 | Zodar | 16 | Solitary | Fiend Folio |
| 98 | Blackstone Gigant | 18 | Solitary | Fiend Folio |
| 99–100 | Hellfire Engine | 19 | Solitary (see source book) | Fiendish Codex II |

APOC notes, stat blocks and pictures per entry are in encounters.json / the roller / STATBLOCKS.md (undead house rules, enclave-demon note, named-encounter flags).

## Road/Trail (generic — any terrain) (d100)

*Use with the terrain table of the terrain crossed; travellers, patrols, merchants and predators of the road.*

| d100 | Encounter | CR | Number appearing | Source |
|---|---|---|---|---|
| 01–08 | Toad | 0.1 | Solitary (see source book) | Monster Manual I |
| 09–15 | Elf, Gray | 0.5 | Solitary (see source book) | Monster Manual I |
| 16–22 | Bram Holt | 1 | Solitary | NPCs — ALL-150 (Shaun's cast) |
| 23–28 | Orc Battle Priest | 1 | Solitary (see source book) | Monster Manual IV |
| 29–34 | Boar | 2 | Solitary (see source book) | Monster Manual I |
| 35–40 | Leopard | 2 | Solitary (see source book) | Monster Manual I |
| 41–46 | Armand | 3 | Solitary (see source book) | Monster Manual III |
| 47–52 | Owl, Giant | 3 | Solitary (see source book) | Monster Manual I |
| 53–57 | Fiendish Cleric of Yeenoghu | 4 | Solitary (see source book) | Monster Manual IV |
| 58–62 | Tharn Bloodtrackers | 4 | Solitary (see source book) | Monsternomicon Vol. 2 |
| 63–67 | Harrier | 5 | Solitary (see source book) | Monsternomicon Vol. 2 |
| 68–72 | Blood Ape | 6 | Solitary (see source book) | Monster Manual II |
| 73–77 | Sea Tiger | 6 | Solitary (see source book) | Monster Manual III |
| 78–81 | Greenspawn Sneak Raid Leader | 7 | Solitary (see source book) | Monster Manual IV |
| 82–85 | Gravorg | 8 | Solitary (see source book) | Monster Manual II |
| 86–89 | Dinosaur, Triceratops | 9 | Solitary (see source book) | Monster Manual I |
| 90–93 | Yrthak | 9 | Solitary (see source book) | Monster Manual I |
| 94–96 | Giant, Cloud | 11 | Solitary (see source book) | Monster Manual I |
| 97–99 | Roper | 12 | Solitary (see source book) | Monster Manual I |
| 100 | Giant, Death | 16 | Solitary, dread (2–4 swarms), or horror (5–8 swarms) | Monster Manual III |

APOC notes, stat blocks and pictures per entry are in encounters.json / the roller / STATBLOCKS.md (undead house rules, enclave-demon note, named-encounter flags).

## Bastion Streets (d100)

*Inside the Melairshield: Watch patrols (inward), Guard (outward at gates/walls), citizens, consortium people, Warforged, War-Torn, constructs, vermin, NPCs. Demons, undead, dragons and flyers are barred by the ward.*

| d100 | Encounter | CR | Number appearing | Source |
|---|---|---|---|---|
| 01–09 | Hawk | 0.333333 | Solitary (see source book) | Monster Manual I |
| 10–17 | Clockroach | 1 | Solitary (see source book) | Monster Manual IV |
| 18–24 | Animated Object | 2 | Solitary (see source book) | Monster Manual I |
| 25–31 | Automaton Hammerer | 3 | Solitary (see source book) | Monster Manual II |
| 32–38 | Maug | 3 | Solitary, squad (4–7), warband (2–4 maugs plus 4–9 hobgoblins), or company (10–40 maugs plus 1 sergeant of 1st or 2nd level per 5 maugs, 2–4 lieutenants of 3rd–6th level, 1 leader of 7th–10th level, and 20–50 hobgoblins) | Fiend Folio |
| 39–44 | Clockwork Horror | 4 | Pair or component (3–8) | Monster Manual II |
| 45–50 | Mimic | 4 | Solitary (see source book) | Monster Manual I |
| 51–56 | Nightmare | 5 | Solitary (see source book) | Monster Manual I |
| 57–62 | Caryatid Column | 6 | Solitary, corbel (2), or colonnade (4–24) | Fiend Folio |
| 63–68 | Mechagargoyle | 6 | Solitary or band (2–5) | Monsternomicon Vol. 1 |
| 69–73 | Shrapnyl | 7 | Solitary (see source book) | Monster Manual II |
| 74–78 | Mind Flayer | 8 | Solitary (see source book) | Monster Manual I |
| 79–82 | Inevitable, Zelekhut | 9 | Solitary | Monster Manual I |
| 83–86 | Golem, Brass | 10 | Solitary (see source book) | Monster Manual II |
| 87–90 | Golem, Stone | 11 | Solitary (see source book) | Monster Manual I |
| 91–93 | Cadaver Collector | 12 | Solitary, pair, or squad (3–5) | Monster Manual III |
| 94–95 | Greater Shadesteel Golem | 14 | Solitary (see source book) | Monster Manual III |
| 96–97 | Woldwrath | 16 | Solitary (see source book) | Monsternomicon Vol. 2 |
| 98 | Merchurion | 17 | Solitary (see source book) | Fiend Folio |
| 99–100 | Scouring Slinger | 18 | Solitary (see source book) | Monster Manual V |

APOC notes, stat blocks and pictures per entry are in encounters.json / the roller / STATBLOCKS.md (undead house rules, enclave-demon note, named-encounter flags).

## Bastion Districts / Interior (d100)

*Interiors, consortium halls, tenements, markets. Ward-barred creatures do not appear; a barred creature is never rolled here.*

| d100 | Encounter | CR | Number appearing | Source |
|---|---|---|---|---|
| 01–09 | Hawk | 0.333333 | Solitary (see source book) | Monster Manual I |
| 10–17 | Farrow | 1 | Solitary (see source book) | Monsternomicon Vol. 1 |
| 18–25 | Dread Guard | 2 | Solitary (see source book) | Monster Manual II |
| 26–33 | Clockwork Mender Swarm | 3 | Solitary (see source book) | Monster Manual IV |
| 34–41 | Tin Golem | 3 | Solitary, pair, or gang (3–4) | Dragon Magazine #341 |
| 42–48 | Gargoyle | 4 | Solitary (see source book) | Monster Manual I |
| 49–55 | Guttersnipe | 5 | Solitary (see source book) | Monster Manual II |
| 56–62 | Stormcloud of Thoon | 5 | Solitary (see source book) | Monster Manual V |
| 63–68 | Mechagargoyle | 6 | Solitary or band (2–5) | Monsternomicon Vol. 1 |
| 69–74 | Shrapnyl | 7 | Solitary (see source book) | Monster Manual II |
| 75–79 | Rip Cutter | 8 | Solitary (see source book) | Monsternomicon Vol. 1 |
| 80–84 | Rogue Eidolon | 9 | Solitary (see source book) | Monster Manual II |
| 85–88 | Runic Guardian | 10 | Solitary (see source book) | Monster Manual II |
| 89–92 | Shadesteel Golem | 11 | Solitary (see source book) | Monster Manual III |
| 93–95 | Golem, Iron | 13 | Solitary (see source book) | Monster Manual I |
| 96–97 | Thoon Elder Brain | 15 | Solitary (see source book) | Monster Manual V |
| 98 | Inevitable, Quarut | 17 | Solitary | Fiend Folio |
| 99–100 | Prismatic Golem | 18 | Solitary (see source book) | Monster Manual III |

APOC notes, stat blocks and pictures per entry are in encounters.json / the roller / STATBLOCKS.md (undead house rules, enclave-demon note, named-encounter flags).

## Underground — Deep Dark (d100)

*Dragons haven't been seen in a thousand years — a legend under the Council of Wyrms. Flavor only: no roll ever produces a dragon. The deep dark: no Fog of Life underground.*

| d100 | Encounter | CR | Number appearing | Source |
|---|---|---|---|---|
| 01–07 | Mohrg | 8 | Solitary, gang (2–4), or mob (2–4 plus 5–10 zombies) | Monster Manual I |
| 08–15 | Bodak | 8 | Solitary or gang (2–4) | Monster Manual I |
| 16–24 | Shaft Wight | 5 | Solitary or small band (2–6) | Monsternomicon Vol. I |
| 25–33 | Slaughter Wight | 8 | Solitary, gang (2–4), or death squad (5–10) | Libris Mortis |
| 34–39 | Clockwork Horror, Adamantine | 9 | Solitary (see source book) | Monster Manual II |
| 40–47 | Pistol Wraith | 9 | Solitary | Monsternomicon Vol. I |
| 48–53 | Brain Golem | 10 | Solitary | Fiend Folio |
| 54–59 | Leechwalker | 10 | Solitary (see source book) | Monster Manual II |
| 60–66 | Atropal Scion | 11 | Solitary | Libris Mortis |
| 67–71 | Mud Golem | 11 | Solitary (see source book) | Monster Manual III |
| 72–76 | Cadaver Collector | 12 | Solitary, pair, or squad (3–5) | Monster Manual III |
| 77–80 | Death Centaur (Bone Golem) | 13 | Solitary (unique) | Constructs: It Is Alive |
| 81–84 | Ten-Headed Terror | 13 | Solitary (see source book) | Monster Manual III |
| 85–87 | Sample 15th-Level NPC Artificer (Warforged) | 15 | Solitary (see source book) | Sharn: City of Towers |
| 88–90 | Windghost | 15 | Solitary (see source book) | Monster Manual II |
| 91–92 | Zodar | 16 | Solitary | Fiend Folio |
| 93–96 | Marilith | 17 | Solitary or pair | Monster Manual I |
| 97 | Golem, Demonflesh | 18 | Solitary | Fiend Folio |
| 98 | Famine Spirit | 19 | Solitary, pair, brood (3–5), or band (2–5 plus 2–8 ghasts and 4–16 ghouls) | Monster Manual II |
| 99–100 | Titan | 21 | Solitary (see source book) | Monster Manual I |

APOC notes, stat blocks and pictures per entry are in encounters.json / the roller / STATBLOCKS.md (undead house rules, enclave-demon note, named-encounter flags).

## Underground — Dungeon / Interior (d100)

*Built interiors below ground; no Fog of Life.*

| d100 | Encounter | CR | Number appearing | Source |
|---|---|---|---|---|
| 01–08 | Cerebral Symbiont, Mind Leech | 0.125 | Solitary (see source book) | Fiend Folio |
| 09–15 | Giant Bee | 1 | Solitary (see source book) | Monster Manual I |
| 16–22 | Cadaver | 2 | Solitary or gang (2–5) | Tome of Horrors II |
| 23–29 | Zombie, Yellow Musk | 2 | Solitary or patch (2–5 yellow musk | Tome of Horrors Revised (Necromancer Games |
| 30–36 | Gadacro | 3 | Clutch (2–6), or murder (7–12) (per Sample Encounter, MM5 p.27) | Monster Manual V |
| 37–42 | Spectral Steed | 3 | Solitary or herd (2–12) | Ghostwalk |
| 43–49 | Haunt | 4 | Solitary | Tome of Horrors Revised (Necromancer Games |
| 50–55 | Avvite | 5 | Solitary or pack (1 avvite dire wolf and 4–7 followers) | Anger of Angels |
| 56–61 | Mummy | 5 | Solitary, warden squad (2–4), or guardian detail (6–10) | Monster Manual I |
| 62–66 | Curst | 6 | Solitary | Lost Empires of Faerûn |
| 67–71 | Yugoloth, Mezzoloth | 6 | Solitary (see source book) | Monster Manual III |
| 72–76 | Orc Plague Speaker | 7 | Solitary (see source book) | Monster Manual IV |
| 77–80 | Gorgon | 8 | Solitary (see source book) | Monster Manual I |
| 81–84 | Demon, Zovvut | 9 | Solitary or squad (1 plus 2–4 wights) | Monster Manual II |
| 85–88 | Azi-Dahaka | 10 | Solitary | Encyclopedia of Demons & Devils Vol. 1 |
| 89–92 | Derek Windsfire | 11 | Solitary | NPCs — ALL-150 (Shaun's cast) |
| 93–95 | Ooze, Elder Black Pudding | 12 | Solitary                                        to move over the opponents, affecting as many as it can | Monster Manual I |
| 96–97 | Ammit | 15 | Solitary | Encyclopedia of Demons & Devils Vol. 1 |
| 98 | Ethergaunt, Black | 17 | Solitary (see source book) | Fiend Folio |
| 99–100 | Ragewind | 19 | Solitary, pair, or cluster (3–5) | Monster Manual II |

APOC notes, stat blocks and pictures per entry are in encounters.json / the roller / STATBLOCKS.md (undead house rules, enclave-demon note, named-encounter flags).

## Ruins Interior (d100)

*Inside ruined structures on the surface; Fog of Life outside, thinner within.*

| d100 | Encounter | CR | Number appearing | Source |
|---|---|---|---|---|
| 01–07 | Cerebral Symbiont, Mind Leech | 0.125 | Solitary (see source book) | Fiend Folio |
| 08–14 | Kaorti | 1 | Solitary (see source book) | Fiend Folio |
| 15–21 | Desiccator | 2 | Solitary or gang (2–5) | Libris Mortis |
| 22–28 | Gibborite | 3 | Solitary or squadron (one gibborite with 3d6 humanoid barbarians, fighters, or warriors of 1st to 3rd level) | Anger of Angels |
| 29–34 | Lion | 3 | Solitary (see source book) | Monster Manual I |
| 35–40 | Vampire Spawn | 4 | Solitary or pack (2–5) | Monster Manual I |
| 41–47 | Painspeaker | 4 | Solitary or cabal (2–6) | Tome of Magic |
| 48–53 | Deadly Sin, Envy | 5 | Solitary | Encyclopedia of Demons & Devils Vol. 1 |
| 54–60 | Selune-Marra Vael | 5 | Solitary | NPCs — ALL-150 (Shaun's cast) |
| 61–65 | Gear Wyrm | 6 | Solitary (see source book) | Monsternomicon Vol. 1 |
| 66–70 | Chaos Beast | 7 | Solitary (see source book) | Monster Manual I |
| 71–75 | Susurrus | 7 | Solitary (see source book) | Monster Manual III |
| 76–79 | Pyre Troll | 8 | Solitary (see source book) | Monsternomicon Vol. 2 |
| 80–83 | Infernal, Quelvitar | 9 | Solitary (see source book) | Monsternomicon Vol. 2 |
| 84–88 | Draudnu | 10 | Rarely encountered in groups of more than four members (A Hard Place, EL 12: a pack of three draudnus — MM5 p.25) | Monster Manual V |
| 89–92 | Kastighur | 11 | Solitary or pair (Fox Hunt, EL 16: two kastighurs — MM4 p.43; kastighurs typically serve more intelligent and powerful demons as hunters and jailers) | Monster Manual IV |
| 93–95 | Death Centaur (Bone Golem) | 13 | Solitary (unique) | Constructs: It Is Alive |
| 96–97 | Giant Psurlon | 15 | Solitary (see source book) | Monster Manual II |
| 98 | Inevitable, Quarut | 17 | Solitary | Fiend Folio |
| 99 | Kumbhakarna | 20 | Unique | Encyclopedia of Demons & Devils Vol. 1 |
| 100 | Saint James | 15 | 1 (plus sentient telepathic dire crocodile partner and flying tavern ST-JAMES — Booze and Magic; crew of unseen servants / invisible stalkers) | Shaun canon / NPCs #150 — Saint James file |

APOC notes, stat blocks and pictures per entry are in encounters.json / the roller / STATBLOCKS.md (undead house rules, enclave-demon note, named-encounter flags).

## River/Lake/Coast — Shoreline (d100)

*Banks, shores, docks and shallows.*

| d100 | Encounter | CR | Number appearing | Source |
|---|---|---|---|---|
| 01–08 | Elf, Aquatic | 0.5 | Solitary (see source book) | Monster Manual I |
| 09–17 | Zombie, Brine | 1 | Gang (2-4) or crew (6-11) | Tome of Horrors Revised (Necromancer Games |
| 18–25 | Storm Elemental, Small | 2 | Solitary (see source book) | Monster Manual III |
| 26–33 | Elemental, Earth | 3 | Solitary (see source book) | Monster Manual I |
| 34–41 | Fire Bat | 3 | Solitary (see source book) | Monster Manual II |
| 42–48 | Sea Cat | 4 | Solitary (see source book) | Monster Manual I |
| 49–54 | Belker | 6 | Solitary (see source book) | Monster Manual I |
| 55–60 | Ormyrr | 6 | Solitary (see source book) | Monster Manual II |
| 61–66 | Breathdrinker | 7 | Solitary (see source book) | Monster Manual II |
| 67–72 | Mudmaw | 7 | Solitary (see source book) | Monster Manual II |
| 73–77 | Legendary Snake | 8 | Solitary (see source book) | Monster Manual II |
| 78–81 | Marraenoloth | 10 | Solitary (see source book) | Monster Manual II |
| 82–85 | Air Weird | 12 | Solitary (see source book) | Monster Manual II |
| 86–89 | Octopus Tree | 12 | Solitary (see source book) | Fiend Folio |
| 90–92 | Cinder Swarm | 13 | Solitary (see source book) | Monster Manual III |
| 93–96 | Skeleton Warrior | 14 | Solitary.                                          and is used by permission. | Tome of Horrors Revised (Necromancer Games |
| 97–98 | Waterveiled Assassin | 15 | Solitary (see source book) | Monster Manual IV |
| 99–100 | Teratomorph | 16 | Solitary (see source book) | Monster Manual II |

APOC notes, stat blocks and pictures per entry are in encounters.json / the roller / STATBLOCKS.md (undead house rules, enclave-demon note, named-encounter flags).

## River/Lake/Coast — Open Water (d100)

*In the water itself.*

| d100 | Encounter | CR | Number appearing | Source |
|---|---|---|---|---|
| 01–07 | Cullenrock Barnacle | 0.5 | Solitary (see source book) | Monsternomicon Vol. 2 |
| 08–15 | Bog Trog | 1 | Solitary (see source book) | Monsternomicon Vol. 1 |
| 16–23 | Octopus | 1 | Solitary (see source book) | Monster Manual I |
| 24–31 | Squid | 1 | Solitary (see source book) | Monster Manual I |
| 32–38 | Sahuagin | 2 | Solitary (see source book) | Monster Manual I |
| 39–45 | Dinosaur, Cryptoclidus | 3 | Solitary (see source book) | Monster Manual II |
| 46–52 | Mummy of the Deep | 4 | Solitary or gang (2-4) | Tome of Horrors Revised (Necromancer Games |
| 53–59 | Vine Horror | 4 | Solitary (see source book) | Fiend Folio |
| 60–65 | Troll, Scrag | 5 | Solitary (see source book) | Monster Manual I |
| 66–71 | Kopru | 6 | Solitary (see source book) | Monster Manual II |
| 72–76 | Boatman | 7 | Solitary (see source book) | Monsternomicon Vol. 1 |
| 77–81 | Naga, Water | 7 | Solitary (see source book) | Monster Manual I |
| 82–86 | Drowned | 9 | Solitary, pair, or crew (3–12) | Monster Manual III |
| 87–91 | Squid, Giant | 9 | Solitary (see source book) | Monster Manual I |
| 92–95 | Megalodon | 11 | Solitary (see source book) | Monster Manual II |
| 96–97 | Elder Spawn of Juiblex | 14 | Solitary (see source book) | Monster Manual V |
| 98 | Aboleth Mage | 17 | Solitary (see source book) | Monster Manual I |
| 99–100 | Ocean Strider | 18 | Solitary (see source book) | Monster Manual II |

APOC notes, stat blocks and pictures per entry are in encounters.json / the roller / STATBLOCKS.md (undead house rules, enclave-demon note, named-encounter flags).
