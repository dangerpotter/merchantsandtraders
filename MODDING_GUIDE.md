# Merchants and Traders - Modding Guide

This guide is for modders who want to extend the Merchants and Traders mod, create compatible add-ons, or learn from its structure.

**Version:** 0.1.0
**Last Updated:** 2025-11-17

---

## Table of Contents

1. [Overview](#overview)
2. [File Structure](#file-structure)
3. [Adding New Trade Goods](#adding-new-trade-goods)
4. [Adding New Merchant Tiers](#adding-new-merchant-tiers)
5. [Hooking Into the Economy System](#hooking-into-the-economy-system)
6. [Creating Compatible Mods](#creating-compatible-mods)
7. [Scripted Effects Documentation](#scripted-effects-documentation)
8. [Scripted Triggers Documentation](#scripted-triggers-documentation)
9. [Variable Reference](#variable-reference)
10. [Best Practices](#best-practices)

---

## Overview

The Merchants and Traders mod is built with modularity and extensibility in mind. The codebase follows consistent naming conventions, clear documentation, and separation of concerns.

### Key Design Principles

- **Prefix Everything:** All mod content uses the `mt_` prefix
- **Modular Files:** Features are separated into logical files
- **Documented Code:** Inline comments explain complex logic
- **Reusable Components:** Effects and triggers are generalized
- **Safe Defaults:** Missing variables won't break the game

---

## File Structure

```
merchantsandtraders/
├── common/
│   ├── buildings/
│   │   └── mt_trade_buildings.txt          # Trade infrastructure
│   ├── character_interactions/
│   │   └── mt_merchant_interactions.txt    # 5 merchant interactions
│   ├── character_templates/
│   │   └── mt_merchant_templates.txt       # AI merchant generation
│   ├── decisions/
│   │   ├── mt_adventurer_start_decisions.txt   # Tier 1 decisions
│   │   ├── mt_merchant_core_decisions.txt      # Career progression
│   │   ├── mt_route_management_decisions.txt   # Route creation/management
│   │   └── mt_ruler_trade_decisions.txt        # Ruler trade support
│   ├── dynasty_modifiers/
│   │   └── mt_dynasty_modifiers.txt        # Dynasty merchant bonuses
│   ├── modifiers/
│   │   ├── mt_trade_goods.txt              # 30+ trade goods
│   │   ├── mt_county_modifiers.txt         # County economic effects
│   │   ├── mt_career_modifiers.txt         # Merchant career bonuses
│   │   ├── mt_decision_modifiers.txt       # Temporary decision effects
│   │   └── mt_economic_modifiers.txt       # Trade income modifiers
│   ├── opinion_modifiers/
│   │   └── mt_merchant_opinion_modifiers.txt
│   ├── on_actions/
│   │   ├── mt_adventurer_on_actions.txt    # Game start, merchant lifecycle
│   │   ├── mt_trade_routes.txt             # Route updates, war effects
│   │   └── mt_initialization.txt           # Global economy initialization
│   ├── script_values/
│   │   ├── mt_values.txt                   # Merchant costs, income
│   │   └── mt_economy_values.txt           # Economic calculations
│   ├── scripted_effects/
│   │   ├── mt_core_effects.txt             # Merchant initialization
│   │   ├── mt_progression_effects.txt      # Tier-up mechanics
│   │   ├── mt_route_effects.txt            # Route management
│   │   ├── mt_county_effects.txt           # County economic changes
│   │   ├── mt_economy_effects.txt          # Income application
│   │   ├── mt_goods_production.txt         # Supply/demand
│   │   └── mt_debug_effects.txt            # Testing/debugging
│   ├── scripted_triggers/
│   │   ├── mt_core_triggers.txt            # Merchant status checks
│   │   ├── mt_progression_triggers.txt     # Tier-up eligibility
│   │   ├── mt_route_triggers.txt           # Route validation
│   │   └── mt_goods_triggers.txt           # Good production checks
│   └── traits/
│       └── mt_merchant_traits.txt          # 4-tier merchant traits
├── events/
│   ├── mt_adventurer_start_events.txt      # Merchant start option
│   ├── mt_merchant_career_events.txt       # Career progression events
│   ├── mt_merchant_events.txt              # Core merchant life
│   ├── mt_flavor_events.txt                # 30+ flavor events
│   ├── mt_trade_route_events.txt           # Route complications
│   ├── mt_economic_events.txt              # Market conditions
│   └── mt_political_events.txt             # Guild politics
├── gui/
│   ├── mt_merchant_window.gui              # Merchant portfolio GUI
│   └── mt_trade_route_window.gui           # Route management GUI
├── localization/
│   └── english/
│       ├── mt_core_l_english.yml           # Core text
│       ├── mt_decisions_l_english.yml      # Decision text
│       ├── mt_*_events_l_english.yml       # Event text (7 files)
│       ├── mt_*_gui_l_english.yml          # GUI text (2 files)
│       └── mt_interactions_l_english.yml   # Interaction text
├── descriptor.mod                           # Mod metadata
├── README.md                                # Player documentation
├── CHANGELOG.md                             # Version history
├── BALANCING.md                             # Economic values
├── MODDING_GUIDE.md                         # This file
├── testing_guide.md                         # Testing documentation
└── TODO.md                                  # Future features
```

---

## Adding New Trade Goods

### Step 1: Define the Trade Good Modifier

Add to `/common/modifiers/mt_trade_goods.txt`:

```
mt_trade_good_example = {
    icon = "gfx/interface/icons/modifiers/modifier_economic.dds"

    # County effects
    county_opinion_add = 5
    monthly_county_prestige = 0.15

    # Economic effects
    levy_reinforcement_rate = 0.05
    development_growth = 0.1
}
```

### Step 2: Set Initial Market Price

Add to `/common/on_actions/mt_initialization.txt` in the `mt_initialize_global_economy` effect:

```
set_global_variable = { name = mt_price_example value = 65 }
```

### Step 3: Add Localization

Add to `/localization/english/mt_core_l_english.yml`:

```yml
mt_trade_good_example:0 "Example Good"
mt_trade_good_example_desc:0 "A valuable example trade good from exotic lands."
```

### Step 4: Add to Regional Specialization (Optional)

Edit appropriate county/region files to make certain areas produce this good:

```
c_example_county = {
    add_county_modifier = {
        modifier = mt_trade_good_example
        years = -1  # Permanent
    }
}
```

### Step 5: Include in Trade Route Selection

Update trade route creation decisions to include the new good in selection options.

---

## Adding New Merchant Tiers

### Step 1: Define the Trait

Add to `/common/traits/mt_merchant_traits.txt`:

```
mt_super_merchant = {
    index = 2050  # Unique index

    # Category
    category = merchant

    # Stats
    diplomacy = 8
    stewardship = 5
    monthly_prestige = 1.5
    monthly_income_mult = 0.30

    # Compatibility
    opposites = {
        wandering_merchant
        trade_post_owner
        trading_company_head
        merchant_prince
        mt_super_merchant  # Can't stack
    }

    # Restrictions
    can_have_children = yes
    can_inherit = yes
}
```

### Step 2: Add Progression Decision

Create decision in `/common/decisions/mt_merchant_core_decisions.txt`:

```
mt_become_super_merchant_decision = {
    picture = "gfx/interface/illustrations/decisions/decision_personal_religious.dds"

    desc = mt_become_super_merchant_decision_desc
    selection_tooltip = mt_become_super_merchant_decision_tooltip

    is_shown = {
        has_trait = merchant_prince
    }

    is_valid = {
        gold >= 10000
        var:mt_reputation >= 150
        var:mt_active_routes >= 50
    }

    effect = {
        # Remove old trait
        remove_trait = merchant_prince

        # Add new trait
        add_trait = mt_super_merchant

        # Update variables
        set_variable = {
            name = mt_max_trade_routes
            value = 9999  # Even more routes!
        }

        # Pay cost
        remove_gold = 10000

        # Event celebration
        trigger_event = mt_career.0500
    }

    cost = {
        gold = 10000
        prestige = 500
    }

    ai_check_interval = 60
    ai_potential = {
        is_ai = yes
        gold >= 15000
    }
    ai_will_do = {
        base = 100
    }
}
```

### Step 3: Add Localization

```yml
mt_super_merchant:0 "Super Merchant"
mt_super_merchant_desc:0 "This character has transcended normal merchant bounds and controls a vast economic empire."
mt_become_super_merchant_decision:0 "Ascend to Super Merchant"
mt_become_super_merchant_decision_desc:0 "You have conquered the trade world. It's time to ascend beyond mortal mercantile limits."
```

### Step 4: Update Max Route Logic

Update `/common/on_actions/mt_adventurer_on_actions.txt` to include the new tier:

```
if = {
    limit = {
        has_trait = mt_super_merchant
        NOT = { has_variable = mt_max_trade_routes }
    }
    set_variable = {
        name = mt_max_trade_routes
        value = 9999
    }
}
```

---

## Hooking Into the Economy System

### Reading Global Market Prices

```
# Get current silk price
if = {
    limit = { global_var:mt_price_silk > 80 }
    # Silk is expensive, good time to sell
}
```

### Modifying Market Prices

```
# Increase silk price by 10
change_variable = {
    name = global_var:mt_price_silk
    add = 10
}

# Ensure price stays in range
if = {
    limit = { global_var:mt_price_silk > 120 }
    set_global_variable = { name = mt_price_silk value = 120 }
}
```

### Triggering Economic Events

```
# Trigger market boom
trigger_event = {
    id = mt_economic_events.0100
    days = 7
}

# Or use debug effect
effect = { mt_debug_boom_market = yes }
```

### Accessing Character Merchant Variables

```
# Check if character is a merchant
if = {
    limit = {
        OR = {
            has_trait = wandering_merchant
            has_trait = trade_post_owner
            has_trait = trading_company_head
            has_trait = merchant_prince
        }
    }

    # Access merchant variables
    save_temporary_scope_value_as = {
        name = merchant_routes
        value = var:mt_active_routes
    }

    save_temporary_scope_value_as = {
        name = merchant_reputation
        value = var:mt_reputation
    }
}
```

---

## Creating Compatible Mods

### Compatibility Checklist

To ensure your mod is compatible with Merchants and Traders:

#### ✅ **Safe to Modify:**

- Graphics and UI (reskins, repositioning)
- Additional localization languages
- New events that don't conflict with mt_ namespace
- New buildings that reference mt_trade_goods
- New decisions for non-merchant characters

#### ⚠️ **Modify With Care:**

- Economic modifiers (may affect balance)
- Character interactions (ensure mt_ interactions still work)
- On-actions (check for conflicts)
- AI behavior (may affect merchant AI)

#### ❌ **Avoid Modifying:**

- Core mt_ scripted effects (will break functionality)
- mt_ variables (will corrupt save games)
- Merchant tier traits (will break progression)
- Global economy variables (will desync markets)

### Creating an Add-On Mod

Example: "MT: Enhanced Trade Buildings" add-on

**descriptor.mod:**
```
name = "MT: Enhanced Trade Buildings"
version = "1.0"
tags = { "Gameplay" "Economy" "Trade" }
picture = "thumbnail.png"
supported_version = "1.12.*"

dependencies = { "Merchants and Traders" }  # Require base mod
```

**Your mod structure:**
```
mt_enhanced_buildings/
├── common/
│   └── buildings/
│       └── mte_advanced_buildings.txt  # Use mte_ prefix
├── localization/
│   └── english/
│       └── mte_buildings_l_english.yml
└── descriptor.mod
```

**Example building:**
```
# mte_advanced_buildings.txt

mte_grand_trade_hall = {
    # Only buildable if MT mod is active
    can_construct_potential = {
        exists = root.var:mt_owned_trade_posts
        root.var:mt_owned_trade_posts >= 3
    }

    # Boosts existing MT mechanics
    county_modifier = {
        monthly_income = 5
        development_growth = 0.2
    }

    # References MT trade goods
    province_modifier = {
        mt_trade_good_silk = yes
    }
}
```

---

## Scripted Effects Documentation

### Core Merchant Effects

#### `mt_initialize_merchant_effect`

**Scope:** Character
**Purpose:** Initialize a character as a new merchant

**Usage:**
```
character = {
    mt_initialize_merchant_effect = yes
}
```

**Parameters:** None

**Effect:**
- Grants Wandering Merchant trait
- Initializes all merchant variables
- Sets up tracking for routes, reputation, goods

---

#### `mt_upgrade_merchant_level_effect`

**Scope:** Character
**Purpose:** Upgrade merchant to next tier

**Usage:**
```
character = {
    mt_upgrade_merchant_level_effect = yes
}
```

**Effect:**
- Removes current tier trait
- Adds next tier trait
- Updates max routes
- Triggers celebration event

---

### Trade Route Effects

#### `create_trade_route_effect`

**Scope:** Character
**Purpose:** Create a new trade route

**Usage:**
```
character = {
    create_trade_route_effect = {
        origin = scope:origin_county
        destination = scope:destination_county
        good = 1  # Silk
    }
}
```

**Parameters:**
- `origin`: County scope (route start)
- `destination`: County scope (route end)
- `good`: Integer (trade good ID)

**Effect:**
- Creates route in first available slot (0-4)
- Sets route variables (health, profit, good)
- Increments active routes counter

---

#### `calculate_route_profit_effect`

**Scope:** Character
**Purpose:** Recalculate profit for a specific route

**Usage:**
```
character = {
    calculate_route_profit_effect = {
        route_id = 0
    }
}
```

**Parameters:**
- `route_id`: Integer 0-4 (which route)

**Effect:**
- Calculates base profit from distance
- Applies good value multiplier
- Applies health factor
- Subtracts maintenance
- Updates mt_route_X_profit variable

---

### Economy Effects

#### `apply_trade_income_effect`

**Scope:** Character
**Purpose:** Apply monthly income from all routes

**Usage:**
```
character = {
    apply_trade_income_effect = yes
}
```

**Effect:**
- Sums profit from all active routes
- Applies merchant tier bonuses
- Adds gold to character

---

### Debug Effects

See `/common/scripted_effects/mt_debug_effects.txt` for full list.

Key debug effects:
- `mt_debug_become_merchant` - Instant merchant conversion
- `mt_debug_add_gold` - Add 1000 gold
- `mt_debug_force_rank_up` - Skip to next tier
- `mt_debug_create_perfect_route` - Guaranteed profitable route
- `mt_debug_crash_market` / `mt_debug_boom_market` - Manipulate economy

---

## Scripted Triggers Documentation

### Merchant Status Triggers

#### `is_merchant_trigger`

**Scope:** Character
**Returns:** Boolean

**Usage:**
```
trigger = {
    is_merchant_trigger = yes
}
```

**True if:**
- Character has any merchant tier trait

---

#### `can_create_trade_route_trigger`

**Scope:** Character
**Returns:** Boolean

**Usage:**
```
trigger = {
    can_create_trade_route_trigger = yes
}
```

**True if:**
- Is a merchant
- Has available route slot
- Has sufficient gold (50+)

---

### Route Validation Triggers

#### `route_is_profitable_trigger`

**Scope:** Character
**Parameters:** `route_id`
**Returns:** Boolean

**Usage:**
```
trigger = {
    route_is_profitable_trigger = {
        route_id = 0
    }
}
```

**True if:**
- Route exists
- Route profit > 5 gold/month

---

#### `route_is_critical_trigger`

**Scope:** Character
**Parameters:** `route_id`
**Returns:** Boolean

**Usage:**
```
trigger = {
    route_is_critical_trigger = {
        route_id = 0
    }
}
```

**True if:**
- Route exists
- Route health < 30

---

## Variable Reference

### Character Variables

| Variable | Type | Range | Purpose |
|----------|------|-------|---------|
| `mt_active_routes` | Integer | 0-999 | Number of active trade routes |
| `mt_max_trade_routes` | Integer | 1-999 | Maximum routes allowed (tier-based) |
| `mt_reputation` | Integer | -100 to 200 | Merchant reputation score |
| `mt_carrying_goods` | Integer | 0-10 | Goods currently carried (Tier 1) |
| `mt_owned_trade_posts` | Integer | 0-100 | Number of trade posts owned |
| `mt_route_X_node_0` | County | - | Route X origin county |
| `mt_route_X_profit` | Integer | -50 to 200 | Route X monthly profit (gold) |
| `mt_route_X_health` | Integer | 0-100 | Route X health (100 = perfect) |
| `mt_route_X_good` | Integer | 1-30 | Route X trade good ID |

### Global Variables

| Variable | Type | Range | Purpose |
|----------|------|-------|---------|
| `mt_economy_initialized` | Boolean | - | Economy system is ready |
| `mt_price_silk` | Integer | 40-120 | Current silk market price |
| `mt_price_*` | Integer | varies | Prices for all 30+ goods |
| `mt_economic_state` | Integer | 0-4 | Current economic state |
| `mt_market_trend_luxury` | Integer | -2 to 2 | Luxury goods market trend |
| `mt_supply_luxury` | Integer | 0-100 | Luxury goods supply level |
| `mt_demand_luxury` | Integer | 0-100 | Luxury goods demand level |
| `mt_economic_cycle_year` | Integer | 1-7 | Year in current economic cycle |
| `mt_total_merchants` | Integer | 0-1000 | Total active merchants globally |
| `mt_total_trade_routes` | Integer | 0-10000 | Total active routes globally |

---

## Best Practices

### Naming Conventions

- **Prefix all identifiers** with `mt_` or your mod prefix
- **Use descriptive names:** `mt_silk_trade_route` not `mt_str1`
- **Separate words with underscores:** `mt_create_trade_route`
- **Scope-appropriate suffixes:**
  - `_effect` for scripted effects
  - `_trigger` for scripted triggers
  - `_decision` for decisions
  - `_event` for events

### Performance Considerations

- **Minimize on_action frequency:** Use yearly/monthly, not daily
- **Cache calculations:** Don't recalculate same value multiple times
- **Use triggers wisely:** Early-exit expensive checks
- **Limit scope iterations:** `every_player` is expensive

**Bad:**
```
on_daily_pulse = {
    on_actions = {
        expensive_calculation_for_everyone
    }
}
```

**Good:**
```
on_monthly_pulse = {
    trigger = {
        is_merchant_trigger = yes  # Early exit
    }
    effect = {
        # Only runs for merchants, once per month
    }
}
```

### Localization Best Practices

- **One file per feature:** Don't mix decisions and events
- **Consistent key naming:** `mt_decision_name`, `mt_decision_name_desc`, `mt_decision_name_tooltip`
- **Include tooltips:** Every decision/interaction needs a tooltip
- **Flavor text:** Add character to descriptions, this is medieval

### Testing Your Changes

1. **Always test in a new game first**
2. **Check error.log after every test**
3. **Use debug effects to speed up testing**
4. **Test edge cases** (what if variable is missing?)
5. **Test with AI** (do AI merchants work?)

### Version Control

- **Comment your changes** with `# v1.1: Added XYZ`
- **Document breaking changes** clearly
- **Maintain CHANGELOG.md**
- **Test compatibility** with previous saves

---

## Example: Complete New Feature

Let's add a "Merchant Guild" feature:

### 1. Create the Decision

`/common/decisions/mt_guild_decisions.txt`:
```
mt_found_merchant_guild_decision = {
    picture = "gfx/interface/illustrations/decisions/decision_council.dds"
    desc = mt_found_merchant_guild_decision_desc

    is_shown = {
        has_trait = trading_company_head
        NOT = { has_variable = mt_guild_founded }
    }

    is_valid = {
        gold >= 2000
        var:mt_reputation >= 75
    }

    effect = {
        set_variable = { name = mt_guild_founded value = yes }
        remove_gold = 2000
        mt_create_guild_effect = yes
        trigger_event = mt_guild_events.0001
    }

    cost = {
        gold = 2000
    }
}
```

### 2. Create the Effect

`/common/scripted_effects/mt_guild_effects.txt`:
```
mt_create_guild_effect = {
    add_character_modifier = {
        modifier = mt_guild_master
        years = -1
    }

    change_variable = {
        name = mt_reputation
        add = 25
    }

    # Unlock guild decisions
    set_variable = {
        name = mt_guild_decisions_unlocked
        value = yes
    }
}
```

### 3. Create the Event

`/events/mt_guild_events.txt`:
```
namespace = mt_guild_events

mt_guild_events.0001 = {
    type = character_event
    title = mt_guild_events.0001.t
    desc = mt_guild_events.0001.desc

    theme = stewardship

    left_portrait = root

    option = {
        name = mt_guild_events.0001.a
        add_prestige = 100
    }
}
```

### 4. Add Localization

`/localization/english/mt_guild_l_english.yml`:
```yml
mt_found_merchant_guild_decision:0 "Found Merchant Guild"
mt_found_merchant_guild_decision_desc:0 "Establish a formal guild to protect merchant interests."
mt_guild_events.0001.t:0 "The Guild is Founded"
mt_guild_events.0001.desc:0 "Your merchant guild has been officially established!"
mt_guild_events.0001.a:0 "Excellent!"
mt_guild_master:0 "Guild Master"
```

### 5. Test

```
# In console
effect = { mt_debug_set_tier = { tier = 3 } }
effect = { mt_debug_add_gold_rich = yes }
# Then use the decision
```

---

## Getting Help

### Resources

- **CK3 Wiki:** https://ck3.paradoxwikis.com/Modding
- **Paradox Forums:** https://forum.paradoxplaza.com/forum/forums/crusader-kings-iii-user-mods.1070/
- **CK3 Modding Discord:** Search for community Discord servers

### Contributing to MT

If you create something cool:

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request
6. Include documentation

### Reporting Compatibility Issues

If you find a conflict:

1. Identify the conflicting files/systems
2. Document the issue on GitHub
3. Suggest a resolution if possible
4. Test proposed fixes

---

*Happy modding! The merchant empire awaits your creativity.*
