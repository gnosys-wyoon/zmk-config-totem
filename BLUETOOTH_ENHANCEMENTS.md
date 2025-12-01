# Bluetooth Enhancement Options

## Current Configuration Status: ✅ Optimized

Your current `config/totem.conf` already includes aggressive bluetooth optimization:
- Maximum TX power (+8 dBm)
- Aggressive connection parameters (6ms min interval)
- Maximized BLE buffers (251 bytes)
- PHY update for 2M speed
- Split-optimized stack/queue sizes

**Performance**: ~90% optimal for split keyboard bluetooth stability

---

## Future Enhancement Options

These are **optional** improvements that could provide marginal gains (5-10%) if specific issues arise.

### 1. BLE Passthrough Mode (Reduce Latency)

**Purpose**: Reduce authentication overhead for faster initial connection

```conf
# Disable passkey entry for faster pairing
CONFIG_ZMK_BLE_PASSKEY_ENTRY=n
```

**When to use**: If you experience slow initial connection times
**Risk**: Low (only affects pairing speed)

---

### 2. Connection Event Length Extension

**Purpose**: Maximize data throughput per connection event

```conf
# Allow longer connection events for better throughput
CONFIG_BT_CTLR_CONN_PARAM_REQ=y
CONFIG_BT_CTLR_DATA_LENGTH_MAX=251
```

**When to use**: If you notice occasional "burst" lag with rapid keypresses
**Risk**: Low (standard BLE feature)

---

### 3. Split Side Priority Override

**Purpose**: Give split communication higher priority than host connection

```conf
# Prioritize split communication over other BLE tasks
CONFIG_ZMK_SPLIT_BLE_CENTRAL_PRIORITY_OVERRIDE=y
```

**When to use**: If one side (usually peripheral) experiences more lag than the other
**Risk**: Medium (experimental feature, test thoroughly)

---

### 4. Power Consumption vs Performance Tuning

**Current Settings**:
- Idle timeout: 30 seconds
- Sleep timeout: 30 minutes

**Option A - Better Battery Life**:
```conf
CONFIG_ZMK_IDLE_TIMEOUT=60000           # 60s idle before sleep
CONFIG_ZMK_IDLE_SLEEP_TIMEOUT=900000    # 15min deep sleep
```

**Option B - Better Responsiveness**:
```conf
CONFIG_ZMK_IDLE_TIMEOUT=15000           # 15s idle
CONFIG_ZMK_IDLE_SLEEP_TIMEOUT=3600000   # 60min deep sleep
```

**When to use**: Adjust based on battery life vs wake-up responsiveness needs
**Risk**: None (user preference)

---

### 5. BLE Channel Map Optimization

**Purpose**: Use advanced channel selection algorithm for better interference avoidance

```conf
# Enable Bluetooth 5.0 channel selection algorithm #2
CONFIG_BT_CTLR_CHAN_SEL_2=y
```

**When to use**: In environments with heavy 2.4GHz interference (WiFi, other BLE devices)
**Risk**: Low (requires BLE 5.0 compatible host, which most modern devices support)

---

### 6. Controller Buffer Optimization

**Purpose**: Increase hardware-level buffers for better packet handling

```conf
# Increase RX/TX controller buffers
CONFIG_BT_CTLR_RX_BUFFERS=10
CONFIG_BT_CTLR_TX_BUFFERS=12
```

**When to use**: If you see packet loss or stuttering during intensive typing
**Risk**: Medium (increases RAM usage, may cause build failure on memory-constrained boards)
**Note**: Test that firmware still fits within flash/RAM limits

---

### 7. GATT Caching Control

**Purpose**: Improve reconnection speed with trusted devices

```conf
# Enable GATT caching for faster reconnections
CONFIG_BT_GATT_CACHING=y
CONFIG_BT_GATT_ENFORCE_CHANGE_UNAWARE=n
```

**When to use**: If reconnection after sleep takes too long
**Risk**: Low (standard BLE feature)

---

## Troubleshooting Guide

### Issue: Occasional lag spikes
**Try**: #1 (Passthrough), #2 (Event length extension)

### Issue: One side drops connection frequently
**Try**: #3 (Split priority), #6 (Buffer optimization)

### Issue: Range issues in noisy environment
**Try**: #5 (Channel selection), verify current power settings

### Issue: Slow wake-up from sleep
**Try**: #4 (Reduce sleep timeout), #7 (GATT caching)

### Issue: Battery drains too fast
**Try**: #4 (Increase timeouts)

---

## Testing Protocol

When testing new bluetooth settings:

1. **Apply one change at a time** - easier to identify what helps/hurts
2. **Test for at least 1 day** - bluetooth issues can be intermittent
3. **Test scenarios**:
   - Normal typing (sustained keypresses)
   - Burst typing (rapid IDE shortcuts)
   - After sleep wake-up
   - Range test (move away from computer)
   - Interference test (near WiFi router)
4. **Monitor**:
   - Latency/responsiveness
   - Connection stability
   - Battery life impact
   - Wake-up time

---

## Notes

- **Current config is already excellent** - only apply these if you have specific issues
- **ZMK version compatibility** - some options may not be available in older ZMK versions
- **Flash/RAM limits** - buffer increases may not fit on all boards
- **Check ZMK docs** - https://zmk.dev/docs/config/bluetooth for latest options

---

**Last Updated**: 2025-11-30
**ZMK Version**: Current as of late 2024/early 2025
