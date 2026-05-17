---
type: overview
domain: "Oric retro computer"
created: 2026-05-17
updated: 2026-05-17
sources: []
---

# Oric retro computer — overview

A recurring theme in this wiki is keeping the 1980s Tangerine Oric-1 and Oric Atmos alive through modern, open-hardware PCB projects. [[OldWer-Metaphoric]] documents Metaphoric, a full Oric clone distributed as KiCAD board designs — it reimplements the machine on a two-PCB main+keyboard set, with its memory subsystem derived from the earlier OriClone-1 project, and adds modern conveniences such as composite video, flexible power and dual joystick ports while letting one build switch between Oric-1 and Atmos ROMs.

[[Board-Folk-Oric-Remix]] takes the complementary approach: rather than a clone, it is a faithful replica of the original Oric motherboard that stays ROM-, software- and form-factor-compatible and still requires the original core chips, including the ULA. It is aimed at repairing or rebuilding genuine Oric machines, folding in service-manual tape modifications, a corrected /ROMDIS circuit, AD724 composite video and an optional Commodore 1531 tape interface. Together the two sources frame the practical choice for a hobbyist today — build a modernised clone from scratch ([[OldWer-Metaphoric]]) or remanufacture an authentic board to revive existing hardware ([[Board-Folk-Oric-Remix]]).

Underpinning both of those projects is the original machine itself, and [[oric.free.fr]] is the wiki's primary reference for it. A static Oric resource site online since 1998, maintained by Euphoric emulator author Fabrice Frances, it supplies the two things the hardware projects assume but do not themselves document: a register-level hardware-programming manual for the Oric's 6502/VIA/UAL/PSG architecture, and a full narrative history of Oric Products International — its 1983 launch, chronic over-optimism, twin receiverships, and the French-led afterlife that produced Sedoric and the Telestrat. It also archives the surviving software, emulator and tool ecosystem. Read it to understand what [[OldWer-Metaphoric]] and [[Board-Folk-Oric-Remix]] are faithfully reproducing.

Where [[oric.free.fr]] documents the original machine, [[defence-force.org]] covers the question of how new Oric software is written today. The personal site of developer Mickaël Pointier, online since 1997, it is the home of the OSDK (Oric Software Development Kit) — a modern PC-hosted cross-development toolchain with a C compiler, 6502 assembler, source-level linker and a full set of tape/disk-image and asset-conversion utilities. The page is a unified web+GitHub source: its companion repository archives the source code of the many Oric games and demos the OSDK produces. Together the wiki now spans the full lifecycle — the history and hardware of the Oric ([[oric.free.fr]]), the toolchain that builds software for it ([[defence-force.org]]), and the open-hardware boards that recreate the machine itself ([[OldWer-Metaphoric]], [[Board-Folk-Oric-Remix]]).
