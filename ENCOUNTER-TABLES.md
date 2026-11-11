# APOC Survival — Random Encounter Tables (d1000)

Built 2026-11-09 from canonical sources only: Demons roster (361 in file — the build order said 355; file truth 361 governs), Undead roster (346), Sentient Constructs roster (92), NPCs cast (150), APOC-VTT monster registry (1,486, Monsternomicon I at 2002-original values).

**Stat blocks & pictures:** every creature on these tables carries its full stat block and its picture in the roller (`index.html`) and in [STATBLOCKS.md](STATBLOCKS.md) / `encounters.json` — roll on the page to see the rolled creature's block and picture. This document stays the quick-reference table set.

## The Badlands — the world outside the cities (Shaun, canon correction 2026-11-11)
**The Badlands is everywhere the city is not.** It is all the untamed world outside the held cities — everywhere the demons crossed the landscape and blighted it as they travelled through. Every table in this set except the Bastion's own describes a place WITHIN the Badlands: its plains, forests, hills, mountains, deserts, swamps, waters, ruins, roads, and deep places are regions of the Badlands, not lands beside it. The **Open Wastes** table is the general table for the open blighted country of the Badlands, between and beyond those regions. Only the Bastion tables are inside a held city.

## One to a thousand — the d1000 scale (Shaun, 2026-11-11)
With every landscape of the Badlands on the tables, the rolls now run **1 to 1000** instead of 1 to 100 (Shaun: "maybe you should make it one to a thousand"), so all the different landscapes and their populations ride at their proper weight on the finer scale. The conversion is exact scaling, nothing more: every band was multiplied by ten (a band printed 46–50 is now 451–500; the old roll of 100 is now 991–1000), so **every creature keeps precisely the share of its table it always had** — nothing was padded, added, removed, or re-weighted, and Saint James still waits on the last 1% of his three tables. All nineteen tables run on the one scale, the Bastion's included, so the roller throws a single die throughout; the Chart Generator builds d1000 charts to match. The Badlands layer rides over the new scale unchanged — it keys on landscapes, not numbers.

## The Badlands layer in the roller — an on/off additive (Shaun, 2026-11-11)
The roller carries a **Badlands layer** toggle. It is not a table and not a landscape: it is the Badlands itself, layered over whichever landscape is rolled. **Off** (the default): landscape rolls stand as printed. **On**: the party is out in the Badlands, and every landscape result is produced as a Badlands encounter — the result carries the layer's canon conditions for that country (on the surface: one grey sky, Fog of Life, hatestorm country, the permanent war, the unclaimed walking it; below ground: no Fog of Life, but the blight soaked deep and the war runs through the dark), and the land's own living creatures in that defiled country may be twisted — warped in body, wrong in habit, no demon and no servant of demons — under Shaun's Twisted template where the DM calls it. The layer never reaches the Bastion tables: the city is the exception, held behind its walls and mythal. Table contents and math are unchanged either way; the roll history records when the layer was on.

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

## The Steampunk overlay — the second additive (Shaun, 2026-11-11)
Beside the Badlands layer sits a second toggle: the **Steampunk overlay**. The two are independent and combine in any state — Badlands on or off, Steampunk on or off — because they layer different things: the Badlands layer is the world's condition; the Steampunk overlay is the age's technology. Steampunk belongs everywhere in this age, so the overlay reaches **every** table, the Bastion's included — the city runs on steam (cannoneer towers, the walking constructs, steamcraft in the workshops), and out in the landscapes the enclaves' war-machines crawl, constructs work fields and ruins, and steamcraft gear turns up in ready hands; elemental workings, in the city or out of it, are fed through steampunk apparatus. When a roll itself produces a construct, the overlay names it the element made manifest: a machine of the age, met in the field. Like the layer, it changes no table contents and no math; the roll history marks it [Steampunk], and the two marks stack when both are on.

**The rewrite (Shaun's spec, 2026-11-11):** with the overlay ON, the rolled creature itself is presented rewritten as a steampunk version — **Steamwork [creature]** — its description and build reworked in the idiom from its own published lines (frame and size, how it moves, its natural weapons rebuilt in steel), shown as the version in play over a published record that stays verbatim and untouched below it; the overlay reworks the form, not the numbers, and OFF the creature stands exactly as published. Two classes are not rewritten: **constructs** (the Warforged among them) are already machines of the age and stand as published; **persons** — the NPC cast, Saint James — are not rebuilt either, for rebuilding a person into a machine is precisely what makes a War-Torn: they are presented kitted in the idiom (steamcraft gear, apparatus, firearms) and themselves unchanged. Both collisions are flagged for Shaun in COVERAGE.md rather than guessed past.

## Area-type layering & folded combinations
- Open country: use the region's table as-is; for the open blighted wastes between regions, use Open Wastes, the Badlands' general table.
- Road/trail: roll on Road/Trail generic, or the terrain table — road travellers are drawn from humanoid/giant/animal stock, so a separate per-terrain road matrix is FOLDED into the one generic Road/Trail table (reason: roads cross terrains; duplicating 11 road tables would repeat the same traveller pool).
- Dungeon/interior: Underground — Dungeon/Interior table (folded from Underground+Ruins pools, reason: built below-ground interiors share both pools).
- City streets/districts: Bastion Streets and Bastion Districts/Interior are separate tables (ward-screened).
- Ruins interior: separate Ruins Interior table.
- River/Lake/Coast is split into Shoreline and Open Water sub-tables (aquatic creatures only in Open Water).
- Per-terrain city and per-terrain dungeon matrices are FOLDED as above — the Bastion is APOC's one great city table-set, and dungeons are terrain-independent interiors. Every named terrain and area type is covered.

## Open Wastes (d1000)

*The general table for the open blighted wastes of the Badlands — the untamed world outside the held cities. The Badlands is not one landscape among the others: every table in this set but the Bastion's is a place within it, and this is its general table for the open country between regions. Dragons haven't been seen in a thousand years — a legend under the Council of Wyrms. Flavor only: no roll ever produces a dragon. Fog of Life lies on this surface terrain.*

| d1000 | Encounter | CR | Number appearing | Source |
|---|---|---|---|---|
| 01–70 | Fiendish Symbiont, Fiendish Familiar | 0.125 | Solitary (see source book) | Fiend Folio |
| 71–130 | Nerra, Varoot | 1 | Solitary (see source book) | Fiend Folio |
| 131–200 | Desiccator | 2 | Solitary or gang (2–5) | Libris Mortis |
| 201–270 | Vasuthant | 2 | Solitary | Monster Manual III |
| 271–330 | Tin Golem | 3 | Solitary, pair, or gang (3–4) | Dragon Magazine / Constructs roster (web-sourced entry) |
| 331–390 | Rutterkin | 3 | Solitary (see source book) | Fiendish Codex I, Book of Vile Darkness |
| 391–450 | Flameskull | 4 | Solitary or company (3–12) | Lost Empires of Faerûn |
| 451–500 | Gravetouched Ghoul Harpy | 5 | Solitary (see source book) | Libris Mortis |
| 501–550 | Karina | 5 | Solitary, gang (2-6) | Encyclopedia of Demons & Devils Vol. 1 |
| 551–600 | Bloodmote Cloud | 6 | Solitary, cloud (2–4 swarms), or infestation (7–12 swarms) | Libris Mortis |
| 601–650 | Lesser Spawn of Juiblex | 6 | Solitary (see source book) | Monster Manual V |
| 651–700 | Cinder Ghoul | 7 | Solitary, gang (2–5), or mob (6–11) | Tome of Horrors II |
| 701–740 | Mohrg | 8 | Solitary, gang (2–4), or mob (2–4 plus 5–10 zombies) | Monster Manual I |
| 741–790 | Shadow Demon | 8 | Solitary | Book of Vile Darkness |
| 791–830 | Kappa | 9 | Solitary | Encyclopedia of Demons & Devils Vol. 1 |
| 831–860 | Cerebrilith | 10 | Solitary or gang (2–4) | Expanded Psionics Handbook |
| 861–890 | Demon, Kastighur | 11 | Solitary or pair (Fox Hunt, EL 16: two kastighurs — MM4 p.43; kastighurs typically serve more intelligent and powerful demons as hunters and jailers) | Monster Manual IV |
| 891–920 | Infernal Soul Stalker | 12 | Solitary (see source book) | Monsternomicon Vol. 1 |
| 921–950 | Blood Fiend | 14 | Solitary, pair, or gang (3–5) | Fiend Folio |
| 951–970 | Dream Vestige | 16 | Solitary | Libris Mortis |
| 971–980 | Lifespark Construct | 18 | Solitary | Advanced Bestiary |
| 981–990 | Isitwalangcengce | 21 | Solitary | Encyclopedia of Demons & Devils Vol. 1 |
| 991–1000 | Saint James | 15 | 1 (plus sentient telepathic dire crocodile partner and flying tavern ST-JAMES — Booze and Magic; crew of unseen servants / invisible stalkers) | Shaun canon / NPCs #150 — Saint James file |

APOC notes, stat blocks and pictures per entry are in encounters.json / the roller / STATBLOCKS.md (undead house rules, enclave-demon note, named-encounter flags).

## Plains (d1000)

*Dragons haven't been seen in a thousand years — a legend under the Council of Wyrms. Flavor only: no roll ever produces a dragon. Fog of Life lies on this surface terrain.*

| d1000 | Encounter | CR | Number appearing | Source |
|---|---|---|---|---|
| 01–60 | Toad | 0.1 | Solitary (see source book) | Monster Manual I |
| 61–120 | Kenku | 0.5 | Solitary (see source book) | Monster Manual III |
| 121–180 | Raggamoffyn | 1 | Solitary, pair, or gang (3–6) | Monster Manual II |
| 181–250 | Desiccator | 2 | Solitary or gang (2–5) | Libris Mortis |
| 251–310 | Swarm, Bat | 2 | Solitary, cloud (2–4 swarms), or infestation (7–12 swarms) | Monster Manual I |
| 311–360 | Dinosaur, Deinonychus | 3 | Solitary (see source book) | Monster Manual I |
| 361–420 | Carrionette | 3 | Solitary or pack (2d4) | Dragon Magazine #339 |
| 421–470 | Crocodile, Giant | 4 | Solitary (see source book) | Monster Manual I |
| 471–520 | Schir | 4 | Solitary or pack (3–8) | Book of Fiends |
| 521–570 | Deadly Sin, Gluttony | 5 | Solitary | Encyclopedia of Demons & Devils Vol. 1 |
| 571–630 | Mummy | 5 | Solitary, warden squad (2–4), or guardian detail (6–10) | Monster Manual I |
| 631–670 | Caryatid Column | 6 | Solitary, corbel (2), or colonnade (4–24) | Fiend Folio |
| 671–710 | Tainted Minion | 6 | Solitary or gang (2–5) | Heroes of Horror |
| 711–760 | Groaning Spirit | 7 | Solitary                                        Groaning spirits are the bane of other undead, and | Tome of Horrors Revised (Necromancer Games |
| 761–810 | Black Troll | 8 | Solitary | Monsternomicon Vol. I |
| 811–850 | Shetan | 8 | Solitary, gang (2-6) | Encyclopedia of Demons & Devils Vol. 1 |
| 851–880 | Mastodon | 9 | Solitary (see source book) | Monster Manual III |
| 881–910 | Githyanki Captain | 10 | Solitary (see source book) | Monster Manual IV |
| 911–940 | The Lord of Blades | 12 | Solitary (see source book) | Five Nations |
| 941–970 | Boneyard | 14 | Solitary | Libris Mortis |
| 971–980 | Hellfire Golem | 17 | Solitary | Fiend Folio |
| 981–1000 | Crawling Head | 20 | Solitary | Fiend Folio |

APOC notes, stat blocks and pictures per entry are in encounters.json / the roller / STATBLOCKS.md (undead house rules, enclave-demon note, named-encounter flags).

## Forest (d1000)

*Dragons haven't been seen in a thousand years — a legend under the Council of Wyrms. Flavor only: no roll ever produces a dragon. Fog of Life lies on this surface terrain.*

| d1000 | Encounter | CR | Number appearing | Source |
|---|---|---|---|---|
| 01–50 | Toad | 0.1 | Solitary (see source book) | Monster Manual I |
| 51–110 | Eagle | 0.5 | Solitary (see source book) | Monster Manual I |
| 111–170 | Trollkin | 0.5 | Solitary (see source book) | Monsternomicon Vol. 1 |
| 171–230 | Mule | 1 | Solitary (see source book) | Monster Manual I |
| 231–290 | Abyssal Skulker | 2 | Solitary, pair, or gang (3–5) | Monster Manual II |
| 291–340 | Greenspawn Leaper | 2 | Solitary (see source book) | Monster Manual IV |
| 341–400 | Sythyss | 2 | Solitary or gang (2–5) | Monsternomicon Vol. I |
| 401–450 | Devil Rat Swarm | 3 | Solitary (see source book) | Monsternomicon Vol. 2 |
| 451–500 | Owl, Giant | 3 | Solitary (see source book) | Monster Manual I |
| 501–550 | Bluespawn Ambusher | 4 | Solitary (see source book) | Monster Manual IV |
| 551–600 | Myconid Guard | 4 | Solitary (see source book) | Monster Manual II |
| 601–650 | Avvite | 5 | Solitary or pack (1 avvite dire wolf and 4–7 followers) | Anger of Angels |
| 651–700 | Cadaver Lord | 5 | Solitary or troupe (cadaver lord plus 1–4 cadavers) | Tome of Horrors II |
| 701–740 | Dinosaur, Bloodstriker | 6 | Solitary (see source book) | Monster Manual III |
| 741–790 | Voidwraith | 6 | Solitary, pair, or gang (3–5) | Libris Mortis |
| 791–830 | Greenspawn Razorfiend | 7 | Solitary (see source book) | Monster Manual IV |
| 831–870 | Deadborn Vulture | 8 | Solitary (see source book) | Monster Manual V |
| 871–900 | Blackspawn Stalker | 9 | Solitary (see source book) | Monster Manual IV |
| 901–930 | Dire Elephant | 10 | Solitary (see source book) | Monster Manual II |
| 931–960 | Tatzylwurm, Black | 11 | Solitary (see source book) | Monsternomicon Vol. 2 |
| 961–990 | Riven | 13 | Solitary | Monsternomicon Vol. II |
| 991–1000 | Elite Demon War Mount | 16 | Solitary (see source book) | Monster Manual III |

APOC notes, stat blocks and pictures per entry are in encounters.json / the roller / STATBLOCKS.md (undead house rules, enclave-demon note, named-encounter flags).

## Hills (d1000)

*Dragons haven't been seen in a thousand years — a legend under the Council of Wyrms. Flavor only: no roll ever produces a dragon. Fog of Life lies on this surface terrain.*

| d1000 | Encounter | CR | Number appearing | Source |
|---|---|---|---|---|
| 01–50 | Kobold | 0.25 | Solitary (see source book) | Monster Manual I |
| 51–100 | Gnome, Forest | 0.5 | Solitary (see source book) | Monster Manual I |
| 101–180 | Bram Holt | 1 | Solitary | NPCs — ALL-150 (Shaun's cast) |
| 181–240 | Raiment | 1 | Solitary | Libris Mortis |
| 241–300 | Baneguard | 2 | Solitary, pair, or squad (3–10) | Lost Empires of Faerûn |
| 301–360 | Malachi Vane | 2 | Solitary | NPCs — ALL-150 (Shaun's cast) |
| 361–410 | Bile Thrall | 3 | Solitary or troop (6-10); often accompa- | Monsternomicon Vol. II |
| 411–460 | Hoar Spirit | 3 | Pack (2–5) or gang (6–11) | Tome of Horrors II |
| 461–510 | Skin Kite | 3 | Solitary, pair, or flock (5–8) | Libris Mortis |
| 511–560 | Draug | 4 | Solitary or crew (1 draug plus 6-11 brine | Tome of Horrors Revised (Necromancer Games |
| 561–600 | Orc Berserker | 4 | Solitary (see source book) | Monster Manual IV |
| 601–650 | Anvil-7 | 5 | Solitary | NPCs — ALL-150 (Shaun's cast) |
| 651–700 | Cadaver Lord | 5 | Solitary or troupe (cadaver lord plus 1–4 cadavers) | Tome of Horrors II |
| 701–750 | Darnoc | 6 | Solitary or gang (2-4) | Tome of Horrors Revised (Necromancer Games |
| 751–790 | Apparition | 7 | Solitary or gang (2-4)                                                              succeeds, the victim | Tome of Horrors Revised (Necromancer Games |
| 791–830 | Groaning Spirit | 7 | Solitary                                        Groaning spirits are the bane of other undead, and | Tome of Horrors Revised (Necromancer Games |
| 831–860 | Bladerager Troll | 8 | Solitary (see source book) | Monster Manual V |
| 861–900 | Scylla Flock | 8 | Solitary, flight (2–4), or colony (5–10) | Monsternomicon Vol. II |
| 901–930 | Aspect of Vecna | 10 | Solitary | Miniatures Handbook |
| 931–960 | Devourer | 11 | Solitary | Monster Manual I |
| 961–990 | Jarilith | 13 | Solitary, pair, or pride (6–10) | Monster Manual II |
| 991–1000 | Giant, Eldritch | 15 | Solitary | Monster Manual III |

APOC notes, stat blocks and pictures per entry are in encounters.json / the roller / STATBLOCKS.md (undead house rules, enclave-demon note, named-encounter flags).

## Mountains (d1000)

*Dragons haven't been seen in a thousand years — a legend under the Council of Wyrms. Flavor only: no roll ever produces a dragon. Fog of Life lies on this surface terrain.*

| d1000 | Encounter | CR | Number appearing | Source |
|---|---|---|---|---|
| 01–70 | Moonrat | 0.25 | Solitary (see source book) | Monster Manual II |
| 71–130 | Krenshar | 1 | Solitary (see source book) | Monster Manual I |
| 131–190 | Greenspawn Leaper | 2 | Solitary (see source book) | Monster Manual IV |
| 191–250 | Worg | 2 | Solitary (see source book) | Monster Manual I |
| 251–320 | Hoar Spirit | 3 | Pack (2–5) or gang (6–11) | Tome of Horrors II |
| 321–380 | Yuan-ti Pureblood | 3 | Solitary (see source book) | Monster Manual I |
| 381–430 | Owlbear | 4 | Solitary (see source book) | Monster Manual I |
| 431–480 | Cyclops | 5 | Solitary (see source book) | Monsternomicon Vol. 2 |
| 481–540 | Shaft Wight | 5 | Solitary or small band (2–6) | Monsternomicon Vol. I |
| 541–590 | Bluespawn Stormlizard | 6 | Solitary (see source book) | Monster Manual IV |
| 591–640 | Redspawn Arcaniss | 6 | Solitary (see source book) | Monster Manual IV |
| 641–680 | Chimera | 7 | Solitary (see source book) | Monster Manual I |
| 681–720 | Yuan-ti Abomination | 7 | Solitary (see source book) | Monster Manual I |
| 721–760 | Ken-Kuni | 8 | Solitary (see source book) | Monster Manual V |
| 761–800 | Bluespawn Burrower | 9 | Solitary (see source book) | Monster Manual IV |
| 801–840 | Rylkar Harridan | 9 | Solitary (see source book) | Monster Manual V |
| 841–870 | Ken-Li | 10 | Solitary (see source book) | Monster Manual V |
| 871–900 | Giant, Cloud | 11 | Solitary (see source book) | Monster Manual I |
| 901–930 | Brood Keeper Larva Swarm | 12 | Solitary (see source book) | Monster Manual III |
| 931–960 | Tatzylwurm, Pale | 12 | Solitary (see source book) | Monsternomicon Vol. 1 |
| 961–990 | Deathshrieker | 15 | Solitary | Monster Manual III |
| 991–1000 | Lucent Worm | 17 | Solitary (see source book) | Fiend Folio |

APOC notes, stat blocks and pictures per entry are in encounters.json / the roller / STATBLOCKS.md (undead house rules, enclave-demon note, named-encounter flags).

## Desert (d1000)

*Dragons haven't been seen in a thousand years — a legend under the Council of Wyrms. Flavor only: no roll ever produces a dragon. Fog of Life lies on this surface terrain.*

| d1000 | Encounter | CR | Number appearing | Source |
|---|---|---|---|---|
| 01–60 | Giant Fire Beetle | 0.333333 | Solitary (see source book) | Monster Manual I |
| 61–120 | Camel | 1 | Solitary (see source book) | Monster Manual I |
| 121–180 | Giant Bee | 1 | Solitary (see source book) | Monster Manual I |
| 181–240 | Moonwing | 1 | Solitary (see source book) | Monsternomicon Vol. 1 |
| 241–300 | Thri-Kreen | 1 | Solitary (see source book) | Monster Manual II |
| 301–350 | Giant Bombardier Beetle | 2 | Solitary (see source book) | Monster Manual I |
| 351–400 | Monstrous Centipede | 2 | Solitary (see source book) | Monster Manual I |
| 401–450 | Armand | 3 | Solitary (see source book) | Monster Manual III |
| 451–500 | Cataphract Beetle | 3 | Solitary (see source book) | Monsternomicon Vol. 2 |
| 501–550 | Giant Wasp | 3 | Solitary (see source book) | Monster Manual I, Monster Manual IV |
| 551–600 | Lolth-Touched Monstrous Hunting Spider | 3 | Solitary (see source book) | Monster Manual IV |
| 601–650 | Swarm, Locust | 3 | Solitary, cloud (2–4 swarms), or infestation (7–12 swarms) | Monster Manual I |
| 651–700 | Giant Stag Beetle | 4 | Solitary (see source book) | Monster Manual I, Monster Manual IV |
| 701–740 | Harssaf | 5 | Solitary (see source book) | Monster Manual III |
| 741–780 | Chelicera | 6 | Solitary (see source book) | Monster Manual III |
| 781–820 | Swarm, Locust, Rapture | 6 | Solitary, cloud (2–4 swarms), or infestation (7–12 swarms) | Fiend Folio |
| 821–860 | Swarm, Locust, Bloodfiend | 8 | Solitary, cloud (2–4 swarms), or infestation (7–12 swarms) | Fiend Folio |
| 861–890 | Ethon | 10 | Solitary (see source book) | Monsternomicon Vol. 2 |
| 891–930 | Sand Dervish | 10 | Solitary | Monsternomicon Vol. II |
| 931–970 | Crawling Apocalypse | 11 | Solitary | Sandstorm |
| 971–980 | Desert Hydra (5-headed) | 15 | Solitary (see source book) | Monsternomicon Vol. 2 |
| 981–1000 | Dry Lich | 18 | Solitary | Sandstorm |

APOC notes, stat blocks and pictures per entry are in encounters.json / the roller / STATBLOCKS.md (undead house rules, enclave-demon note, named-encounter flags).

## Swamp/Marsh (d1000)

*Dragons haven't been seen in a thousand years — a legend under the Council of Wyrms. Flavor only: no roll ever produces a dragon. Fog of Life lies on this surface terrain.*

| d1000 | Encounter | CR | Number appearing | Source |
|---|---|---|---|---|
| 01–60 | Raven | 0.166667 | Solitary (see source book) | Monster Manual I |
| 61–120 | Warforged | 0.5 | Solitary (see source book) | Monster Manual III |
| 121–180 | Shadar-Kai | 1 | Solitary (see source book) | Fiend Folio |
| 181–240 | Dire Maggot | 2 | Solitary (see source book) | Libris Mortis |
| 241–300 | Sickening Sleep | 2 | Solitary (see source book) | Monster Manual III |
| 301–360 | Boggle | 3 | Solitary (see source book) | Monster Manual II |
| 361–420 | Monstrous Scorpion | 3 | Solitary (see source book) | Monster Manual I |
| 421–470 | Arkamoi | 4 | Solitary (see source book) | Monster Manual V |
| 471–520 | Nagatha | 4 | Solitary (see source book) | Monster Manual IV |
| 521–570 | Kobold Wraith | 5 | Solitary, pair, gang (3–5), or pack (6–11). | Savage Species |
| 571–620 | Bog Mummy | 6 | Solitary, warden squad (2-4), or guard- | Tome of Horrors Revised (Necromancer Games |
| 621–670 | Catoblepas | 6 | Solitary (see source book) | Monster Manual II |
| 671–720 | Redspawn Arcaniss | 6 | Solitary (see source book) | Monster Manual IV |
| 721–760 | Darktentacles | 7 | Solitary (see source book) | Monster Manual II |
| 761–800 | Apparition | 7 | Solitary or gang (2-4)                                                              succeeds, the victim | Tome of Horrors Revised (Necromancer Games |
| 801–840 | Blackwing | 8 | Solitary (see source book) | Monster Manual V |
| 841–880 | Doru, Infectious Blasheme | 9 | Solitary (see source book) | Libris Mortis |
| 881–910 | Forest Haunt | 10 | Solitary (see source book) | Monster Manual V |
| 911–940 | Skindancer | 11 | Solitary (see source book) | Monster Manual III |
| 941–970 | Twilight Sisters | 12 | Solitary (see source book) | Monsternomicon Vol. 2 |
| 971–980 | Siege Beetle | 16 | Solitary (see source book) | Monster Manual V |
| 981–1000 | The Black Duke | 19 | Solitary (see source book) | Monster Manual V |

APOC notes, stat blocks and pictures per entry are in encounters.json / the roller / STATBLOCKS.md (undead house rules, enclave-demon note, named-encounter flags).

## River/Lake/Coast (d1000)

*Dragons haven't been seen in a thousand years — a legend under the Council of Wyrms. Flavor only: no roll ever produces a dragon. Fog of Life lies on this surface terrain.*

| d1000 | Encounter | CR | Number appearing | Source |
|---|---|---|---|---|
| 01–90 | Cullenrock Barnacle | 0.5 | Solitary (see source book) | Monsternomicon Vol. 2 |
| 91–150 | Bog Trog | 1 | Solitary (see source book) | Monsternomicon Vol. 1 |
| 151–210 | Selkie | 1 | Solitary (see source book) | Fiend Folio |
| 211–280 | Zombie, Brine | 1 | Gang (2-4) or crew (6-11) | Tome of Horrors Revised (Necromancer Games |
| 281–340 | Sahuagin, Malenti | 2 | Solitary (see source book) | Monster Manual I |
| 341–400 | Dinosaur, Cryptoclidus | 3 | Solitary (see source book) | Monster Manual II |
| 401–460 | Fire Bat | 3 | Solitary (see source book) | Monster Manual II |
| 461–510 | Gargoyle, Kapoacinth | 4 | Solitary (see source book) | Monster Manual I |
| 511–560 | Vine Horror | 4 | Solitary (see source book) | Fiend Folio |
| 561–610 | Troll, Scrag | 5 | Solitary (see source book) | Monster Manual I |
| 611–660 | Glaistig | 6 | Solitary (see source book) | Monster Manual III |
| 661–710 | Storm Elemental, Large | 6 | Solitary (see source book) | Monster Manual III |
| 711–750 | Chuul | 7 | Solitary (see source book) | Monster Manual I |
| 751–790 | Naga, Water | 7 | Solitary (see source book) | Monster Manual I |
| 791–830 | Octopus, Giant | 8 | Solitary (see source book) | Monster Manual I |
| 831–870 | Drowned | 9 | Solitary, pair, or crew (3–12) | Monster Manual III |
| 871–900 | Ruin Elemental | 10 | Solitary (see source book) | Monster Manual V |
| 901–930 | Earth Weird | 12 | Solitary (see source book) | Monster Manual II |
| 931–950 | Cinder Swarm | 13 | Solitary (see source book) | Monster Manual III |
| 951–970 | Cyclonic Ravager | 15 | Solitary (see source book) | Monster Manual IV |
| 971–980 | Aboleth Mage | 17 | Solitary (see source book) | Monster Manual I |
| 981–1000 | Ocean Strider | 18 | Solitary (see source book) | Monster Manual II |

APOC notes, stat blocks and pictures per entry are in encounters.json / the roller / STATBLOCKS.md (undead house rules, enclave-demon note, named-encounter flags).

## Underground (d1000)

*Dragons haven't been seen in a thousand years — a legend under the Council of Wyrms. Flavor only: no roll ever produces a dragon. No Fog of Life here.*

| d1000 | Encounter | CR | Number appearing | Source |
|---|---|---|---|---|
| 01–60 | Cerebral Symbiont, Mind Leech | 0.125 | Solitary (see source book) | Fiend Folio |
| 61–120 | Bram Holt | 1 | Solitary | NPCs — ALL-150 (Shaun's cast) |
| 121–180 | Vasha Rook | 1 | Solitary | NPCs — ALL-150 (Shaun's cast) |
| 181–240 | Lurking Strangler | 2 | Solitary (see source book) | Monster Manual III |
| 241–300 | Automaton Hammerer | 3 | Solitary (see source book) | Monster Manual II |
| 301–370 | Ghoul-Stirge | 3 | Solitary, gang (2-4), or flock (5-8) | Tome of Horrors Revised (Necromancer Games |
| 371–440 | Skulleton | 3 | Solitary | Tome of Horrors Revised (Necromancer Games |
| 441–490 | Gargoyle | 4 | Solitary (see source book) | Monster Manual I |
| 491–540 | Swarm, Centipede | 4 | Solitary, cloud (2–4 swarms), or infestation (7–12 swarms) | Monster Manual I |
| 541–590 | Howler Wasp Queen | 5 | Solitary (see source book) | Monster Manual IV |
| 591–640 | Beholder, Gauth | 6 | Solitary (see source book) | Monster Manual I |
| 641–690 | Mummy Administrator | 6 | Solitary (see source book) | Sandstorm |
| 691–730 | Dire Bear | 7 | Solitary (see source book) | Monster Manual I |
| 731–770 | Swordwraith | 7 | Solitary, company (2–8), or squadron (11–20 plus 1 leader of 6th–9th level) | Fiend Folio |
| 771–810 | Mindshredder Zenthal | 8 | Solitary (see source book) | Monster Manual III |
| 811–850 | Drowned | 9 | Solitary, pair, or crew (3–12) | Monster Manual III |
| 851–880 | Darkweaver | 10 | Solitary (see source book) | Fiend Folio |
| 881–920 | Grimweird | 11 | Solitary, pair, or clique (3–9) | Monster Manual III |
| 921–950 | Slaughterstone Eviscerator | 12 | Solitary (see source book) | Monster Manual III |
| 951–970 | Dolomite | 15 | Solitary (see source book) | Monsternomicon Vol. 1 |
| 971–980 | Ethergaunt, Black | 17 | Solitary (see source book) | Fiend Folio |
| 981–1000 | Brammin Ironroot | 19 | Solitary | NPCs — ALL-150 (Shaun's cast) |

APOC notes, stat blocks and pictures per entry are in encounters.json / the roller / STATBLOCKS.md (undead house rules, enclave-demon note, named-encounter flags).

## Ruins (d1000)

*Dragons haven't been seen in a thousand years — a legend under the Council of Wyrms. Flavor only: no roll ever produces a dragon. Fog of Life lies on this surface terrain.*

| d1000 | Encounter | CR | Number appearing | Source |
|---|---|---|---|---|
| 01–60 | Cerebral Symbiont, Mind Leech | 0.125 | Solitary (see source book) | Fiend Folio |
| 61–120 | Gnoll | 1 | Solitary (see source book) | Monster Manual I |
| 121–180 | Bugbear | 2 | Solitary (see source book) | Monster Manual I |
| 181–240 | Triton | 2 | Solitary (see source book) | Monster Manual I |
| 241–300 | Ettercap | 3 | Solitary (see source book) | Monster Manual I |
| 301–360 | Salamander | 3 | Solitary (see source book) | Monster Manual I |
| 361–430 | Flameskull | 4 | Solitary or company (3–12) | Lost Empires of Faerûn |
| 431–500 | Vampire Spawn | 4 | Solitary or pack (2–5) | Monster Manual I |
| 501–550 | Ghostly Sorcerer | 5 | Solitary (see source book) | Tome of Magic |
| 551–600 | Troll | 5 | Solitary (see source book) | Monster Manual I, Monsternomicon Vol. 1 |
| 601–650 | Hag, Annis | 6 | Solitary (see source book) | Monster Manual I |
| 651–690 | Chaos Beast | 7 | Solitary (see source book) | Monster Manual I |
| 691–750 | Spectral Troll | 7 | Solitary or gang (2–4) | Tome of Horrors Revised (Necromancer Games |
| 751–790 | Mob of Zombies | 8 | Solitary (see source book) | Exemplars of Evil |
| 791–830 | Eloko | 9 | Solitary | Encyclopedia of Demons & Devils Vol. 1 |
| 831–870 | Yunwi Djunsti | 9 | Solitary, 2-5 (gang) | Encyclopedia of Demons & Devils Vol. 1 |
| 871–900 | Yagnoloth | 10 | Solitary (see source book) | Monster Manual II |
| 901–930 | Abeil Queen | 12 | Solitary (see source book) | Monster Manual II |
| 931–950 | Sarkrith, Spelleater | 13 | Solitary (see source book) | Fiend Folio |
| 951–970 | Thoon Elder Brain | 15 | Solitary (see source book) | Monster Manual V |
| 971–980 | Vermin Lord | 17 | Solitary (see source book) | Monster Manual III |
| 981–990 | Aspect of Dispater | 21 | Solitary (see source book) | Fiendish Codex II |
| 991–1000 | Saint James | 15 | 1 (plus sentient telepathic dire crocodile partner and flying tavern ST-JAMES — Booze and Magic; crew of unseen servants / invisible stalkers) | Shaun canon / NPCs #150 — Saint James file |

APOC notes, stat blocks and pictures per entry are in encounters.json / the roller / STATBLOCKS.md (undead house rules, enclave-demon note, named-encounter flags).

## Bastion (d1000)

*Dragons haven't been seen in a thousand years — a legend under the Council of Wyrms. Flavor only: no roll ever produces a dragon. No Fog of Life here.*

| d1000 | Encounter | CR | Number appearing | Source |
|---|---|---|---|---|
| 01–70 | Hawk | 0.333333 | Solitary (see source book) | Monster Manual I |
| 71–140 | Bogun | 1 | Solitary (see source book) | Monster Manual II |
| 141–210 | Skorne | 1 | Solitary (see source book) | Monsternomicon Vol. 1 |
| 211–280 | Lumi | 2 | Solitary (see source book) | Monster Manual III |
| 281–340 | Clockwork Stallion | 3 | Solitary (see source book) | Monster Manual IV |
| 341–400 | Tin Golem | 3 | Solitary, pair, or gang (3–4) | Dragon Magazine #341 |
| 401–460 | Force Golem | 4 | Solitary (see source book) | Monster Manual V |
| 461–520 | Chain Golem | 5 | Solitary (see source book) | Monster Manual II |
| 521–580 | Incarnate Construct (sample) | 5 | Solitary (alone or with its spellcaster liberator) | Savage Species |
| 581–630 | Caryatid Column | 6 | Solitary, corbel (2), or colonnade (4–24) | Fiend Folio |
| 631–680 | Scyther of Thoon | 6 | Solitary (see source book) | Monster Manual V |
| 681–730 | Shrapnyl | 7 | Solitary (see source book) | Monster Manual II |
| 731–770 | Iron Maiden | 8 | Solitary | Monsternomicon Vol. 1 |
| 771–810 | Clockwork Horror, Adamantine | 9 | Solitary (see source book) | Monster Manual II |
| 811–850 | Bronze Serpent | 10 | Solitary (see source book) | Monster Manual II |
| 851–880 | Alchemical Golem | 11 | Solitary (see source book) | Monster Manual III |
| 881–910 | Wicker Man | 11 | Solitary (see source book) | Fiend Folio |
| 911–940 | Slaughterstone Eviscerator | 12 | Solitary (see source book) | Monster Manual III |
| 941–960 | Inevitable, Marut | 15 | Solitary | Monster Manual I |
| 961–970 | Zodar | 16 | Solitary | Fiend Folio |
| 971–980 | Blackstone Gigant | 18 | Solitary | Fiend Folio |
| 981–1000 | Hellfire Engine | 19 | Solitary (see source book) | Fiendish Codex II |

APOC notes, stat blocks and pictures per entry are in encounters.json / the roller / STATBLOCKS.md (undead house rules, enclave-demon note, named-encounter flags).

## Road/Trail (generic — any terrain) (d1000)

*Use with the terrain table of the terrain crossed; travellers, patrols, merchants and predators of the road.*

| d1000 | Encounter | CR | Number appearing | Source |
|---|---|---|---|---|
| 01–80 | Toad | 0.1 | Solitary (see source book) | Monster Manual I |
| 81–150 | Elf, Gray | 0.5 | Solitary (see source book) | Monster Manual I |
| 151–220 | Bram Holt | 1 | Solitary | NPCs — ALL-150 (Shaun's cast) |
| 221–280 | Orc Battle Priest | 1 | Solitary (see source book) | Monster Manual IV |
| 281–340 | Boar | 2 | Solitary (see source book) | Monster Manual I |
| 341–400 | Leopard | 2 | Solitary (see source book) | Monster Manual I |
| 401–460 | Armand | 3 | Solitary (see source book) | Monster Manual III |
| 461–520 | Owl, Giant | 3 | Solitary (see source book) | Monster Manual I |
| 521–570 | Fiendish Cleric of Yeenoghu | 4 | Solitary (see source book) | Monster Manual IV |
| 571–620 | Tharn Bloodtrackers | 4 | Solitary (see source book) | Monsternomicon Vol. 2 |
| 621–670 | Harrier | 5 | Solitary (see source book) | Monsternomicon Vol. 2 |
| 671–720 | Blood Ape | 6 | Solitary (see source book) | Monster Manual II |
| 721–770 | Sea Tiger | 6 | Solitary (see source book) | Monster Manual III |
| 771–810 | Greenspawn Sneak Raid Leader | 7 | Solitary (see source book) | Monster Manual IV |
| 811–850 | Gravorg | 8 | Solitary (see source book) | Monster Manual II |
| 851–890 | Dinosaur, Triceratops | 9 | Solitary (see source book) | Monster Manual I |
| 891–930 | Yrthak | 9 | Solitary (see source book) | Monster Manual I |
| 931–960 | Giant, Cloud | 11 | Solitary (see source book) | Monster Manual I |
| 961–990 | Roper | 12 | Solitary (see source book) | Monster Manual I |
| 991–1000 | Giant, Death | 16 | Solitary, dread (2–4 swarms), or horror (5–8 swarms) | Monster Manual III |

APOC notes, stat blocks and pictures per entry are in encounters.json / the roller / STATBLOCKS.md (undead house rules, enclave-demon note, named-encounter flags).

## Bastion Streets (d1000)

*Inside the Melairshield: Watch patrols (inward), Guard (outward at gates/walls), citizens, consortium people, Warforged, War-Torn, constructs, vermin, NPCs. Demons, undead, dragons and flyers are barred by the ward.*

| d1000 | Encounter | CR | Number appearing | Source |
|---|---|---|---|---|
| 01–90 | Hawk | 0.333333 | Solitary (see source book) | Monster Manual I |
| 91–170 | Clockroach | 1 | Solitary (see source book) | Monster Manual IV |
| 171–240 | Animated Object | 2 | Solitary (see source book) | Monster Manual I |
| 241–310 | Automaton Hammerer | 3 | Solitary (see source book) | Monster Manual II |
| 311–380 | Maug | 3 | Solitary, squad (4–7), warband (2–4 maugs plus 4–9 hobgoblins), or company (10–40 maugs plus 1 sergeant of 1st or 2nd level per 5 maugs, 2–4 lieutenants of 3rd–6th level, 1 leader of 7th–10th level, and 20–50 hobgoblins) | Fiend Folio |
| 381–440 | Clockwork Horror | 4 | Pair or component (3–8) | Monster Manual II |
| 441–500 | Mimic | 4 | Solitary (see source book) | Monster Manual I |
| 501–560 | Nightmare | 5 | Solitary (see source book) | Monster Manual I |
| 561–620 | Caryatid Column | 6 | Solitary, corbel (2), or colonnade (4–24) | Fiend Folio |
| 621–680 | Mechagargoyle | 6 | Solitary or band (2–5) | Monsternomicon Vol. 1 |
| 681–730 | Shrapnyl | 7 | Solitary (see source book) | Monster Manual II |
| 731–780 | Mind Flayer | 8 | Solitary (see source book) | Monster Manual I |
| 781–820 | Inevitable, Zelekhut | 9 | Solitary | Monster Manual I |
| 821–860 | Golem, Brass | 10 | Solitary (see source book) | Monster Manual II |
| 861–900 | Golem, Stone | 11 | Solitary (see source book) | Monster Manual I |
| 901–930 | Cadaver Collector | 12 | Solitary, pair, or squad (3–5) | Monster Manual III |
| 931–950 | Greater Shadesteel Golem | 14 | Solitary (see source book) | Monster Manual III |
| 951–970 | Woldwrath | 16 | Solitary (see source book) | Monsternomicon Vol. 2 |
| 971–980 | Merchurion | 17 | Solitary (see source book) | Fiend Folio |
| 981–1000 | Scouring Slinger | 18 | Solitary (see source book) | Monster Manual V |

APOC notes, stat blocks and pictures per entry are in encounters.json / the roller / STATBLOCKS.md (undead house rules, enclave-demon note, named-encounter flags).

## Bastion Districts / Interior (d1000)

*Interiors, consortium halls, tenements, markets. Ward-barred creatures do not appear; a barred creature is never rolled here.*

| d1000 | Encounter | CR | Number appearing | Source |
|---|---|---|---|---|
| 01–90 | Hawk | 0.333333 | Solitary (see source book) | Monster Manual I |
| 91–170 | Farrow | 1 | Solitary (see source book) | Monsternomicon Vol. 1 |
| 171–250 | Dread Guard | 2 | Solitary (see source book) | Monster Manual II |
| 251–330 | Clockwork Mender Swarm | 3 | Solitary (see source book) | Monster Manual IV |
| 331–410 | Tin Golem | 3 | Solitary, pair, or gang (3–4) | Dragon Magazine #341 |
| 411–480 | Gargoyle | 4 | Solitary (see source book) | Monster Manual I |
| 481–550 | Guttersnipe | 5 | Solitary (see source book) | Monster Manual II |
| 551–620 | Stormcloud of Thoon | 5 | Solitary (see source book) | Monster Manual V |
| 621–680 | Mechagargoyle | 6 | Solitary or band (2–5) | Monsternomicon Vol. 1 |
| 681–740 | Shrapnyl | 7 | Solitary (see source book) | Monster Manual II |
| 741–790 | Rip Cutter | 8 | Solitary (see source book) | Monsternomicon Vol. 1 |
| 791–840 | Rogue Eidolon | 9 | Solitary (see source book) | Monster Manual II |
| 841–880 | Runic Guardian | 10 | Solitary (see source book) | Monster Manual II |
| 881–920 | Shadesteel Golem | 11 | Solitary (see source book) | Monster Manual III |
| 921–950 | Golem, Iron | 13 | Solitary (see source book) | Monster Manual I |
| 951–970 | Thoon Elder Brain | 15 | Solitary (see source book) | Monster Manual V |
| 971–980 | Inevitable, Quarut | 17 | Solitary | Fiend Folio |
| 981–1000 | Prismatic Golem | 18 | Solitary (see source book) | Monster Manual III |

APOC notes, stat blocks and pictures per entry are in encounters.json / the roller / STATBLOCKS.md (undead house rules, enclave-demon note, named-encounter flags).

## Underground — Deep Dark (d1000)

*Dragons haven't been seen in a thousand years — a legend under the Council of Wyrms. Flavor only: no roll ever produces a dragon. The deep dark: no Fog of Life underground.*

| d1000 | Encounter | CR | Number appearing | Source |
|---|---|---|---|---|
| 01–70 | Mohrg | 8 | Solitary, gang (2–4), or mob (2–4 plus 5–10 zombies) | Monster Manual I |
| 71–150 | Bodak | 8 | Solitary or gang (2–4) | Monster Manual I |
| 151–240 | Shaft Wight | 5 | Solitary or small band (2–6) | Monsternomicon Vol. I |
| 241–330 | Slaughter Wight | 8 | Solitary, gang (2–4), or death squad (5–10) | Libris Mortis |
| 331–390 | Clockwork Horror, Adamantine | 9 | Solitary (see source book) | Monster Manual II |
| 391–470 | Pistol Wraith | 9 | Solitary | Monsternomicon Vol. I |
| 471–530 | Brain Golem | 10 | Solitary | Fiend Folio |
| 531–590 | Leechwalker | 10 | Solitary (see source book) | Monster Manual II |
| 591–660 | Atropal Scion | 11 | Solitary | Libris Mortis |
| 661–710 | Mud Golem | 11 | Solitary (see source book) | Monster Manual III |
| 711–760 | Cadaver Collector | 12 | Solitary, pair, or squad (3–5) | Monster Manual III |
| 761–800 | Death Centaur (Bone Golem) | 13 | Solitary (unique) | Constructs: It Is Alive |
| 801–840 | Ten-Headed Terror | 13 | Solitary (see source book) | Monster Manual III |
| 841–870 | Sample 15th-Level NPC Artificer (Warforged) | 15 | Solitary (see source book) | Sharn: City of Towers |
| 871–900 | Windghost | 15 | Solitary (see source book) | Monster Manual II |
| 901–920 | Zodar | 16 | Solitary | Fiend Folio |
| 921–960 | Marilith | 17 | Solitary or pair | Monster Manual I |
| 961–970 | Golem, Demonflesh | 18 | Solitary | Fiend Folio |
| 971–980 | Famine Spirit | 19 | Solitary, pair, brood (3–5), or band (2–5 plus 2–8 ghasts and 4–16 ghouls) | Monster Manual II |
| 981–1000 | Titan | 21 | Solitary (see source book) | Monster Manual I |

APOC notes, stat blocks and pictures per entry are in encounters.json / the roller / STATBLOCKS.md (undead house rules, enclave-demon note, named-encounter flags).

## Underground — Dungeon / Interior (d1000)

*Built interiors below ground; no Fog of Life.*

| d1000 | Encounter | CR | Number appearing | Source |
|---|---|---|---|---|
| 01–80 | Cerebral Symbiont, Mind Leech | 0.125 | Solitary (see source book) | Fiend Folio |
| 81–150 | Giant Bee | 1 | Solitary (see source book) | Monster Manual I |
| 151–220 | Cadaver | 2 | Solitary or gang (2–5) | Tome of Horrors II |
| 221–290 | Zombie, Yellow Musk | 2 | Solitary or patch (2–5 yellow musk | Tome of Horrors Revised (Necromancer Games |
| 291–360 | Gadacro | 3 | Clutch (2–6), or murder (7–12) (per Sample Encounter, MM5 p.27) | Monster Manual V |
| 361–420 | Spectral Steed | 3 | Solitary or herd (2–12) | Ghostwalk |
| 421–490 | Haunt | 4 | Solitary | Tome of Horrors Revised (Necromancer Games |
| 491–550 | Avvite | 5 | Solitary or pack (1 avvite dire wolf and 4–7 followers) | Anger of Angels |
| 551–610 | Mummy | 5 | Solitary, warden squad (2–4), or guardian detail (6–10) | Monster Manual I |
| 611–660 | Curst | 6 | Solitary | Lost Empires of Faerûn |
| 661–710 | Yugoloth, Mezzoloth | 6 | Solitary (see source book) | Monster Manual III |
| 711–760 | Orc Plague Speaker | 7 | Solitary (see source book) | Monster Manual IV |
| 761–800 | Gorgon | 8 | Solitary (see source book) | Monster Manual I |
| 801–840 | Demon, Zovvut | 9 | Solitary or squad (1 plus 2–4 wights) | Monster Manual II |
| 841–880 | Azi-Dahaka | 10 | Solitary | Encyclopedia of Demons & Devils Vol. 1 |
| 881–920 | Derek Windsfire | 11 | Solitary | NPCs — ALL-150 (Shaun's cast) |
| 921–950 | Ooze, Elder Black Pudding | 12 | Solitary                                        to move over the opponents, affecting as many as it can | Monster Manual I |
| 951–970 | Ammit | 15 | Solitary | Encyclopedia of Demons & Devils Vol. 1 |
| 971–980 | Ethergaunt, Black | 17 | Solitary (see source book) | Fiend Folio |
| 981–1000 | Ragewind | 19 | Solitary, pair, or cluster (3–5) | Monster Manual II |

APOC notes, stat blocks and pictures per entry are in encounters.json / the roller / STATBLOCKS.md (undead house rules, enclave-demon note, named-encounter flags).

## Ruins Interior (d1000)

*Inside ruined structures on the surface; Fog of Life outside, thinner within.*

| d1000 | Encounter | CR | Number appearing | Source |
|---|---|---|---|---|
| 01–70 | Cerebral Symbiont, Mind Leech | 0.125 | Solitary (see source book) | Fiend Folio |
| 71–140 | Kaorti | 1 | Solitary (see source book) | Fiend Folio |
| 141–210 | Desiccator | 2 | Solitary or gang (2–5) | Libris Mortis |
| 211–280 | Gibborite | 3 | Solitary or squadron (one gibborite with 3d6 humanoid barbarians, fighters, or warriors of 1st to 3rd level) | Anger of Angels |
| 281–340 | Lion | 3 | Solitary (see source book) | Monster Manual I |
| 341–400 | Vampire Spawn | 4 | Solitary or pack (2–5) | Monster Manual I |
| 401–470 | Painspeaker | 4 | Solitary or cabal (2–6) | Tome of Magic |
| 471–530 | Deadly Sin, Envy | 5 | Solitary | Encyclopedia of Demons & Devils Vol. 1 |
| 531–600 | Selune-Marra Vael | 5 | Solitary | NPCs — ALL-150 (Shaun's cast) |
| 601–650 | Gear Wyrm | 6 | Solitary (see source book) | Monsternomicon Vol. 1 |
| 651–700 | Chaos Beast | 7 | Solitary (see source book) | Monster Manual I |
| 701–750 | Susurrus | 7 | Solitary (see source book) | Monster Manual III |
| 751–790 | Pyre Troll | 8 | Solitary (see source book) | Monsternomicon Vol. 2 |
| 791–830 | Infernal, Quelvitar | 9 | Solitary (see source book) | Monsternomicon Vol. 2 |
| 831–880 | Draudnu | 10 | Rarely encountered in groups of more than four members (A Hard Place, EL 12: a pack of three draudnus — MM5 p.25) | Monster Manual V |
| 881–920 | Kastighur | 11 | Solitary or pair (Fox Hunt, EL 16: two kastighurs — MM4 p.43; kastighurs typically serve more intelligent and powerful demons as hunters and jailers) | Monster Manual IV |
| 921–950 | Death Centaur (Bone Golem) | 13 | Solitary (unique) | Constructs: It Is Alive |
| 951–970 | Giant Psurlon | 15 | Solitary (see source book) | Monster Manual II |
| 971–980 | Inevitable, Quarut | 17 | Solitary | Fiend Folio |
| 981–990 | Kumbhakarna | 20 | Unique | Encyclopedia of Demons & Devils Vol. 1 |
| 991–1000 | Saint James | 15 | 1 (plus sentient telepathic dire crocodile partner and flying tavern ST-JAMES — Booze and Magic; crew of unseen servants / invisible stalkers) | Shaun canon / NPCs #150 — Saint James file |

APOC notes, stat blocks and pictures per entry are in encounters.json / the roller / STATBLOCKS.md (undead house rules, enclave-demon note, named-encounter flags).

## River/Lake/Coast — Shoreline (d1000)

*Banks, shores, docks and shallows.*

| d1000 | Encounter | CR | Number appearing | Source |
|---|---|---|---|---|
| 01–80 | Elf, Aquatic | 0.5 | Solitary (see source book) | Monster Manual I |
| 81–170 | Zombie, Brine | 1 | Gang (2-4) or crew (6-11) | Tome of Horrors Revised (Necromancer Games |
| 171–250 | Storm Elemental, Small | 2 | Solitary (see source book) | Monster Manual III |
| 251–330 | Elemental, Earth | 3 | Solitary (see source book) | Monster Manual I |
| 331–410 | Fire Bat | 3 | Solitary (see source book) | Monster Manual II |
| 411–480 | Sea Cat | 4 | Solitary (see source book) | Monster Manual I |
| 481–540 | Belker | 6 | Solitary (see source book) | Monster Manual I |
| 541–600 | Ormyrr | 6 | Solitary (see source book) | Monster Manual II |
| 601–660 | Breathdrinker | 7 | Solitary (see source book) | Monster Manual II |
| 661–720 | Mudmaw | 7 | Solitary (see source book) | Monster Manual II |
| 721–770 | Legendary Snake | 8 | Solitary (see source book) | Monster Manual II |
| 771–810 | Marraenoloth | 10 | Solitary (see source book) | Monster Manual II |
| 811–850 | Air Weird | 12 | Solitary (see source book) | Monster Manual II |
| 851–890 | Octopus Tree | 12 | Solitary (see source book) | Fiend Folio |
| 891–920 | Cinder Swarm | 13 | Solitary (see source book) | Monster Manual III |
| 921–960 | Skeleton Warrior | 14 | Solitary.                                          and is used by permission. | Tome of Horrors Revised (Necromancer Games |
| 961–980 | Waterveiled Assassin | 15 | Solitary (see source book) | Monster Manual IV |
| 981–1000 | Teratomorph | 16 | Solitary (see source book) | Monster Manual II |

APOC notes, stat blocks and pictures per entry are in encounters.json / the roller / STATBLOCKS.md (undead house rules, enclave-demon note, named-encounter flags).

## River/Lake/Coast — Open Water (d1000)

*In the water itself.*

| d1000 | Encounter | CR | Number appearing | Source |
|---|---|---|---|---|
| 01–70 | Cullenrock Barnacle | 0.5 | Solitary (see source book) | Monsternomicon Vol. 2 |
| 71–150 | Bog Trog | 1 | Solitary (see source book) | Monsternomicon Vol. 1 |
| 151–230 | Octopus | 1 | Solitary (see source book) | Monster Manual I |
| 231–310 | Squid | 1 | Solitary (see source book) | Monster Manual I |
| 311–380 | Sahuagin | 2 | Solitary (see source book) | Monster Manual I |
| 381–450 | Dinosaur, Cryptoclidus | 3 | Solitary (see source book) | Monster Manual II |
| 451–520 | Mummy of the Deep | 4 | Solitary or gang (2-4) | Tome of Horrors Revised (Necromancer Games |
| 521–590 | Vine Horror | 4 | Solitary (see source book) | Fiend Folio |
| 591–650 | Troll, Scrag | 5 | Solitary (see source book) | Monster Manual I |
| 651–710 | Kopru | 6 | Solitary (see source book) | Monster Manual II |
| 711–760 | Boatman | 7 | Solitary (see source book) | Monsternomicon Vol. 1 |
| 761–810 | Naga, Water | 7 | Solitary (see source book) | Monster Manual I |
| 811–860 | Drowned | 9 | Solitary, pair, or crew (3–12) | Monster Manual III |
| 861–910 | Squid, Giant | 9 | Solitary (see source book) | Monster Manual I |
| 911–950 | Megalodon | 11 | Solitary (see source book) | Monster Manual II |
| 951–970 | Elder Spawn of Juiblex | 14 | Solitary (see source book) | Monster Manual V |
| 971–980 | Aboleth Mage | 17 | Solitary (see source book) | Monster Manual I |
| 981–1000 | Ocean Strider | 18 | Solitary (see source book) | Monster Manual II |

APOC notes, stat blocks and pictures per entry are in encounters.json / the roller / STATBLOCKS.md (undead house rules, enclave-demon note, named-encounter flags).
