# ZMK Studio Configuration Backup Guide

## Problem
ZMK Studio stores your keymap in the keyboard's flash memory, not in the repository.
When you flash new firmware, your Studio configuration will be lost.

---

## Solution 1: Screenshots (Recommended - Fastest)

1. **Open ZMK Studio** in your browser
2. **Connect your keyboard**
3. **Take screenshots of each layer**:
   - BASE layer
   - NAV layer
   - SYM layer
   - ADJ layer
   - Any other customizations

4. **Save screenshots** to this directory:
   ```
   zmk-config-totem/studio-backups/YYYY-MM-DD/
   ```

5. **Document special settings**:
   - Behavior settings (mod-tap timings, etc.)
   - Combo configurations
   - Any macros you created

---

## Solution 2: Manual Documentation

Create a text file documenting your changes:

```markdown
# My ZMK Studio Configuration - [DATE]

## Layer: BASE
- Position 0: Q
- Position 1: W
[... etc]

## Layer: NAV
[Document changes from default]

## Combos
- Q+W: ESC
[... etc]

## Behavior Settings
- Mod-tap timing: XXX ms
[... etc]
```

---

## Solution 3: Keep Old Firmware Files

1. **Before flashing new firmware**:
   - Download your CURRENT firmware from GitHub Actions
   - Save to: `zmk-config-totem/firmware-backups/studio-version/`
   - Label clearly: `totem_left_STUDIO_CONFIG.uf2`

2. **To revert**: Simply flash the old firmware files back

**WARNING**: This only works if you haven't pushed changes to GitHub that triggered a new build since your Studio config.

---

## Solution 4: Use ZMK Studio After Flashing

**Good news**: You can still use ZMK Studio with the new firmware!

After flashing the optimized firmware:
1. Connect to ZMK Studio
2. Make any additional tweaks you want
3. The new firmware includes all the Bluetooth fixes and features
4. You can customize on top of the optimized base

---

## Recommended Workflow

**BEFORE flashing new firmware**:

1. ✅ Take screenshots of all layers in ZMK Studio
2. ✅ Document any special combos or macros you created
3. ✅ Note any behavior settings you changed (timings, etc.)
4. ✅ Download current firmware build as backup (if available)

**AFTER flashing new firmware**:

1. ✅ Test the Bluetooth improvements (this is critical)
2. ✅ Try the new programming combos and layers
3. ✅ If you miss specific settings, use ZMK Studio to add them back
4. ✅ Studio changes are saved to the keyboard, not the repo

---

## Getting Your Current Firmware

If you want to backup your current firmware that has your Studio config:

1. Go to: https://github.com/gnosys-wyoon/zmk-config-totem/actions
2. Find the build you're currently using
3. Download that `firmware.zip`
4. Save it as a backup before flashing new version

---

## Important Notes

- **ZMK Studio changes are stored IN the keyboard**, not in your GitHub repo
- **Flashing new firmware will overwrite Studio settings**
- **You can always use Studio again after flashing** to make new customizations
- **The new firmware has the Bluetooth fixes** - this is the critical improvement
- **Screenshots are your best documentation** - quick and accurate

---

## Recovery Plan

If you flash the new firmware and want your old config back:

**Option A**: Reflash old firmware (if you saved it)
**Option B**: Use screenshots to recreate config in ZMK Studio
**Option C**: Contact me - I can help recreate your layout in the keymap file

---

## Future-Proofing

For future configurations, consider:

1. **Document changes immediately** when using ZMK Studio
2. **Take screenshots regularly**
3. **Keep a changelog** of what you customize
4. **Save firmware backups** before major changes

The ZMK team is working on export functionality for Studio, but it's not available yet.
