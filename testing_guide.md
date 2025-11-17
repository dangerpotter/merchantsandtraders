# Merchants and Traders - Testing Guide

This guide provides comprehensive instructions for testing the Merchants and Traders mod, including console commands, test scenarios, and common issues to check for.

## Table of Contents

1. [Console Commands](#console-commands)
2. [Test Scenarios](#test-scenarios)
3. [Common Bugs to Check](#common-bugs-to-check)
4. [Balance Testing](#balance-testing)
5. [Verifying Trade Routes](#verifying-trade-routes)
6. [Event System Testing](#event-system-testing)
7. [Performance Testing](#performance-testing)

---

## Console Commands

### Enabling the Console

1. Navigate to your CK3 installation directory
2. Open the launcher
3. In the launcher, go to Settings
4. Enable **Debug Mode**
5. In game, press **`** (backtick) or **~** (tilde) to open the console

### Essential Debug Commands

#### Quick Merchant Setup

```
# Become a merchant instantly
effect = { mt_debug_become_merchant = yes }

# Add testing gold (1000)
effect = { mt_debug_add_gold = yes }

# Add more gold (5000)
effect = { mt_debug_add_gold_rich = yes }

# Add small amount (100)
effect = { mt_debug_add_gold_small = yes }
```

#### Tier Progression

```
# Force rank up to next tier
effect = { mt_debug_force_rank_up = yes }

# Set to specific tier (1-4)
effect = { mt_debug_set_tier = { tier = 1 } }  # Wandering Merchant
effect = { mt_debug_set_tier = { tier = 2 } }  # Trade Post Owner
effect = { mt_debug_set_tier = { tier = 3 } }  # Trading Company Head
effect = { mt_debug_set_tier = { tier = 4 } }  # Merchant Prince
```

#### Trade Route Testing

```
# Create a guaranteed profitable route
effect = { mt_debug_create_perfect_route = yes }
```

#### Market Manipulation

```
# Crash the global market
effect = { mt_debug_crash_market = yes }

# Boom the global market
effect = { mt_debug_boom_market = yes }

# Reset market to baseline
effect = { mt_debug_reset_market = yes }
```

#### Reputation Testing

```
# Max out reputation (100)
effect = { mt_debug_max_reputation = yes }

# Tank reputation (-50)
effect = { mt_debug_tank_reputation = yes }
```

#### Variable Inspection

```
# Show all character merchant variables
effect = { mt_debug_show_all_variables = yes }

# Show global economy status
effect = { mt_debug_show_global_economy = yes }
```

#### Standard CK3 Console Commands

```
# Add gold manually
add_gold = 1000

# Add prestige
add_prestige = 500

# Advance time (days)
fast_forward = 365

# Reveal entire map
observe

# Kill character (select them first)
kill

# Yesmen (AI accepts everything)
yesmen
```

---

## Test Scenarios

### Scenario 1: New Merchant Start

**Objective:** Verify the merchant adventurer start option works correctly.

**Steps:**

1. Start a new game
2. Select "Create Custom Ruler" or any unlanded character
3. Wait for the merchant start event to fire (~3 days)
4. Accept the merchant start option
5. Verify you receive:
   - Wandering Merchant trait
   - Starting gold boost
   - Merchant variables initialized

**Expected Results:**
- Event fires within 3-10 days
- Trait granted successfully
- Character sheet shows merchant information
- No script errors in error.log

**Test Commands:**
```
# If event doesn't fire, trigger manually:
event mt_start.0002
```

### Scenario 2: Manual Trade Progression

**Objective:** Test the Tier 1 manual trading system.

**Steps:**

1. Become a wandering merchant (or use `mt_debug_become_merchant`)
2. Use decision "Purchase Trade Goods"
3. Verify gold is deducted and `mt_carrying_goods` variable increases
4. Travel to another province (optional)
5. Use decision "Sell Trade Goods"
6. Verify profit/loss is calculated correctly

**Expected Results:**
- Goods can be purchased when you have enough gold
- Carrying goods variable updates correctly
- Selling provides profit based on distance/market conditions
- No negative gold exploits

**Test Commands:**
```
effect = { mt_debug_become_merchant = yes }
effect = { mt_debug_add_gold = yes }
```

### Scenario 3: Tier Progression

**Objective:** Verify progression through all 4 merchant tiers.

**Steps:**

1. Start as Wandering Merchant (Tier 1)
2. Accumulate required gold and reputation for Tier 2
3. Use "Establish Trade Post" decision
4. Verify upgrade to Trade Post Owner
5. Repeat for Tier 3 (Trading Company Head)
6. Repeat for Tier 4 (Merchant Prince)

**Test each tier for:**
- Correct trait applied
- Max trade route limit updated
- Decision availability changes
- Prestige gains applied

**Quick Test Commands:**
```
effect = { mt_debug_become_merchant = yes }
effect = { mt_debug_force_rank_up = yes }  # Repeat 3 times to reach max tier
```

### Scenario 4: Trade Route Creation

**Objective:** Test automated trade route system.

**Steps:**

1. Reach at least Tier 2 (Trade Post Owner)
2. Open the Trade Route Management GUI
3. Select origin county
4. Select destination county
5. Choose trade good
6. Confirm route creation
7. Verify monthly income updates

**Expected Results:**
- GUI displays correctly
- Routes appear in merchant portfolio
- Monthly gold income increases
- Route health tracks correctly (100 = perfect)

**Test Commands:**
```
effect = { mt_debug_set_tier = { tier = 2 } }
effect = { mt_debug_create_perfect_route = yes }
```

### Scenario 5: Economic Events

**Objective:** Verify economic events fire and affect the game correctly.

**Steps:**

1. Start a game with merchants active
2. Fast forward time (use `fast_forward = 365`)
3. Watch for economic events:
   - Market price fluctuations
   - Supply shortages
   - Economic booms/crashes
   - Trade disruptions from war

**Expected Results:**
- Events fire at appropriate frequencies (see BALANCING.md for MTTH)
- Global market variables change
- Player receives notifications
- Price changes affect route profitability

**Test Commands:**
```
# Trigger specific events manually
event mt_economic_events.0100  # Boom
event mt_economic_events.0200  # Crash

# Or use debug effects
effect = { mt_debug_crash_market = yes }
effect = { mt_debug_boom_market = yes }
```

### Scenario 6: War Disruption

**Objective:** Test trade route disruption during wartime.

**Steps:**

1. Create merchant with active trade routes
2. Start a war in a county your route passes through
3. Verify route health decreases
4. Verify profit decreases
5. Wait for war to end
6. Verify route begins recovery

**Expected Results:**
- Routes through war zones show reduced health
- Notification sent to player
- Profit recalculates automatically
- Routes recover after war ends

**Test Commands:**
```
effect = { mt_debug_set_tier = { tier = 3 } }
effect = { mt_debug_create_perfect_route = yes }

# Then start a war normally or use:
war = { attacker = ... defender = ... }
```

### Scenario 7: Character Death

**Objective:** Verify proper cleanup when merchant dies.

**Steps:**

1. Create merchant character with routes and goods
2. Check merchant variables are set
3. Kill character (old age, assassination, combat, etc.)
4. Verify variables are cleaned up
5. Check if heir inherits anything (currently: no inheritance)

**Expected Results:**
- Routes close on death
- Goods are lost
- No orphaned variables
- No script errors

**Test Commands:**
```
# Setup merchant
effect = { mt_debug_set_tier = { tier = 3 } }
effect = { mt_debug_create_perfect_route = yes }

# Kill character
kill
```

---

## Common Bugs to Check

### Critical Bugs

- [ ] **Infinite Gold Exploit:** Can player abuse buy/sell decisions for infinite gold?
- [ ] **Negative Gold:** Can any decision put player into negative gold?
- [ ] **Trait Stacking:** Can player have multiple merchant tier traits at once?
- [ ] **Route Overflow:** What happens if player exceeds max routes?
- [ ] **Variable Persistence:** Do merchant variables save/load correctly?

### Functional Bugs

- [ ] **Missing Localization:** Are there any `missing_key` strings in tooltips?
- [ ] **Decision Availability:** Do decisions show when they shouldn't (or vice versa)?
- [ ] **Event Chains:** Do all event chains complete properly without breaking?
- [ ] **GUI Display:** Do GUI windows display all information correctly?
- [ ] **Null References:** Any `<null>` values in tooltips or text?

### Balance Issues

- [ ] **Too Easy:** Can player become wealthy too quickly?
- [ ] **Too Hard:** Is progression impossibly slow?
- [ ] **Risk/Reward:** Are risky decisions worth taking?
- [ ] **AI Behavior:** Do AI merchants behave reasonably?
- [ ] **Economic Impact:** Do merchants actually affect the game world?

### Performance Issues

- [ ] **Lag Spikes:** Do monthly pulses cause noticeable lag?
- [ ] **Memory Leaks:** Does game slow down over long campaigns?
- [ ] **Save File Size:** Do merchant variables bloat save files excessively?

---

## Balance Testing

### Progression Pacing

Test how long it takes to reach each tier:

| Tier | Expected Time | Gold Required | Method |
|------|---------------|---------------|---------|
| Tier 1 → 2 | 5-10 years | ~500 gold | Manual trading + 1 route |
| Tier 2 → 3 | 10-20 years | ~2000 gold | 3 routes + trade posts |
| Tier 3 → 4 | 20-40 years | ~10,000 gold | 10 routes + company expansion |

**Test Process:**

1. Start new game as Tier 1 merchant
2. Play normally (no console commands)
3. Track time to reach each tier
4. Note if progression feels too fast/slow
5. Compare to expected times above

### Income Testing

Verify income from trade routes is balanced:

| Merchant Tier | Routes | Expected Monthly Income | Expected Yearly Income |
|---------------|--------|-------------------------|------------------------|
| Tier 1 | 1 | 5-15 gold/month | 60-180 gold/year |
| Tier 2 | 3 | 15-50 gold/month | 180-600 gold/year |
| Tier 3 | 10 | 50-200 gold/month | 600-2,400 gold/year |
| Tier 4 | 20+ | 200-500+ gold/month | 2,400-6,000+ gold/year |

**Test Commands:**
```
effect = { mt_debug_set_tier = { tier = 2 } }
effect = { mt_debug_create_perfect_route = yes }
# Repeat 3 times for 3 routes

# Fast forward 1 year and check gold gain
fast_forward = 365
```

### Decision Costs

Verify decision costs feel appropriate:

| Decision | Cost | Reward | Feels Balanced? |
|----------|------|--------|-----------------|
| Purchase Goods | 20-50 gold | 25-75 gold (sell) | ☐ Yes ☐ No |
| Establish Trade Post | 200 gold | Tier up | ☐ Yes ☐ No |
| Create Trade Route | 50 gold | Monthly income | ☐ Yes ☐ No |
| Hire Caravan Guard | 30 gold | Route security | ☐ Yes ☐ No |

---

## Verifying Trade Routes

### Route Health System

Route health should be affected by:

- **Wars** in route counties: -20 to -40 health
- **Raids** in route counties: -10 to -20 health
- **Low security** (bandit events): -5 to -15 health
- **Peace and stability**: +5 health per month (up to 100 max)

**Test:**

1. Create a trade route
2. Check initial health (should be 80-100)
3. Start a war in route county
4. Verify health drops
5. End war
6. Verify health recovers over time

**Commands:**
```
effect = { mt_debug_create_perfect_route = yes }
effect = { mt_debug_show_all_variables = yes }  # Check health value
```

### Route Profitability

Factors affecting profit:

- **Distance:** Longer routes = higher profit (1-3 gold per county)
- **Good Value:** Luxury goods = higher profit
- **Market Prices:** Price fluctuations affect margins
- **Route Health:** Low health = reduced profit
- **Merchant Tier:** Higher tier = bonuses to profit

**Test:**

1. Create routes of different lengths
2. Create routes with different goods
3. Compare monthly profit values
4. Verify longer luxury routes are most profitable

### Route Limits

Verify max routes per tier:

- **Tier 1:** Max 1 route
- **Tier 2:** Max 3 routes
- **Tier 3:** Max 10 routes
- **Tier 4:** Max 999 routes (unlimited)

**Test:**

```
effect = { mt_debug_set_tier = { tier = 1 } }
effect = { mt_debug_create_perfect_route = yes }
effect = { mt_debug_create_perfect_route = yes }  # Should fail or warn
```

---

## Event System Testing

### Event Frequency

| Event Type | MTTH (Mean Time To Happen) | Expected Frequency |
|------------|---------------------------|-------------------|
| Flavor Events | 6-12 months | ~1-2 per year |
| Trade Route Events | 20 months | ~1 per 2 years per route |
| Economic Events | 60 months | ~1 per 5 years |
| Career Events | Triggered by actions | On tier-up, bankruptcy, etc. |

### Testing Event Chains

**Flavor Events (mt_flavor_events.txt):**

```
event mt_flavor.1001   # Travel: Desert Caravan
event mt_flavor.1010   # Travel: Mountain Pass
event mt_flavor.2001   # People: Rival Merchant
event mt_flavor.3001   # Goods: Exotic Goods
event mt_flavor.4001   # Rumors: Distant Market
event mt_flavor.5001   # Personal: Homesickness
event mt_flavor.6001   # Seasonal: Winter Trading
```

**Trade Route Events:**

```
event mt_trade_route_events.0001   # Random complication
event mt_trade_route_events.0010   # Route critical warning
```

**Economic Events:**

```
event mt_economic_events.0100   # Market boom
event mt_economic_events.0200   # Market crash
```

**Career Events:**

```
event mt_career.0001   # Tier 1 success
event mt_career.0100   # Tier 2 celebration
event mt_career.0200   # Tier 3 achievement
event mt_career.0300   # Tier 4 ascension
```

### Event Testing Checklist

For each event, verify:

- [ ] Text displays correctly (no missing localization)
- [ ] Options work as described
- [ ] Effects apply correctly (gold changes, variables update)
- [ ] Follow-up events chain properly
- [ ] No script errors in error.log
- [ ] Tooltips are accurate and helpful
- [ ] Historical flavor feels appropriate

---

## Performance Testing

### Save/Load Testing

1. Create merchant with max routes (Tier 4)
2. Create 20+ trade routes
3. Save the game
4. Exit completely
5. Load the save
6. Verify all routes still exist
7. Verify all variables preserved
8. Check `error.log` for issues

### Long Campaign Testing

1. Start new game with merchant
2. Fast forward 200 years: `fast_forward = 73000`
3. Check game performance
4. Verify no memory leaks
5. Check save file size
6. Verify economic variables haven't gone to extreme values

**Expected Save File Impact:**

- Vanilla save: ~5-10 MB
- With MT mod (1 merchant): +100-500 KB
- With MT mod (10 merchants): +500 KB - 2 MB
- Acceptable if < 5 MB increase

### Error Log Monitoring

After each test session, check `Documents/Paradox Interactive/Crusader Kings III/logs/error.log`:

**Acceptable:**
- Warning messages (yellow)
- Info messages (white)

**Not Acceptable:**
- Error messages (red) related to MT mod
- Script errors
- Null reference errors
- Missing variable errors

---

## Test Report Template

Use this template when reporting test results:

```
# Test Session Report

**Date:** [Date]
**Mod Version:** 0.1.0
**Game Version:** CK3 1.12.x
**Testing Duration:** [Hours]

## Tests Performed

- [ ] New merchant start
- [ ] Tier progression
- [ ] Trade route creation
- [ ] Economic events
- [ ] War disruption
- [ ] Character death cleanup
- [ ] Balance testing
- [ ] Performance testing

## Issues Found

### Critical Bugs
1. [Description]
   - Steps to reproduce
   - Expected vs actual behavior
   - Error log entries (if any)

### Balance Issues
1. [Description]
   - Feels too easy/hard/slow/fast
   - Suggested adjustment

### Minor Issues
1. [Description]

## Performance Notes

- Save file size: [X MB]
- Lag during monthly pulse: [Yes/No]
- Memory usage: [Normal/High]
- Error log: [Clean/Warnings/Errors]

## Overall Assessment

[Your overall impression of mod stability and balance]

## Recommendations

[Suggested changes or areas needing more testing]
```

---

## Quick Test Checklist

Use this for rapid smoke testing after changes:

### 5-Minute Quick Test

- [ ] Mod loads without errors
- [ ] New game starts successfully
- [ ] Merchant start event fires
- [ ] At least one decision works
- [ ] No error log entries
- [ ] GUI windows open

### 30-Minute Standard Test

- [ ] All 5-minute tests pass
- [ ] Test all 4 merchant tiers
- [ ] Create at least 3 trade routes
- [ ] Trigger 3+ events manually
- [ ] Test market crash and boom
- [ ] Save and reload successfully

### 2-Hour Comprehensive Test

- [ ] All 30-minute tests pass
- [ ] Play through natural progression (Tier 1→2→3)
- [ ] Test all character interactions
- [ ] Test war disruption
- [ ] Test character death
- [ ] Test all debug commands
- [ ] Review all error logs
- [ ] Check balance pacing

---

## Troubleshooting

### Common Issues

**Mod doesn't load:**
- Check descriptor.mod is correct
- Verify CK3 version compatibility (1.12.x)
- Check error.log for syntax errors

**Events not firing:**
- Verify global variable `mt_game_initialized` is set
- Check trigger conditions in event files
- Use console to trigger manually: `event [event_id]`

**Variables not saving:**
- Check save file for variable entries
- Verify on_actions are firing (check debug logs)
- Test with clean save (no other mods)

**GUI not displaying:**
- Clear GUI cache: Delete `gui.cache` in Documents/CK3
- Verify .gui files have no syntax errors
- Check localization files are loaded

**Performance problems:**
- Reduce number of active routes
- Check for infinite loops in effects
- Profile using `profile = yes` in defines

---

## Conclusion

This testing guide should help you systematically test all features of the Merchants and Traders mod. Always test on a clean game installation with no other mods enabled first, then test compatibility with popular mods.

For bug reports, please include:
1. Exact steps to reproduce
2. Expected vs actual behavior
3. Relevant error log entries
4. Save file (if applicable)
5. List of other mods enabled

Happy testing!
