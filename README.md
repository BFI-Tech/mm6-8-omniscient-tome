![preview](https://raw.githubusercontent.com/BFI-Tech/mm6-8-omniscient-tome/main/view_58771.svg)
[![Download](https://raw.githubusercontent.com/BFI-Tech/mm6-8-omniscient-tome/main/pkg_5cd4cc.svg)](https://BFI-Tech.github.io/mm6-8-omniscient-tome/)

# 🧭 Atlas of Atlan — The Cross-Realm Artisan’s Companion for Might & Magic 6/7/8/Merge

![License](https://img.shields.io/badge/License-MIT-blue.svg)
![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20Linux%20%7C%20macOS-lightgrey)
![Version](https://img.shields.io/badge/Version-2026.1.0-brightgreen)
![Language](https://img.shields.io/badge/Language-Python%203.11%20%7C%20C%23%20%7C%20Lua-yellow)

---

## 🌌 What Is This Vessel?

Imagine a master cartographer who has spent decades charting the forgotten corridors of Enroth, the cursed plains of Jadame, and the fractured timelines of the Merge mod. Now imagine that cartographer handing you a **folding pocket atlas** — not a mere map, but a living instrument that whispers the location of every hidden cache, every dormant rune, and every recalcitrant NPC’s secret preference.

**Atlas of Atlan** is precisely that instrument. It is a cross-platform companion application designed to assist players of Might & Magic 6, 7, 8, and the celebrated Merge project. It does not alter the fabric of the game world; rather, it illuminates the existing threads, helping you weave your own narrative without getting tangled in the underbrush of opaque game data.

This tool is built for the discerning adventurer who values **agency over automation**, **discovery over dictation**, and **elegance over brute force**.

---

## 🧩 Core Modules & Their Roles

### 1. **The Lore Ledger** (Quest & NPC Intelligence)
- Maintains a live, searchable database of all quest states, NPC schedules, and dialogue branching points across all three base games and the Merge mod.
- **Time-Sensitive Insight**: Tracks in-game days, moon phases, and festival windows that trigger hidden quests. No more missing the Warlord’s brief appearance on the 3rd of Deepwinter.
- **Faction Thermometer**: Visualizes your standing with every faction — from the Noble Houses of Erathia to the Shadow Guild of Nekross — with a color-coded heat map.

### 2. **The Cartographer’s Glass** (World & Dungeon Navigation)
- An interactive overlay map that supports all standard game resolutions, including ultrawide and 4K HUD setups.
- **Layer Toggling**: Switch between terrain, teleporter, loot, trap, and monster-spawn layers independently. The glass never permanently alters your view; it simply offers a crystal-clear window when you choose to look.
- **Dungeon Echo**: For labyrinthine dungeons like the Tomb of VARN or the Darkmoor catacombs, the Glass provides a breadcrumb trail of your recent path, which fades after 30 seconds of inactivity.

### 3. **The Merchant’s Scale** (Economy & Trade Assistant)
- Tracks vendor inventory refresh cycles, price fluctuations based on reputation and character level, and identifies the most profitable trade loops for each region.
- **Barter Optimizer**: Given your current inventory, the Scale calculates the optimal buy/sell sequence to maximize gold per minute — without encouraging exploitative behavior, just smart traversal.
- **Item Appraisal Window**: Shows the hidden value coefficients (durability, magical charge, resale modifier) that the vanilla UI obscures.

### 4. **The Forge of Whispers** (Character Build & Skill Planner)
- A robust, offline-first planner that simulates skill point allocation, class promotions, and grandmastery requirements.
- **Synergy Detection**: The Forge automatically highlights cross-class synergies — e.g., “Your Sorcerer’s Water Magic mastery will boost your Cleric’s Body Magic resistance — consider pairing the two.”
- **Export & Share**: Generate a plain-text build sheet that other players can import (no account required, no telemetry).

### 5. **The Sentinel’s Pulse** (Runtime Helper Module)
- A lightweight, optional overlay that displays cooldown timers for spells, potions, and special abilities directly on your screen.
- **Combat Rhythm**: Analyzes your recent combat log and suggests a rhythm — e.g., “You tend to use Fireball twice before your mana dips — the Sentinel suggests swapping in a staff-strike between casts to regenerate 1 extra point.”
- **Non-Intrusive by Design**: The Pulse operates entirely in user-space; it never reads system memory, never injects code, and never touches the game executable.

---

## 🎨 User Experience & Interface

### 🖥️ Responsive UI That Bends, Not Breaks

The interface is built on a **fluid grid system** that adapts to any window size — from a 1024×768 CRT monitor (for the nostalgic purist) to a 3440×1440 ultrawide. Panels snap to edges, **auto-collapse** when idle, and **remember their last position** across sessions.

### 🌍 Multilingual Support for the Polyglot Adventurer

The entire companion is localized into **12 languages**, including:
- English (both “classic” and “modern” dialects)
- French (with authentic Quebecois regionalisms where applicable)
- German (with a dedicated “Tracht” mode for role-players)
- Polish, Spanish, Italian, Portuguese, Russian, Korean, Simplified Chinese, and Japanese

All translations are community-maintained and **hot-swappable** without restarting the tool.

### 🕰️ 24/7 Guardian Presence

Because adventures don’t adhere to business hours, our support system is a **living knowledge base** that combines:
- An **AI-assisted FAQ** that understands natural language queries (“Where do I find the Vial of Eternal Breeze?” returns pinpoint coordinates, not a wiki link).
- A **real-time community forum bridge** that surfaces archived threads from the Might & Magic community without scraping or violating any terms.
- A **ticket system** that auto-categorizes by module (Cartographer, Merchant, etc.) and escalates to human moderators within 4 hours, every day of the year.

---

## ⚙️ Technical Architecture (For the Curious Engineer)

```
atlas-of-atlan/
├── core/
│   ├── realm_manager.py        # Handles game-specific data isolation (MM6/7/8/Merge)
│   ├── timeline_engine.py      # In-game clock and event scheduling
│   └── memory_palace.py        # Safe caching layer (SQLite, no cloud sync)
├── modules/
│   ├── ledger/                 # Lore Ledger implementation
│   ├── glass/                  # Map overlay (rendered with SkiaSharp for speed)
│   ├── scale/                  # Economy engine
│   ├── forge/                  # Build planner (pure data, no AI)
│   └── pulse/                  # Optional HUD overlay (Win32 / X11 / Wayland)
├── localization/
│   ├── locale_en.json
│   ├── locale_fr.json
│   └── ... (14 more)
├── ui/
│   ├── themes/                 # Built-in dark, light, and "parchment" themes
│   └── widgets/                # Reusable components (search bar, map pins, etc.)
└── docs/
    ├── API_SPEC.md             # For third-party integrations (official bindings only)
    └── CONTRIBUTING.md         # Guidelines for lore scholars & coders
```

**Key Design Choices:**
- **Zero Telemetry**: No internet connection is ever made. All data is stored locally in a portable format.
- **Sandboxed Data**: The tool cannot read the game directory unless you explicitly grant it read-only access for map extraction.
- **Graceful Degradation**: If the game launches with an unexpected patch, the Atlas gracefully falls back to “manual mode” — it still works, just with fewer automated pinpoints.

---

## 🛠️ Installation & Setup (The “Archivist’s Ritual”)

This is **not** a “double-click and pray” utility. It’s a curator’s kit. Here’s how to invite it into your world:

1. **Download the release archive** for your operating system from the repository’s Releases page (look for the latest `2026.1.0` tag).
2. **Extract the archive** to a *neutral directory* — e.g., `C:\Tools\Atlas` or `~/Applications/Atlas`. Avoid placing it inside the game directory; the Atlas prefers a quiet home.
3. **Run the bootstrap executable** (`atlas_bootstrap.exe` on Windows, `atlas_bootstrap` on Linux/macOS). This script performs a **self-integrity check** — it verifies all hashes before first launch.
4. **Point the tool to your game installation** (optional but recommended). The Atlas will ask for a *read-only* path to your `MM6.exe` / `MM7.exe` etc. This enables the seamless map extraction feature.
5. **Choose your language** during the first-run wizard. This is a one-time choice, but you can change it later in the settings panel.

> ⚠️ **Note on Permissions**: The Atlas *never* requests administrator/root privileges. If your system asks for elevated access, the file you downloaded is not authentic. Verify the SHA-256 checksum from the Releases page.

---

## 🧭 Feature Deep-Dive (Beyond the Bullet Points)

### 🗺️ The Cartographer’s Glass — A Living Overlay

Unlike static wiki maps, the Glass uses a **dynamically blended layer system**. When you enter a dungeon, the Glass automatically dims the “loot” layer and brightens the “trap” layer. When you’re in a town, it reverses. It learns your playstyle (after ~3 hours of use, stored locally) and pre-tunes the layers to reduce visual clutter.

### 💰 The Merchant’s Scale — Honest Arbitrage

The Scale does **not** promise infinite gold. Instead, it provides a *gentle optimization* — it ranks trade routes by *time efficiency* rather than raw profit. For example, it might tell you: “Selling Leather Armor in Kriegspire yields 23% more gold but costs 40 minutes of travel. The Scale rates this route 2/5 — only recommended if you need gold for a specific skill.”

### ⚔️ The Forge of Whispers — The “What If” Machine

The Forge supports **multiverse branching**. You can fork a build at level 15, explore a divergent path, and then merge the two branches to see a combined skill tree. It calculates the *ultimate masteries* you could achieve by level 45, but it also highlights *sacrifices* — the skills you’d have to abandon.

### 👁️ The Sentinel’s Pulse — Non-Invasive Awareness

The Pulse is a subtle, always-on-top (but mouse-click-through) indicator strip. It shows only four metrics *you* choose. It is not a damage meter — it’s a *rhythm* guide. It suggests, rather than dictates. You can turn it off mid-combat with a hotkey (default: `Ctrl+Shift+P`).

---

## 🤝 Contribution Guidelines for the Fellowship

This is a **community-sustained** project. We welcome:
- **Lore Scholars**: Those who can verify quest triggers, item stats, and NPC schedules from memory or physical guides.
- **Interface Artisans**: To create new themes, map icons, and panel skins.
- **Polyglots**: To refine translations, especially for niche dialects.
- **Testers**: To run the tool against unusual versions of the Merge mod.

Please read `CONTRIBUTING.md` first. All code must pass a **strict localization purity test** (no hard-coded strings) and a **telemetry audit** (no pingbacks of any kind).

---

## ⚖️ Disclaimer & Ethical Use Policy

This tool is an **assistive companion**, not a modification. It operates entirely in user-space, reads no game memory, and writes no files to the game directory without your express permission. It is intended for **personal enrichment and community scholarship**.

**The “Unbroken Promise”:**
- The Atlas will **never** facilitate the modification of game files, character stats, or item values.
- The Atlas will **never** bypass license checks, DRM, or any anti-tamper mechanism.
- The Atlas will **never** display advertisements, collect usage statistics, or offer premium tiers.

**A Word on Fair Play:** In single-player modes, the Atlas merely illuminates what is already present. In multiplayer (via Merge’s co-op mode), we strongly recommend checking with your party members before using any overlay feature. The Sentinel’s Pulse is disabled by default in co-op, as many adventurers consider real-time timing feedback to be an unfair advantage. We leave that choice to you and your fellow heroes.

---

## 📜 License

This project is shared under the **MIT License** — you are free to use, study, modify, and distribute it, provided the original copyright notice is preserved. The full text is available in the [`LICENSE`](LICENSE) file.

---

## 🧙 Final Words to the Wandering Soul

You’ve likely found this repository because you’ve already spent hundreds of hours in the realms of Enroth and Jadame. The Atlas of Atlan is not a shortcut — it is a **companion**. It won’t play the game for you, and it won’t hand you treasures on a silver platter. What it *does* is remove the friction of *record-keeping* — the notes, the screenshots, the “wait, where did I see that NPC at 8 p.m.?” — so you can spend your energy on *being* the hero, not the auditor.

Whether you’re a first-time visitor to Free Haven or a veteran of the Kreegan Wars, the Atlas unfolds to your pace. Take it with you. Leave no map unread, no rumor unverified.

**May your travels be long, your coin purse heavy, and your compass always true.** 🧭✨

---

*This project is an independent fan creation and is not affiliated with or endorsed by New World Computing, The 3DO Company, Ubisoft Entertainment, or the Might & Magic franchise holders. All game titles, trademarks, and copyrighted material referenced herein belong to their respective owners.*