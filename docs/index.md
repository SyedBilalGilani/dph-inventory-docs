<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>DPH Inventory System v1</title>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@700;800&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  :root { --bg:#0a0c10;--surface:#111318;--border:#1e2330;--accent:#4f8ef7;--accent3:#10b981;--text:#e8eaf0;--muted:#6b7280; }
  *{margin:0;padding:0;box-sizing:border-box;}
  body{background:var(--bg);color:var(--text);font-family:'DM Sans',sans-serif;font-size:15px;line-height:1.7;max-width:800px;margin:0 auto;padding:40px 28px 80px;}
  .hero{border:1px solid var(--border);border-radius:14px;padding:44px 40px 36px;background:linear-gradient(135deg,#0f1420,#111827);margin-bottom:40px;position:relative;overflow:hidden;}
  .hero::before{content:'';position:absolute;top:-60px;right:-60px;width:260px;height:260px;background:radial-gradient(circle,rgba(79,142,247,0.1) 0%,transparent 70%);}
  .badge-row{display:flex;gap:8px;flex-wrap:wrap;margin-bottom:18px;}
  .badge{font-family:'Syne',sans-serif;font-size:10px;font-weight:700;letter-spacing:.1em;text-transform:uppercase;padding:3px 11px;border-radius:100px;border:1px solid;}
  .b1{color:var(--accent);border-color:rgba(79,142,247,.3);background:rgba(79,142,247,.08);}
  .b2{color:#a78bfa;border-color:rgba(124,58,237,.3);background:rgba(124,58,237,.08);}
  .b3{color:var(--accent3);border-color:rgba(16,185,129,.3);background:rgba(16,185,129,.08);}
  .hero h1{font-family:'Syne',sans-serif;font-size:34px;font-weight:800;line-height:1.15;margin-bottom:6px;background:linear-gradient(135deg,#e8eaf0,#a0aec0);-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;}
  .hero-sub{font-size:15px;color:var(--muted);margin-bottom:22px;}
  .hero-desc{font-size:14px;color:#9ca3af;line-height:1.8;border-top:1px solid var(--border);padding-top:20px;}
  .section-label{font-family:'Syne',sans-serif;font-size:10px;font-weight:700;letter-spacing:.12em;text-transform:uppercase;color:var(--accent);margin-bottom:12px;display:flex;align-items:center;gap:10px;}
  .section-label::after{content:'';flex:1;height:1px;background:var(--border);}
  .section{margin-bottom:36px;}
  h2{font-family:'Syne',sans-serif;font-size:18px;font-weight:700;margin-bottom:12px;}
  p{color:#9ca3af;margin-bottom:10px;font-size:14px;}
  .grid{display:grid;grid-template-columns:1fr 1fr;gap:10px;}
  .card{background:var(--surface);border:1px solid var(--border);border-radius:10px;padding:16px;}
  .card-icon{font-size:18px;margin-bottom:8px;display:block;}
  .card-title{font-family:'Syne',sans-serif;font-size:13px;font-weight:700;color:var(--text);margin-bottom:4px;}
  .card-desc{font-size:12px;color:var(--muted);line-height:1.5;}
  .highlight{background:rgba(79,142,247,.05);border:1px solid rgba(79,142,247,.18);border-radius:10px;padding:18px 22px;margin-bottom:12px;}
  .highlight p{color:#c4cad6;margin:0;font-size:14px;}
  table{width:100%;border-collapse:collapse;font-size:13px;}
  th{font-family:'Syne',sans-serif;font-size:10px;font-weight:700;letter-spacing:.08em;text-transform:uppercase;color:var(--muted);padding:8px 14px;text-align:left;border-bottom:1px solid var(--border);}
  td{padding:10px 14px;border-bottom:1px solid rgba(30,35,48,.5);color:#9ca3af;vertical-align:top;}
  tr:last-child td{border-bottom:none;}
  td:first-child{font-family:'Syne',sans-serif;font-weight:700;color:var(--text);white-space:nowrap;}
  .tag{display:inline-block;background:#1a2035;border:1px solid var(--border);border-radius:5px;padding:1px 9px;font-size:11px;color:var(--accent);}
  .two-col{display:grid;grid-template-columns:1fr 1fr;gap:20px;}
  ul.check{list-style:none;}
  ul.check li{padding:6px 0;color:#9ca3af;font-size:13px;display:flex;gap:10px;border-bottom:1px solid rgba(30,35,48,.4);}
  ul.check li:last-child{border-bottom:none;}
  ul.check li::before{content:'✓';color:var(--accent3);font-weight:700;flex-shrink:0;}
  ul.check li.no::before{content:'—';color:var(--muted);}
  .list-head{font-family:'Syne',sans-serif;font-size:13px;font-weight:700;margin-bottom:10px;}
  .list-head.green{color:var(--accent3);}
  .list-head.gray{color:var(--muted);}
  .divider{height:1px;background:var(--border);margin:36px 0;}
  .footer{text-align:center;font-size:12px;color:var(--muted);padding-top:24px;border-top:1px solid var(--border);}
  .footer strong{color:var(--text);font-family:'Syne',sans-serif;}
  .plain{display:none;white-space:pre-wrap;font-family:monospace;font-size:13px;background:#111;color:#ccc;padding:24px;border-radius:10px;line-height:1.6;}
  .toggle-btn{background:var(--accent);color:#fff;border:none;border-radius:8px;padding:10px 20px;font-family:'Syne',sans-serif;font-size:13px;font-weight:700;cursor:pointer;margin-bottom:24px;}
</style>
</head>
<body>

<!--<button class="toggle-btn" onclick="toggleView()">Toggle Plain Text (for copy/paste)</button>-->

<div class="plain" id="plain">DPH Inventory System v1.0
Unreal Engine 5 | Blueprint Only | No Plugins Required

A modular, Blueprint-only using Gameplay tags inventory system for UE5. No plugins. Drop it into any project and start building immediately.

FEATURES
- Drag & Drop between inventory, hotbar, and storage containers
- Hotbar (keys 1-0): consume food, equip weapons, extendable to any type
- Stack Splitting: Shift+Click to split any stack in half instantly
- Drop Slider: Right-click to choose how many items to drop to the world
- World Pickup: Press E to pick up items with DOT-product facing detection
- Equipment: Handheld items attach to character sockets on equip
- Tooltips: Hover any slot for name, description, icon, quantity
- Category Filter: Filter inventory by item type

ARCHITECTURE
Component-based — each system is isolated and replaceable:
- ItemContainerComponent: Core inventory logic and slot management
- HandheldManagerComponent: Spawns and attaches equipped item meshes
- InteractionManagerComponent: World interaction with FOV filtering

ITEM SYSTEM
Items use UE5 Gameplay Tags — no enums, no hard references. Add new items without modifying any Blueprint. Each item has a Data Asset with name, description, icon, world actor class, and stack size.

CONTROLS
I / Tab         Toggle inventory
E               Pick up / interact
1-0             Hotbar activate
Shift+Click     Split stack in half
Right Click     Open drop quantity slider

REQUIREMENTS
- Unreal Engine 5.0+
- Blueprint or C++ project
- No plugins required
- Works with any ability system (GAS, custom, or none)
- Multiplayer not supported in v1

INCLUDED IN V1
- Drag and drop inventory
- Hotbar with type-based routing
- Stack splitting
- Drop quantity slider
- World item pickup and interaction
- Handheld equipment system
- Tooltip system
- Category filtering
- Gameplay Tag item identification
- Full technical documentation included

NOT IN V1 (planned v2): Equipment panel UI, Shop system, Crafting, Hunger/health, Multiplayer</div>

<div id="visual">
<div class="hero">
  <div class="badge-row">
    <span class="badge b1">Unreal Engine 5</span>
    <span class="badge b2">Blueprint Only</span>
    <span class="badge b3">No Plugins Required</span>
  </div>
  <h1>DPH Inventory System</h1>
  <p class="hero-sub">by DevPlayHub — v1.0</p>
  <p class="hero-desc">A modular, Blueprint-only inventory system for UE5. No external plugins. This is tested on UE 5.7 but will work on 5.0+ easily. Drop it into any project — drag and drop, hotbar, item splitting, world pickup, equipment, and tooltips all included.</p>
</div>

<div class="section">
  <div class="section-label">Features</div>
  <div class="grid">
    <div class="card"><span class="card-icon">🎒</span><div class="card-title">Drag & Drop Inventory</div><p class="card-desc">Move items between inventory, hotbar, and storage containers.</p></div>
    <div class="card"><span class="card-icon">🔢</span><div class="card-title">Hotbar (Keys 1–0)</div><p class="card-desc">Consume food, equip weapons — extendable to any item type.</p></div>
    <div class="card"><span class="card-icon">✂️</span><div class="card-title">Stack Splitting</div><p class="card-desc">Shift+Click to instantly split any stack in half.</p></div>
    <div class="card"><span class="card-icon">📦</span><div class="card-title">Drop Quantity Slider</div><p class="card-desc">Right-click to choose exactly how many items to drop.</p></div>
    <div class="card"><span class="card-icon">🌐</span><div class="card-title">World Item Pickup</div><p class="card-desc">Press E to interact. </p></div>
    <div class="card"><span class="card-icon">🗡️</span><div class="card-title">Equipment System</div><p class="card-desc">Handheld items attach to character sockets on equip.</p></div>
    <div class="card"><span class="card-icon">💬</span><div class="card-title">Item Tooltips</div><p class="card-desc">Hover any slot for name, description, icon, and quantity.</p></div>
    <div class="card"><span class="card-icon">🏷️</span><div class="card-title">Category Filtering</div><p class="card-desc">Filter inventory by item type.</p></div>
  </div>
</div>

<div class="section">
  <div class="section-label">No Plugin Dependency</div>
  <div class="highlight">
    <p><strong style="color:#e8eaf0;">Works with any ability system.</strong> No external plugins. Hook in your own GAS, ALS, or custom stat system at clearly documented extension points. Pure Blueprint — fully readable and modifiable.</p>
  </div>
</div>

<div class="section">
  <div class="section-label">Controls</div>
  <table>
    <tr><th>Input</th><th>Action</th></tr>
    <tr><td><span class="tag">I / Tab</span></td><td>Toggle inventory</td></tr>
    <tr><td><span class="tag">E</span></td><td>Pick up / interact with world object</td></tr>
    <tr><td><span class="tag">1 – 0</span></td><td>Hotbar activate (consume / equip)</td></tr>
    <tr><td><span class="tag">Shift + Click</span></td><td>Split stack in half</td></tr>
    <tr><td><span class="tag">Right Click</span></td><td>Open drop quantity slider</td></tr>
  </table>
</div>

<div class="section">
  <div class="section-label">What's Included</div>
  <div class="two-col">
    <div>
      <p class="list-head green">✓ Included in v1</p>
      <ul class="check">
        <li>Drag and drop inventory</li>
        <li>Hotbar with type-based routing</li>
        <li>Stack splitting</li>
        <li>Drop quantity slider</li>
        <li>World item pickup</li>
        <li>Equipment system</li>
        <li>Tooltip system</li>
        <li>Category filtering</li>
        <li>Gameplay Tag item IDs</li>
        <li>Full technical documentation</li>
      </ul>
    </div>
    <div>
      <p class="list-head gray">— Planned for v2</p>
      <ul class="check">
        <li class="no">Equipment panel UI</li>
        <li class="no">Shop / vendor system</li>
        <li class="no">Crafting system</li>
        <li class="no">Hunger / health attributes</li>
        <li class="no">Multiplayer support</li>
      </ul>
    </div>
  </div>
</div>

<div class="section">
  <div class="section-label">Requirements</div>
  <table>
    <tr><th>Item</th><th>Details</th></tr>
    <tr><td>Engine Version</td><td>Unreal Engine 5.7 + But will work fine 0n 5.0+ </td></tr>
    <tr><td>Project Type</td><td>Blueprint or C++</td></tr>
    <tr><td>Required Plugins</td><td>None — Enhanced Input and Gameplay Tags ship with UE5</td></tr>
    <tr><td>Ability System</td><td>Not required — fully standalone</td></tr>
    <tr><td>Multiplayer</td><td>Not supported in v1</td></tr>
  </table>
</div>

<div class="divider"></div>
<div class="footer"><strong>DPH Inventory System v1.0</strong><br>Unreal Engine 5 &nbsp;·&nbsp; Blueprint Only &nbsp;·&nbsp; No Plugin Dependencies</div>
</div>

<script>
function toggleView(){
  const p=document.getElementById('plain'),v=document.getElementById('visual');
  if(p.style.display==='block'){p.style.display='none';v.style.display='block';}
  else{p.style.display='block';v.style.display='none';}
}
</script>
</body>
</html>
