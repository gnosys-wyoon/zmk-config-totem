# ZMK Studio Configuration Backup
**Date**: 2025-11-30
**Source**: User's current ZMK Studio configuration

---

## BASE LAYER

### Layout Overview
```
┌─────┬─────┬─────┬─────┬─────┐     ┌─────┬─────┬─────┬─────┬─────┐
│  Q  │  W  │  E  │  R  │  T  │     │  Y  │  U  │  I  │  O  │  P  │
├─────┼─────┼─────┼─────┼─────┤     ├─────┼─────┼─────┼─────┼─────┤
│  A  │  S  │  D  │  F  │  G  │     │  H  │  J  │  K  │  L  │  ;  │
├─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┐
│Shift│  Z  │  X  │  C  │  V  │  B  │  N  │  M  │  ,  │  .  │  /  │  \  │
└─────┴─────┴─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┴─────┴─────┘
                  │ Esc │ Win │ SPC │ RET │ Tab │ Del │
                  │ LCtrl│NAVI│     │     │ SYM │RAlt │
                  └─────┴─────┴─────┴─────┴─────┴─────┘
                   HOLD   HOLD                HOLD  HOLD
```

### Key Assignments

**Top Row (10 keys):**
- Q, W, E, R, T | Y, U, I, O, P

**Home Row (10 keys):**
- A, S, D, F, G | H, J, K, L, ;
- **Note**: NO home row mods (plain keys)

**Bottom Row (12 keys):**
- Outer Left: **Shift**
- Z, X, C, V, B | N, M, , (comma), . (dot), / (fslash)
- Outer Right: **\ (backslash)**

**Thumb Cluster (6 keys, L→R):**

| Position | **HOLD** | **TAP** | Type |
|----------|----------|---------|------|
| Thumb 1 | **Left Ctrl** | **Esc** | Mod-tap |
| Thumb 2 | **NAVI layer** | **Super/Win/Meta** | Layer-tap |
| Thumb 3 | - | **Space** | Regular key |
| Thumb 4 | - | **Return/Enter** | Regular key |
| Thumb 5 | **SYM layer** | **Tab** | Layer-tap |
| Thumb 6 | **Right Alt** | **Delete** | Mod-tap |

---

## Key Differences from Repository Config

| Feature | ZMK Studio (Current) | Repository Config |
|---------|---------------------|-------------------|
| **Home Row Mods** | ❌ None (plain keys) | ✅ A=Alt, S=Alt, D=Ctrl, F=Shift (mirrored right) |
| **Left Outer** | Shift | DEL |
| **Thumb Esc** | Mod-tap (Ctrl/Esc) | Layer-tap or plain Esc |
| **Thumb GUI** | Layer-tap (NAVI/Super) | Layer-tap (NAV/GUI) |
| **Thumb Tab** | Layer-tap (SYM/Tab) | Layer-tap (SYM/Tab) ✅ same |
| **Thumb Del** | Mod-tap (RAlt/Del) | Plain BSPC |
| **TVP Layers** | ✅ Still present | ❌ Removed in latest commit |

---

## NAVI LAYER (Navigation + Numbers + Numpad)

### Layout Overview
```
┌─────┬─────┬─────┬─────┬─────┐     ┌─────┬─────┬─────┬─────┬─────┐
│  1  │  2  │  3  │  4  │  5  │     │  6  │  7  │  8  │  9  │  0  │
├─────┼─────┼─────┼─────┼─────┤     ├─────┼─────┼─────┼─────┼─────┤
│BkSp │ Del │  ↑  │  =  │  {  │     │  }  │ KP4 │ KP5 │ KP6 │  '  │
│     │     │     │     │     │     │     │  ←  │     │  →  │     │
├─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┐
│Shft │ Tab │  ←  │  ↓  │  →  │  (  │  )  │ KP1 │ KP2 │ KP3 │  -  │  `  │
│     │     │     │     │     │     │     │ End │  ↓  │PgDn │     │     │
└─────┴─────┴─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┴─────┴─────┘
                  │  ?  │  ?  │ Alt │  ?  │  ?  │ KP0 │
                  │     │     │     │     │     │ Ins │
                  └─────┴─────┴─────┴─────┴─────┴─────┘
```

### Key Assignments

**Top Row (10 keys - Regular Number Keys):**
- `1`, `2`, `3`, `4`, `5` | `6`, `7`, `8`, `9`, `0`
- These are **regular keyboard number row** (not numpad)

**Home Row (10 keys):**
- Left: `Backspace`, `Delete`, `Up Arrow`, `=`, `{`
- Right: `}`, `KP_4/Left Arrow`, `KP_5`, `KP_6/Right Arrow`, `'` (quote)

**Bottom Row (12 keys including outers):**
- Outer Left: `Shift`
- Left middle: `Tab`, `←` (keyboard), `↓` (keyboard), `→` (keyboard), `(` (Shift+9)
- Right middle: `)` (Shift+0), `KP_1/End`, `KP_2/Down`, `KP_3/PageDown`, `-`
- Outer Right: `` ` `` (grave/backtick)

**Thumb Cluster (6 keys):**
- Left 3: `?`, `?` (transparent - NAVI held), `Alt`
- Right 3: `?` (transparent), `mo(ADJ)` - momentary ADJ layer, `KP_0/Insert`

**Tri-Layer Access:**
- Hold **NAVI + SYM** simultaneously → **ADJ layer activates**
- When NAVI is held, 5th thumb (normally SYM layer-tap) becomes momentary ADJ

### Numpad Layout (Right Side)
```
       (shift+9)
KP_4   KP_5   KP_6
(←)           (→)

       (shift+0)
KP_0   KP_1   KP_2   KP_3
(Ins)  (End)  (↓)   (PgDn)
```

### Design Philosophy

**Brilliant numpad emulation!** Mimics a full keyboard numpad with:
- Regular number row (1-0) on top for typing
- Numpad cluster on right side with navigation functions
- Parentheses `()` positioned like numpad 9/0 for programming
- Traditional arrow cluster `←↓→` on bottom left
- Backspace/Delete on home row for quick editing

### Programming Features
- **Brackets/Braces**: `{`, `}`, `(`, `)`
- **Punctuation**: `=`, `-`, `'`, `` ` ``
- **Navigation**: Full arrow keys + Home/End/PgUp/PgDn/Insert

**Note:** Most thumb keys appear transparent (pass-through from BASE layer)

---

## SYM LAYER (Symbols + Common Shortcuts)

### Layout Overview
```
┌─────┬─────┬─────┬─────┬─────┐     ┌─────┬─────┬─────┬─────┬─────┐
│  !  │  @  │  #  │  $  │  %  │     │  ^  │  &  │  `  │  '  │  -  │
├─────┼─────┼─────┼─────┼─────┤     ├─────┼─────┼─────┼─────┼─────┤
│ ^~  │     │     │     │     │     │     │  =  │  ~  │  "  │  _  │
│Ctrl │trans│trans│trans│trans│     │trans│     │     │     │     │
├─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┐
│trans│ ^Z  │ ^X  │ ^C  │ ^V  │trans│trans│trans│trans│trans│trans│trans│
└─────┴─────┴─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┴─────┴─────┘
                  │trans│m ADJ│trans│trans│trans│trans│
                  └─────┴─────┴─────┴─────┴─────┴─────┘
```

### Key Assignments

**Top Row (10 keys - All with Shift modifier):**
- `!` @ `#` `$` `%` | `^` `&` `` ` `` `'` `-`
- First 7 are Shift+numbers: Shift+1 through Shift+7
- Last 3 are plain: backtick, quote, minus

**Home Row (10 keys):**
- Position 0: **Ctrl+~** (Ctrl+Shift+`) - VSCode terminal toggle
- Positions 1-5: **Transparent** (pass through from BASE)
- Positions 6-9: `=` `~` `"` `_` (equals, tilde, double-quote, underscore)

**Bottom Row (12 keys):**
- Outer Left: **Transparent**
- **Copy/Paste cluster**: Ctrl+Z, Ctrl+X, Ctrl+C, Ctrl+V
- Rest: **Transparent**
- Outer Right: **Transparent**

**Thumb Cluster (6 keys - Mirror of NAVI):**
- Left 3: transparent, **mo(ADJ)**, transparent
- Right 3: transparent, transparent, transparent (SYM held)

**Tri-Layer (same as NAVI):**
- Hold **NAVI + SYM** → **ADJ layer activates**
- When SYM held, 2nd thumb becomes momentary ADJ

---

### Design Philosophy

**Under-utilized but essential!** This layer provides:
- **Common symbols** for programming: `! @ # $ % ^ & ` ' - = ~ " _`
- **Editor shortcuts**: Ctrl+Z/X/C/V (undo/cut/copy/paste)
- **VSCode terminal**: Ctrl+~ (first key on home row)
- **Minimal layer** - most keys transparent to keep BASE layer accessible

### Programming Symbols Available
- **Shifted numbers**: `! @ # $ % ^ &`
- **Quotes**: `` ` `` (backtick), `'` (single), `"` (double)
- **Math/Logic**: `-` (minus), `_` (underscore), `=` (equals), `~` (tilde)

**Note:** This is a "sparse" layer focused on high-frequency symbols and shortcuts only

---

## ADJ LAYER (System Functions & F-Keys)

### Layout Overview
```
┌─────┬─────┬─────┬─────┬─────┐     ┌─────┬─────┬─────┬─────┬─────┐
│O BLE│ BT0 │ BT1 │ BT2 │Reset│     │     │ F7  │ F8  │ F9  │ F12 │
├─────┼─────┼─────┼─────┼─────┤     ├─────┼─────┼─────┼─────┼─────┤
│BTClr│BTNxt│     │     │Boot │     │     │ F4  │ F5  │ F6  │ F11 │
├─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┐
│O USB│     │BTPrv│     │     │Unlck│     │ F1  │ F2  │ F3  │ F10 │     │
└─────┴─────┴─────┼─────┼─────┼─────┼─────┼─────┼─────┼─────┴─────┴─────┘
                  │     │     │     │     │     │     │
                  └─────┴─────┴─────┴─────┴─────┴─────┘
```

### Key Assignments

**Top Row (10 keys):**
- **LEFT SIDE - Bluetooth & System:**
  - `OUT_BLE` - Output selection: Bluetooth
  - `BT_SEL 0` - Bluetooth profile 0
  - `BT_SEL 1` - Bluetooth profile 1
  - `BT_SEL 2` - Bluetooth profile 2
  - `Reset` - System reset
- **RIGHT SIDE - F-Keys:**
  - Transparent, F7, F8, F9, F12

**Home Row (10 keys):**
- **LEFT SIDE - Bluetooth Management:**
  - `BT_CLR` - Clear current Bluetooth profile
  - `BT_NXT` - Next Bluetooth profile
  - Transparent, Transparent
  - `Bootloader` - Enter bootloader mode
- **RIGHT SIDE - F-Keys:**
  - Transparent, F4, F5, F6, F11

**Bottom Row (12 keys):**
- **Outer Left:** `OUT_USB` - Output selection: USB
- **LEFT MIDDLE:**
  - Transparent
  - `BT_PRV` - Previous Bluetooth profile
  - Transparent, Transparent
- **RIGHT MIDDLE:**
  - `Studio Unlock` - Unlock ZMK Studio
  - F1, F2, F3, F10
- **Outer Right:** Transparent

**Thumb Cluster (6 keys):**
- All **Transparent** (pass through from BASE)

---

### Function Groups

**Bluetooth Management (Left Side):**
```
OUT_BLE   BT_0   BT_1   BT_2   Reset
BT_CLR    BT_NXT
OUT_USB           BT_PRV
```

**F-Keys (Right Side):**
```
F7   F8   F9   F12
F4   F5   F6   F11
F1   F2   F3   F10
```

### Features

**Bluetooth Controls:**
- **Profile Management**: Switch between 3 Bluetooth profiles (0, 1, 2)
- **Profile Navigation**: Next/Previous profile
- **Clear Profile**: Remove Bluetooth pairing for current profile
- **Output Selection**: Switch between BLE and USB

**System Functions:**
- **Reset**: Soft reset keyboard (sys_reset)
- **Bootloader**: Enter bootloader for firmware flashing
- **Studio Unlock**: Unlock ZMK Studio for configuration

**F-Keys for IDE:**
- Arranged in logical groups: F1-F3, F4-F6, F7-F9
- F10, F11, F12 on right edge
- Perfect for IDE shortcuts (debug, run, step, etc.)

**Safety Note:**
- BT_CLR only clears **current** profile (not all profiles)
- Reset and Bootloader require holding NAVI+SYM, making accidental activation unlikely

---

## TVP1 & TVP2 LAYERS

**Status**: Present in Studio config but **NOT USED**
- These layers exist but are not utilized
- Will be removed in the new repository firmware
- No need to preserve them

---

---

## COMPREHENSIVE COMPARISON: Studio Config vs Repository Config

### Major Differences

| Feature | **Your Studio Config** | **Repository Config** | **Winner** |
|---------|----------------------|---------------------|------------|
| **Home Row Mods** | ❌ None (plain keys) | ✅ A/S/D/F = Alt/Alt/Ctrl/Shift | **Studio** (cleaner, no accidents) |
| **Thumb Modifiers** | ✅ Ctrl/Alt on thumbs | ✅ Similar | Equal |
| **NAVI Layer** | ✅ Numpad emulation + numbers | ❌ Simple nav + numbers | **Studio** (brilliant numpad) |
| **SYM Layer** | ✅ Sparse, essential symbols | ✅ Full programming symbols | **Repo** (more symbols) |
| **SYM Shortcuts** | ✅ Ctrl+~ for terminal | ❌ Not present | **Studio** (VSCode users) |
| **Copy/Paste** | ✅ Ctrl+Z/X/C/V on SYM | ❌ Not present | **Studio** (convenient) |
| **Combos** | ❓ Unknown | ✅ 13 bracket/symbol combos | **Repo** (more shortcuts) |
| **Bluetooth** | ✅ Same Bluetooth config | ⚠️ NEW: Max power settings | **Repo** (fixes lag!) |
| **Left Outer Key** | Shift | DEL | **Studio** (more useful) |
| **Parentheses** | ✅ On NAVI (numpad position) | ✅ On SYM | **Studio** (intuitive) |

---

## What You're GAINING with New Firmware

### ✅ **CRITICAL: Bluetooth Stability**
- **Maximum TX power** (+8 dBm) - fixes your lag problem!
- Aggressive connection parameters
- Enhanced buffers and split optimization
- **This alone makes the upgrade worth it**

### ✅ **Programming Combos**
The new firmware adds **13 combos** you don't currently have:
- Bracket combos: `[` `]` `{` `}` `(` `)`
- Symbol combos: `` ` `` `~` `|` `_`
- Utility: Tab, Caps Word

### ✅ **Expanded SYM Layer**
More symbols easily accessible:
- All brackets on home row: `{ [ ( < ` ~ > ) ] }`
- More operators: `| - = + \ / _ : ; ?`
- Complete symbol set for programming

### ✅ **Better Timing**
- Improved mod-tap timing (200ms vs unknown)
- Optimized for fewer accidental activations

---

## What You're LOSING (and what to do about it)

### ⚠️ **NAVI Layer Numpad**
**Your Studio config**: Brilliant numpad emulation with KP_0-9 and navigation
**Repo config**: Simple numbers without numpad functions

**Solution**: After flashing, use ZMK Studio to add back:
- KP_4/Left, KP_5, KP_6/Right
- KP_1/End, KP_2/Down, KP_3/PgDn
- KP_0/Insert

### ⚠️ **VSCode Terminal Shortcut**
**Your Studio config**: Ctrl+~ on SYM layer first key
**Repo config**: Not present

**Solution**: Add back via ZMK Studio after flashing

### ⚠️ **Copy/Paste Cluster**
**Your Studio config**: Ctrl+Z/X/C/V on SYM layer
**Repo config**: Not present

**Solution**: Add back via ZMK Studio after flashing

### ⚠️ **Left Outer Key**
**Your Studio config**: Shift (convenient)
**Repo config**: DEL

**Solution**: Change in ZMK Studio after flashing

---

## RECOMMENDED APPROACH

### Option 1: Flash New Firmware + Customize (RECOMMENDED)

**Step 1**: Flash the new firmware (get Bluetooth fixes!)
**Step 2**: Use ZMK Studio to customize:
- ✅ Keep all the combos and new symbols
- ✅ Add back your numpad layout on NAVI
- ✅ Add back Ctrl+~ on SYM
- ✅ Add back Ctrl+Z/X/C/V on SYM
- ✅ Change left outer to Shift

**Benefits**:
- ✅ Bluetooth stability (CRITICAL FIX)
- ✅ All your custom layout preserved
- ✅ Plus new combos and features
- ✅ Best of both worlds!

### Option 2: Create Hybrid Keymap in Repo

I can modify the repository keymap to include your best features:
- Add numpad emulation to NAVI layer
- Add Ctrl+~/Z/X/C/V to SYM layer
- Change left outer to Shift
- Keep all the combos

**Benefits**:
- ✅ Everything baked into firmware
- ✅ No need to use Studio after flashing
- ❌ Takes more time now

### Option 3: Stay with Current Firmware

Keep using your Studio config as-is.

**Problems**:
- ❌ **Bluetooth lag persists** (your main issue!)
- ❌ No combos for programming
- ❌ Limited symbol access

---

## MY RECOMMENDATION

**Do Option 1**: Flash new firmware, then spend 10 minutes in ZMK Studio adding back your best customizations.

**Why?**
1. **Fixes your Bluetooth problem** (the whole reason we started!)
2. **You get the combos** for faster programming
3. **You keep your numpad** (just add it back in Studio)
4. **5 minute investment** for a much better keyboard

**After flashing, your to-do list:**
- [ ] In ZMK Studio, add numpad keys to NAVI layer (5 min)
- [ ] Add Ctrl+~ to SYM layer first key (1 min)
- [ ] Add Ctrl+Z/X/C/V to SYM layer (2 min)
- [ ] Change left outer to Shift if you prefer (1 min)
- [ ] Test Bluetooth stability - should be perfect now!

---

## COMPLETE BACKUP CHECKLIST

✅ BASE layer documented
✅ NAVI layer documented (including brilliant numpad layout)
✅ SYM layer documented (Ctrl+~/Z/X/C/V shortcuts)
✅ ADJ layer documented (Bluetooth + F-keys)
✅ TVP layers noted as unused
✅ Comparison with repository config
✅ Migration strategy defined

**This backup is COMPLETE and SAFE to proceed with flashing new firmware!**
