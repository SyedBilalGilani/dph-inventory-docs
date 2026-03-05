# DPH Inventory System

**Easy Inventory System for Unreal Engine 5**

[![Unreal Engine 5](https://img.shields.io/badge/Unreal%20Engine-5.0%2B-blue)](https://unrealengine.com)
[![Blueprint Only](https://img.shields.io/badge/Blueprint-Only-purple)](https://fab.com)
[![No Plugins](https://img.shields.io/badge/Plugins-None%20Required-green)](https://fab.com)

---

A modular, Blueprint-only inventory system using Gameplay Tags for UE5. No external plugins. Tested on UE 5.7 but works on 5.0+. Drop it into any project — drag and drop, hotbar, item splitting, world pickup, equipment, and tooltips all included.

---

## Features

| Feature | Description |
|---------|-------------|
| 🎒 **Drag & Drop** | Move items between inventory, hotbar, and storage containers |
| 🔢 **Hotbar (1–0)** | Consume food, equip weapons — extendable to any item type |
| ✂️ **Stack Splitting** | Shift+Click to instantly split any stack in half |
| 📦 **Drop Slider** | Right-click to choose exactly how many items to drop |
| 🌐 **World Pickup** | Press E to pick up items |
| 🗡️ **Equipment** | Handheld items attach to character sockets on equip |
| 💬 **Tooltips** | Hover any slot for name, description, icon, and quantity |
| 🏷️ **Category Filter** | Filter inventory by item type |

---

## No Plugin Dependency

!!! success "Works with any ability system"
    No external plugins required. Hook in your own GAS, ALS, or custom stat system at clearly documented extension points. Pure Blueprint — fully readable and modifiable.

---

## Architecture

Component-based — each system is isolated and replaceable:

| Component | Purpose |
|-----------|---------|
| `ItemContainerComponent` | Core inventory logic and slot management |
| `HandheldManagerComponent` | Spawns and attaches equipped item meshes to character sockets |
| `InteractionManagerComponent` | World interaction with FOV filtering |

---

## Item System

Items use UE5 Gameplay Tags — no enums, no hard references. Add new items without modifying any Blueprint. Each item has a Data Asset with name, description, icon, world actor class, and stack size.

---

## Controls

| Input | Action |
|-------|--------|
| `I / Tab` | Toggle inventory |
| `E` | Pick up / interact with world object |
| `1 – 0` | Hotbar activate (consume / equip) |
| `Shift + Click` | Split stack in half |
| `Right Click` | Open drop quantity slider |

---

## What's Included

**✅ Included in v1**

- Drag and drop inventory
- Hotbar with type-based routing
- Stack splitting
- Drop quantity slider
- World item pickup and interaction
- Handheld equipment system
- Tooltip system
- Category filtering
- Gameplay Tag item identification
- Full technical documentation (PDF)

**— Planned for v2**

- Equipment panel UI
- Shop / vendor system
- Crafting system
- Hunger / health attributes
- Multiplayer support

---

## Requirements

| Item | Details |
|------|---------|
| Engine Version | Unreal Engine 5.7+ (works on 5.0+) |
| Project Type | Blueprint or C++ |
| Required Plugins | None — Enhanced Input and Gameplay Tags ship with UE5 |
| Ability System | Not required — fully standalone |
| Multiplayer | Not supported in v1 |

---

*DPH Inventory System v1.0 — Unreal Engine 5 · Blueprint Only · No Plugin Dependencies*
