# Inbox

Drop URLs below under `## Pending`. Run `/pin-llm-wiki run <url>` to ingest a single URL (auto-queues it if missing), or `/pin-llm-wiki run` to batch-process every pending item. Agents may use `/pin-llm-wiki queue <url>` to suggest URLs without immediately ingesting them.

## Pending

<!-- Add URLs here, one per line, as markdown checkboxes.
     Supported inline tags (append each wrapped in HTML comment syntax):
       detail:brief        — override detail level for this source
       detail:standard
       detail:deep
       branch:dev          — GitHub: use this branch instead of default
       clone               — GitHub deep: full git clone to raw/github/<org>-<repo>/
       skip                — skip this URL on the next run
       companion:github.com/<org>/<repo>  — web: use this repo as companion (skip auto-discovery)
       no-companion        — web: suppress companion GitHub fetch even if a repo is found
       note: <text>        — freeform note for human review (ignored by ingest)
-->

- [ ] https://github.com/sodiumlb/ocula-pivic-firmware <!-- note: modern Pico-based ULA replacement firmware; companion to LOCI; central to build plan Phase 3 -->
- [ ] https://github.com/sodiumlb/loci-hardware <!-- note: LOCI hardware design files + project wiki; pairs with already-ingested loci-firmware -->
- [ ] https://myretrostore.co.uk/product/oric-1-atmos-clone-issue-5-pcb/ <!-- note: Kenneth's traced-replica PCB (Option D in build-journey paper); currently OOS -->
- [ ] https://oric.forumactif.org/t945-metaphoric <!-- note: French CEO/Oric forum's Metaphoric thread; Kenneth is OP -->
- [ ] https://ceo.oric.org/community/oric-atmos/metaphoric/ <!-- note: CEO Oric forum Metaphoric thread -->
- [ ] https://www.986-studio.com/category/retro-computing/oric/replicoric/ <!-- note: historical Replic'Oric project (2014); context only -->
- [ ] https://oldcrap.org/2019/12/14/oric-nova-64/ <!-- note: Old Crap teardown of an actual Oric Nova 64 (the user's childhood machine) -->
- [ ] https://oric.signal11.org.uk/html/diagrom.htm <!-- note: Mike Brown's Oric diagnostic ROM; essential first-power-on tool -->
- [ ] https://en.wikipedia.org/wiki/Pravetz_(computer) <!-- note: Pravetz 8D Bulgarian Oric clone; alternate ULA donor source -->
- [ ] https://forum.defence-force.org/viewtopic.php?f=11&t=2268 <!-- note: forum: Metaphoric original announcement (Dec 2024, 17 replies, 19k views) -->
- [ ] https://forum.defence-force.org/viewtopic.php?f=11&t=2398 <!-- note: forum: Metaphoric V2 (Apr 2025) — what's in the repo -->
- [ ] https://forum.defence-force.org/viewtopic.php?f=11&t=2522 <!-- note: forum: Loci + Metaphoric (Apr 2026) — confirms the recommended pairing works -->
- [ ] https://forum.defence-force.org/viewtopic.php?f=11&t=2351 <!-- note: forum: OCULA canonical thread (267 replies, 90k views, still active May 2026) -->
- [ ] https://forum.defence-force.org/viewtopic.php?f=11&t=2447 <!-- note: forum: the one and only Oric Remix thread (Aug 2025, 4 replies) -->

## Completed

<!-- Processed lines are moved here automatically.
     Format after ingest: - [x] https://... with an "ingested YYYY-MM-DD" HTML comment appended.
     To re-fetch: add a "refresh" HTML comment to the line, then run /pin-llm-wiki run.
     The refresh tag is removed automatically after re-fetch.
-->

- [x] https://github.com/OldWer/Metaphoric <!-- ingested 2026-05-17 -->
- [x] https://github.com/Board-Folk/Oric-Remix <!-- ingested 2026-05-17 -->
- [x] http://oric.free.fr/ <!-- ingested 2026-05-17 -->
- [x] https://www.defence-force.org/ <!-- ingested 2026-05-17 -->
- [x] https://forum.defence-force.org/index.php <!-- ingested 2026-05-17 -->
- [x] https://osdk.org/ <!-- ingested 2026-05-17 -->
- [x] https://library.defence-force.org/ <!-- ingested 2026-05-17 -->
- [x] https://blog.defence-force.org/ <!-- ingested 2026-05-17 -->
- [x] http://www.48katmos.freeuk.com/ <!-- ingested 2026-05-17 -->
- [x] https://github.com/sodiumlb/loci-firmware <!-- ingested 2026-05-17 -->
- [x] https://www.raxiss.com/article/id/38-LOCI <!-- ingested 2026-05-17 -->
