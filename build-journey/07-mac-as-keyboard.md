---
type: journey-note
title: "MacBook as keyboard / terminal — typing on the Mac instead of the Oric"
created: 2026-05-18
status: research note — partial; USB keyboard via LOCI needs hands-on testing
related_wiki:
  - "[[sodiumlb-loci-hardware]]"
  - "[[sodiumlb-loci-firmware]]"
  - "[[raxiss.com]]"
---

# MacBook as keyboard / terminal — typing on the Mac instead of the Oric

> **Question:** Can I use a terminal program on my MacBook to type into the Oric — instead of typing on the Oric keyboard?
>
> **Short answer:** Yes, **for BBS/terminal sessions** — clean, well-supported, works today. For general Oric use (BASIC, programs) it is harder; a USB keyboard via LOCI is possible but comes with caveats.

---

## 1. The two distinct use cases

| Use case | What you want | Supported? |
|---|---|---|
| **A — BBS / serial terminal sessions** | Mac keyboard drives an Oric terminal session over the modem | ✅ Yes — via PicoWiFiModemUSB TCP server mode (see below) |
| **B — General Oric input** | Mac keyboard replaces the physical Oric keyboard for BASIC, programs, etc. | ⚠️ Partial — USB HID keyboard via LOCI works for LOCI-aware software; doesn't replace the VIA keyboard matrix for legacy programs |

---

## 2. Use case A — Driving a BBS session from the Mac (works today)

### How

PicoWiFiModemUSB has a **TCP server mode**: `AT$SP=2323` tells the modem to listen on TCP port 2323 for incoming connections. When a connection arrives, the modem relays it transparently to the Oric's ACIA (via LOCI).

On the Mac, open Terminal.app and Telnet into the Pico W's local IP:

```bash
telnet 192.168.1.42 2323     # replace with your Pico W's IP (check router DHCP)
```

Everything you type on the Mac keyboard goes: **Mac → WiFi → PicoWiFiModemUSB → LOCI ACIA emulation → Oric terminal software**.

The Oric terminal software processes it exactly as if it arrived from the remote BBS. Effectively the Mac becomes the keyboard for that terminal session.

### Setup steps

On the Oric side (one-time, via the Oric keyboard):

```
AT$SP=2323        ← enable TCP server on port 2323
AT&W              ← save setting
ATI               ← shows the Pico W's IP address
```

On the Mac:
```bash
telnet <pico-ip> 2323
```

### What you can do from the Mac terminal

- Type commands into the Oric terminal program
- The Oric's screen still shows output (the video is on the Oric)
- You are essentially "remoting" the keyboard half of the Oric terminal session

### Limitation

- The Oric **display** is still on the Oric's connected TV/monitor — the Mac is keyboard-only, not screen. There is no screen-sharing or video-over-IP for the Oric.
- The Oric must be running terminal software that reads the ACIA. This won't let you type into BASIC unless the Oric is already in a mode that reads ACIA input.

---

## 3. Use case B — USB keyboard plugged into LOCI (partial / experimental)

LOCI lists USB HID devices (mouse, keyboard, game controllers) among its supported USB peripherals. The LOCI User Manual notes:

> *"USB mouse and other HID devices can be accessed from Oric with new APIs."*

The qualification **"new APIs"** is important: this means LOCI-aware software can query HID input via the LOCI interface. It does **not** automatically remap a USB keyboard to the Oric's VIA keyboard matrix (the physical keyboard wiring). Legacy software that polls the VIA keyboard matrix directly will not see USB HID input.

### What does work

- The **LOCI UI** itself (the configuration menu) already responds to the physical Oric keyboard. Whether it also reads a LOCI-attached USB keyboard is not documented as of the ingested wiki.
- New software written for LOCI can use the HID APIs — so BBS terminal software written with LOCI in mind could read a USB keyboard directly.
- A USB keyboard plugged into LOCI's USB-C port (or via a powered hub) is a viable path for software that explicitly supports it.

### What does not work

- Plugging the MacBook itself into LOCI's USB-C. The Mac cannot present itself as a USB HID keyboard device — Macs are USB hosts, not devices. LOCI is also a USB host. Two hosts cannot connect directly.
- Legacy Oric software (BASIC, most games) polling the VIA keyboard matrix — they will not see USB input without a matrix-injection shim.

### USB keyboard that DOES work today (if you want one before the Metaphoric keyboard is built)

Simply plug **any standard USB keyboard** into LOCI's USB-C port. For LOCI-UI navigation and any LOCI-aware terminal software, it should work. This is a practical interim option while the Metaphoric MX keyboard PCB is being assembled.

---

## 4. What is not possible (honest column)

| Approach | Why it doesn't work |
|---|---|
| Mac USB-C directly into LOCI | Mac is USB host; LOCI is USB host — no device mode on either side |
| Screen sharing / remote desktop for the Oric | No IP stack on the Oric; no video-over-network hardware |
| Mac driving Oric BASIC interactively over WiFi | Requires Oric software that reads ACIA and passes to BASIC input — not off-the-shelf |

---

## 5. Practical recommendation

For **BBS use** (which is the main serial use case): set `AT$SP=2323` on the PicoWiFiModemUSB once, then `telnet <pico-ip> 2323` from Terminal.app whenever you want to type from the Mac. This requires zero extra hardware beyond what is already in the BOM.

For **general Oric use** before the Metaphoric keyboard PCB is assembled: plug a cheap USB keyboard into LOCI's USB-C. It won't run legacy software but the LOCI UI and new LOCI-aware software will see it.

For **full keyboard replacement** (legacy + new software): there is no off-the-shelf solution today. Board-Folk Oric-Remix has a prototype PS/2+USB keyboard expansion in their repo (`Expansions/Oric-PS2USB/`) that injects keystrokes into the VIA matrix — but it is a prototype, and it is for Oric Remix, not Metaphoric ([[Board-Folk-Oric-Remix]]).

---

## 6. Decision log

- **2026-05-18.** Researched Mac-as-keyboard options. For BBS sessions: PicoWiFiModemUSB TCP server mode + `telnet <ip> port` from Terminal.app is the clean answer — no extra hardware. For general keyboard use: USB keyboard via LOCI is partial (LOCI-aware software only). No full VIA matrix injection solution available for Metaphoric today.
