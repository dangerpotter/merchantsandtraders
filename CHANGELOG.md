# Changelog

All notable changes to the Merchants and Traders mod will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

## [0.1.0] - 2025-11-17 - Foundation Release

### 🎉 Initial Release

The first playable version of Merchants and Traders! This release establishes the complete foundation for the merchant simulation system with full 4-tier progression, extensive events, GUI integration, and a dynamic global economy.

---

### ✅ Core Systems Implemented

#### Merchant Progression System
- **4 Merchant Tiers** with distinct traits and abilities:
  - Tier 1: Wandering Merchant (1 route max, manual trading)
  - Tier 2: Trade Post Owner (3 routes, prestige generation)
  - Tier 3: Trading Company Head (10 routes, company-wide bonuses)
  - Tier 4: Merchant Prince (unlimited routes, maximum influence)
- **Progression mechanics** with gold, reputation, and route requirements
- **Tier-up celebrations** with unique events for each rank
- **Bankruptcy system** with warnings and recovery mechanics
- **Reputation tracking** affecting opportunities and interactions

#### Trade Goods Economy
- **30+ trade goods** across 4 categories:
  - 12 Luxury Goods (silk, spices, jade, pearls, etc.)
  - 7 Common Luxuries (wine, furs, wool, salt, etc.)
  - 8 Common Goods (grain, timber, iron, fish, etc.)
  - 4 Bulk Goods (stone, clay, rope, tar)
- **Dynamic market pricing** that fluctuates based on supply/demand
- **Regional specializations** for trade goods
- **Income and prestige modifiers** for each good

#### Trade Route System
- **Automated trade route creation** between counties
- **Route profitability calculations** based on:
  - Distance (longer = more profit)
  - Trade good value (luxury > common > bulk)
  - Route health (wars/raids cause disruption)
  - Merchant tier bonuses
- **Route health system** (0-100 scale)
  - Wars reduce health by 20-40 points
  - Raids reduce health by 10-20 points
  - Peace allows +5 recovery per month
  - Caravan guards provide +10 health bonus
- **Monthly income application** from all active routes
- **Route management decisions** (create, cancel, invest, reroute)

#### Global Economy Simulation
- **Market price tracking** for all 30+ trade goods
- **Economic cycles** with 7-year patterns
- **Economic states:** Depression, Recession, Stable, Growth, Boom
- **Market trends** for luxury, common, and bulk goods
- **Supply and demand tracking** (0-100 scale)
- **Monthly and yearly economic pulses** that drive changes
- **Price clamping** to prevent extremes (goods stay in viable ranges)

---

### 📜 Events System (70+ Events)

#### Flavor Events (30+ Events)
**Travel & Encounters (5 events):**
- Desert caravan journeys
- Mountain pass crossings
- Port arrivals
- Beautiful landscapes
- Getting lost adventures

**People (5 events):**
- Old friends and reunions
- Eager apprentices
- Rival merchants
- Master artisans
- Beggars and charity

**Goods & Products (5 events):**
- Exotic spice discoveries
- Silk quality concerns
- Local food sampling
- Custom order opportunities
- Wine tasting experiences

**Rumors & News (5 events):**
- Distant market opportunities
- War impact on trade
- Guild gossip
- Legendary merchant tales
- New trade routes opening

**Personal (5 events):**
- Homesickness on the road
- Trade success celebrations
- Reflection on life choices
- Ledger keeping insights
- Grand merchant dreams

**Seasonal (5 events):**
- Winter trading slowdowns
- Spring renewal and optimism
- Summer trade festivals
- Autumn harvest profits
- Year-end accounting

#### Career Events
- Tier-up celebrations for each rank
- Bankruptcy warnings
- Reputation milestones
- Merchant competition
- Partnership offers

#### Trade Route Events
- Random route complications
- Bandit attacks
- Unexpected profits
- Critical route warnings
- Route recovery notifications

#### Economic Events
- Global market booms
- Economic crashes
- Supply shortages (good-specific)
- Demand surges (regional)
- Economic cycle transitions

#### Political Events
- Guild politics and rivalries
- Ruler relations
- Trade policy changes
- Merchant alliances
- Asset seizures

---

### 🎮 Decisions System (40+ Decisions)

#### Merchant Start Decisions
- Become a Wandering Merchant
- Purchase Trade Goods (variable cost 20-50 gold)
- Sell Trade Goods (profit based on distance/luck)
- Manual trade opportunities

#### Merchant Career Decisions
- Establish Trade Post (Tier 1→2, costs 200 gold)
- Form Trading Company (Tier 2→3, costs 1,000 gold)
- Ascend to Merchant Prince (Tier 3→4, costs 5,000 gold)
- Expand operations
- Manage reputation
- Recover from bankruptcy

#### Trade Route Management
- Create Trade Route (50 gold setup cost)
- Cancel Trade Route (no refund)
- Hire Caravan Guard (30 gold/month)
- Invest in Route Security (100 gold, +10 health)
- Reroute Trade Goods (25 gold, change destination)

#### Ruler Trade Decisions
- Support Local Merchants (100 gold, +opinion)
- Establish Trade Policy (200 gold, county modifiers)
- Tax Merchant Activity (20 gold income, -opinion)
- Build Trade Infrastructure (500 gold, permanent bonus)
- Grant Trade Rights (+opinion modifier)

---

### 🤝 Character Interactions (5 Interactions)

1. **Request Trade Rights** - Merchants ask rulers for trade permission
2. **Negotiate Trade Deal** - Merchant partnerships and alliances
3. **Hire Caravan Guard** - Protect valuable trade routes
4. **Seize Merchant Assets** - Rulers can confiscate merchant wealth (risk/reward)
5. **Offer Merchant Protection** - Rulers protect merchants for benefits

---

### 🖼️ GUI System

#### Merchant Portfolio Window
- Character portrait and stats display
- Active routes summary
- Current reputation score
- Total monthly income from trade
- Merchant tier and progression tracking
- Tooltips for all values

#### Trade Route Management Window
- Visual route creation interface
- Origin and destination county selection
- Trade good selection menu
- Route profitability preview
- Active route management
- Route cancellation options

---

### 📚 Localization (3,750+ Lines)

**14 English localization files:**
- mt_core_l_english.yml (691 lines) - Core game text
- mt_trade_gui_l_english.yml (398 lines) - Trade route GUI
- mt_merchant_gui_l_english.yml (405 lines) - Merchant portfolio GUI
- mt_merchant_career_events_l_english.yml (378 lines) - Career event text
- mt_decisions_l_english.yml (293 lines) - Decision titles and descriptions
- mt_economic_events_l_english.yml (296 lines) - Economic event text
- mt_trade_route_events_l_english.yml (226 lines) - Route event text
- mt_political_events_l_english.yml (201 lines) - Political event text
- mt_merchant_interactions_l_english.yml (183 lines) - Interaction text
- mt_adventurer_start_l_english.yml (136 lines) - Adventurer start events
- mt_interactions_l_english.yml (133 lines) - General interaction labels
- mt_merchant_events_l_english.yml (38 lines) - Merchant life events
- mt_flavor_events_l_english.yml (245 lines) - 30+ flavor event descriptions
- mt_merchant_decisions_l_english.yml (127 lines) - Merchant decision text

**Full coverage for:**
- All events (70+)
- All decisions (40+)
- All interactions (5)
- All GUI elements
- All tooltips
- All notifications

---

### 🔧 Scripted Framework

#### Scripted Effects (6 files, 4,200+ lines)
- mt_core_effects.txt - Merchant initialization, trait management
- mt_progression_effects.txt - Tier-up mechanics, reputation calculation
- mt_route_effects.txt - Route creation, profitability calculations, maintenance
- mt_county_effects.txt - County economic modifiers, development impacts
- mt_economy_effects.txt - Trade income application, economic calculations
- mt_goods_production.txt - Trade good supply and demand mechanics
- **NEW: mt_debug_effects.txt** - Debug and testing tools for modders

#### Scripted Triggers (4 files)
- mt_core_triggers.txt - Merchant status checks, prerequisites
- mt_progression_triggers.txt - Tier-up eligibility, progression gates
- mt_route_triggers.txt - Route validation, profitability checks, security
- mt_goods_triggers.txt - Good production checks, supply/demand evaluation

#### Script Values (2 files)
- mt_values.txt - Merchant progression costs, route income, pricing
- mt_economy_values.txt - Economic calculation values, supply/demand factors

#### On-Actions (3 files)
- mt_adventurer_on_actions.txt - Game start, merchant lifecycle, cleanup
- mt_trade_routes.txt - Route updates, war/raid disruption, recovery
- **NEW: mt_initialization.txt** - Global economy initialization, market setup

---

### 🛠️ Debug & Testing Tools

**Debug Effects (mt_debug_effects.txt):**
- `mt_debug_add_gold` - Add 1000 gold instantly
- `mt_debug_add_gold_rich` - Add 5000 gold
- `mt_debug_add_gold_small` - Add 100 gold
- `mt_debug_become_merchant` - Instant merchant conversion with full setup
- `mt_debug_force_rank_up` - Skip to next merchant tier
- `mt_debug_set_tier` - Set specific tier (1-4)
- `mt_debug_create_perfect_route` - Create guaranteed profitable route
- `mt_debug_crash_market` - Test economic disaster scenarios
- `mt_debug_boom_market` - Test economic prosperity scenarios
- `mt_debug_reset_market` - Reset economy to baseline
- `mt_debug_show_all_variables` - Display all merchant variables in log
- `mt_debug_show_global_economy` - Display global economic state
- `mt_debug_max_reputation` - Set reputation to 100
- `mt_debug_tank_reputation` - Set reputation to -50

---

### 📖 Documentation

**Player Documentation:**
- **README.md** - Comprehensive guide (730+ lines)
  - Complete feature list
  - Installation instructions (Windows/Linux/Mac)
  - How to start as merchant adventurer
  - Full progression guide (Tier 1 through Tier 4)
  - Tips for new players
  - Compatibility notes
  - Troubleshooting section
  - Known limitations
  - Credits and community info

- **NEW: testing_guide.md** - Testing and debugging guide
  - Console commands reference
  - Test scenarios and procedures
  - Common bugs checklist
  - Balance testing guidelines
  - Route verification steps
  - Event system testing
  - Performance testing tips
  - Test report template

**Modder Documentation:**
- **NEW: MODDING_GUIDE.md** - Complete modding reference
  - File structure explanation
  - How to add new trade goods
  - How to add new merchant tiers
  - Hooking into the economy system
  - Creating compatible mods
  - Scripted effects documentation
  - Scripted triggers documentation
  - Variable reference guide
  - Best practices and examples

- **NEW: BALANCING.md** - Economic balancing documentation
  - All gold values for decisions
  - Route profit ranges by tier
  - Event frequencies (MTTH values)
  - AI behavior weights
  - Risk/reward ratio analysis
  - Progression pacing benchmarks
  - Global economy parameters
  - Balancing philosophy
  - Tuning recommendations

---

### 🎯 Key Features Highlights

**For Players:**
- Start as unlanded merchant adventurer
- Build from humble trader to merchant prince
- Create automated trade empire spanning continents
- Experience medieval merchant life through 30+ flavor events
- Adapt to dynamic global economy (booms, crashes, wars)
- Visual GUI for portfolio and route management
- Meaningful progression over 50-100 year campaigns

**For Modders:**
- Clean, well-documented codebase
- Modular file structure
- Extensive debug tools
- Comprehensive modding guide
- Easy to extend with new goods, tiers, events
- Compatible with other economic mods (mostly)

---

### 🔢 Statistics

**Code:**
- **54 total mod files**
- **~43,000+ total lines of code and text**
- **70+ events** across 7 event files
- **40+ decisions** across 4 decision files
- **30+ trade goods** with full properties
- **4 merchant tier traits** with progression
- **5 character interactions**
- **2 custom GUI windows**

**Localization:**
- **14 localization files**
- **3,750+ lines of English text**
- **100% coverage** of all mod content

**Documentation:**
- **6 documentation files**
- **2,500+ lines of documentation**
- Complete player guide
- Complete modder guide
- Complete testing guide
- Complete balancing reference

---

### ⚙️ Technical Details

**CK3 Compatibility:**
- Compatible with CK3 version **1.12.***
- Tested on 1.12.5
- Requires new game for v0.1.0 (save compatibility coming)

**Naming Conventions:**
- All mod content uses `mt_` prefix
- Consistent naming across all files
- No vanilla file modifications
- Clean integration with base game

**Performance:**
- Optimized monthly/yearly pulses
- Minimal performance impact with <10 merchants
- Slight lag possible with 50+ active merchants globally
- Save file increase: ~500KB-2MB with heavy usage

**Known Limitations in v0.1.0:**
- No merchant inheritance (routes lost on death)
- AI merchant behavior basic (optimization coming)
- No trade leagues/alliances yet
- No merchant republics yet
- English localization only

---

### 📝 Credits

**Development:**
- Design & Implementation: Created with assistance from **Claude Code** (Anthropic AI)
- Testing: Community testing ongoing
- Inspiration: Historical medieval trade networks, Hanseatic League, Silk Road

**Special Thanks:**
- Paradox Interactive for Crusader Kings 3
- CK3 modding community for documentation and tools
- Early testers and feedback providers

---

### 🚀 What's Next?

**Planned for v0.2.0:**
- Enhanced regional trade good specialization
- Improved AI merchant behavior
- Additional flavor events (50+ total)
- Trade building system
- Save game compatibility improvements

**Future Versions:**
- v0.3.0: Merchant dynasties and inheritance
- v0.4.0: Advanced route management and automation
- v0.5.0: Trade buildings and infrastructure
- v0.6.0: Trade leagues and alliances
- v0.7.0: Naval trade and piracy
- v1.0.0: Merchant republics, full feature set

---

### 📥 Installation

1. Download from GitHub releases or Steam Workshop (coming soon)
2. Extract to CK3 mod folder
3. Enable in launcher
4. Start new game
5. Wait for merchant start event (3-10 days)
6. Begin your journey!

### 🐛 Reporting Issues

Found a bug? Please report on GitHub Issues with:
- CK3 version
- Mod version (0.1.0)
- Steps to reproduce
- Error log excerpt (if applicable)
- Save file (if applicable)

---

## Version History Summary

- **[0.1.0]** (2025-11-17) - **Foundation Release** - Complete merchant system with 4 tiers, 70+ events, dynamic economy, GUI, 3,750+ lines of localization, full documentation

---

**Thank you for playing Merchants and Traders!**

*May your routes be profitable and your ventures prosperous!*
