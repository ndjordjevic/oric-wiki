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

<!-- Curated 2026-05-17 against the build decision in build-journey/01-decision-bom-order.md:
     board = Metaphoric V2, original HCS10017 ULA, LOCI storage, OCULA as a later open experiment.
     Items are grouped: ingest the first two groups; the `skip`-tagged group is kept for the
     record but excluded from the next run. Flip a `skip` tag to re-include an item. -->

### Core build — ingest (Metaphoric + original ULA + LOCI)

- [ ] https://github.com/sodiumlb/loci-hardware <!-- note: LOCI hardware design files + project wiki; LOCI is the chosen storage peripheral -->
- [ ] https://oric.signal11.org.uk/html/diagrom.htm <!-- note: Mike Brown's diagnostic ROM; essential first-power-on tool (build doc §9) -->
- [ ] https://forum.defence-force.org/viewtopic.php?f=11&t=2268 <!-- note: forum: Metaphoric original announcement (Dec 2024) -->
- [ ] https://forum.defence-force.org/viewtopic.php?f=11&t=2398 <!-- note: forum: Metaphoric V2 (Apr 2025) — the exact version being built -->
- [ ] https://forum.defence-force.org/viewtopic.php?f=11&t=2522 <!-- note: forum: Loci + Metaphoric (Apr 2026) — confirms the chosen pairing works -->
- [ ] https://oric.forumactif.org/t945-metaphoric <!-- note: French CEO/Oric forum's Metaphoric thread; Kenneth is OP -->
- [ ] https://ceo.oric.org/community/oric-atmos/metaphoric/ <!-- note: CEO Oric forum Metaphoric thread -->

### OCULA — ingest (the optional open-hardware experiment, build doc §3)

- [ ] https://github.com/sodiumlb/ocula-hardware <!-- note: OCULA KiCAD hardware design files (BSD-3) — the open ULA-replacement board; key to the "understand every piece" goal -->
- [ ] https://github.com/sodiumlb/ocula-pivic-firmware <!-- note: OCULA/PIVIC firmware (BSD-3) -->
- [ ] https://github.com/sodiumlb/ocula-docs <!-- note: OCULA user documentation — install + firmware-update guide -->
- [ ] https://forum.defence-force.org/viewtopic.php?f=11&t=2709 <!-- note: forum: OCULA canonical thread. CORRECTED — 00 paper listed this as t=2351, but t=2351 is an unrelated "Music" thread; the real OCULA thread is t=2709 (18 pages, active May 2026) -->

### Skip — not relevant to the chosen build (kept for the record; remove the `skip` tag to re-include)

- [ ] https://myretrostore.co.uk/product/oric-1-atmos-clone-issue-5-pcb/ <!-- skip --> <!-- note: Kenneth's Issue 5 PCB — rejected: not open source and PCB not orderable -->
- [ ] https://forum.defence-force.org/viewtopic.php?f=11&t=2447 <!-- skip --> <!-- note: Oric Remix forum thread — rejected board option (Metaphoric chosen) -->
- [ ] https://oldcrap.org/2019/12/14/oric-nova-64/ <!-- skip --> <!-- note: Nova 64 teardown — cosmetic/historical only; user dropped the Nova case/badge angle. Soft skip — re-include if you want childhood-machine reference photos -->
- [ ] https://www.986-studio.com/category/retro-computing/oric/replicoric/ <!-- skip --> <!-- note: Replic'Oric — historical 2014 project, not a build candidate -->
- [ ] https://en.wikipedia.org/wiki/Pravetz_(computer) <!-- skip --> <!-- note: Pravetz 8D — was a fallback ULA donor; ULA now sourced from eBay (Nati 99), so background only -->

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
