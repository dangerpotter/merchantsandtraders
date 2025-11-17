# Merchants and Traders

A comprehensive merchant and trade route system for Crusader Kings 3.

Transform your CK3 experience with a deep merchant simulation, trade routes, economic events, and a complete progression system from wandering merchant to merchant prince.

**Version:** 0.1.0
**CK3 Compatibility:** 1.12.*
**Status:** Foundation Complete - Ready for Testing

---

## Table of Contents

1. [Overview](#overview)
2. [Features](#features)
3. [Installation](#installation)
4. [How to Play](#how-to-play)
5. [Merchant Progression Guide](#merchant-progression-guide)
6. [Tips for New Players](#tips-for-new-players)
7. [Compatibility](#compatibility)
8. [Known Limitations](#known-limitations)
9. [Troubleshooting](#troubleshooting)
10. [Documentation](#documentation)
11. [Credits](#credits)

---

## Overview

Merchants and Traders transforms the economic landscape of CK3 by introducing a deep and engaging trade system. Play as a merchant adventurer, build trade networks spanning continents, manage economic crises, and rise through the ranks to become a legendary Merchant Prince.

### What Makes This Mod Unique?

- **Complete 4-tier merchant progression system**: From humble trader to economic powerhouse
- **30+ immersive flavor events**: Experience the life of a medieval merchant
- **Dynamic global economy**: Markets boom and crash based on supply, demand, and world events
- **Deep trade route mechanics**: Create profitable routes, manage risks, respond to disruptions
- **Full GUI integration**: Custom windows for merchant portfolio and trade route management
- **Extensive localization**: 3,750+ lines of English text (more languages coming)
- **Built for expansion**: Modular design makes it easy to add new features

---

## Features

### ✅ **Implemented in v0.1.0**

#### Merchant Career System

**4 Merchant Tiers with Full Progression:**

1. **Wandering Merchant** (Tier 1)
   - Individual trader carrying goods manually
   - 1 trade route maximum
   - +5% monthly income, +2 diplomacy
   - Purchase and sell goods decisions

2. **Trade Post Owner** (Tier 2)
   - Established merchant with permanent trading post
   - 3 trade routes maximum
   - +10% monthly income, +3 diplomacy, +1 stewardship, +0.25 prestige/month
   - Can establish trade posts in counties

3. **Trading Company Head** (Tier 3)
   - Merchant guild leader managing multiple ventures
   - 10 trade routes maximum
   - +15% monthly income, +4 diplomacy, +2 stewardship, +0.5 prestige/month
   - Access to company-wide decisions

4. **Merchant Prince** (Tier 4)
   - Economic powerhouse with vast trade empire
   - 999 trade routes (unlimited)
   - +20% monthly income, +6 diplomacy, +3 stewardship, +1 prestige/month
   - Maximum influence and economic power

#### Trade Goods System

**30+ Trade Goods Across Categories:**

- **Luxury Goods**: Silk, spices, jade, pearls, gemstones, dyes, incense, perfume, ivory, amber
- **Common Luxuries**: Fine wine, furs, wool, leather, salt, honey, wax
- **Common Goods**: Wine, grain, timber, iron, copper, tin, fish, pottery, textiles
- **Bulk Goods**: Stone, clay, rope, tar

Each good has:
- Dynamic market prices that fluctuate
- Supply and demand tracking
- Regional specializations
- Income and prestige bonuses

#### Trade Route System

- **Automated monthly income** from established routes
- **Route health system**: Wars, raids, and bandits affect profitability
- **Distance-based profits**: Longer routes = higher potential returns
- **Risk management**: Hire guards, negotiate protection, manage disruptions

#### Events System (70+ Events)

**30+ Flavor Events:**
- Travel experiences (desert caravans, mountain passes, port arrivals)
- People encounters (rival merchants, helpful guides, mysterious strangers)
- Goods discoveries (exotic finds, quality issues, rare opportunities)
- Market rumors (distant markets, trade opportunities)
- Personal moments (homesickness, pride in success)
- Seasonal events (winter trading, summer festivals)

**Trade Route Events:**
- Bandit attacks
- Route complications
- Unexpected profits
- Market changes

**Economic Events:**
- Global market booms
- Economic crashes
- Supply shortages
- Demand surges

**Career Events:**
- Tier-up celebrations
- Bankruptcy warnings
- Reputation changes
- Competition events

#### Character Interactions

5 unique merchant interactions:

1. **Request Trade Rights**: Ask rulers for permission to trade in their lands
2. **Negotiate Trade Deal**: Partner with other merchants
3. **Hire Caravan Guard**: Protect your goods from bandits
4. **Seize Merchant Assets**: Rulers can confiscate wealth (be careful!)
5. **Offer Merchant Protection**: Rulers can protect merchants for benefits

#### GUI System

- **Merchant Portfolio Window**: View your character's stats, routes, income, reputation
- **Trade Route Management Window**: Create, manage, and cancel trade routes visually
- Tooltips for all elements
- Clean, immersive medieval aesthetic

#### Global Economy Simulation

- **Dynamic market prices**: 30+ goods with fluctuating values
- **Economic cycles**: 7-year cycles with booms and recessions
- **Supply and demand**: Global tracking affects prices and opportunities
- **Market trends**: Luxury, common, and bulk goods trend independently
- **Monthly and yearly pulses**: Economy evolves over time

#### Decision System (40+ Decisions)

**Adventurer/Merchant Start:**
- Become a wandering merchant
- Purchase starting trade goods
- Sell goods for profit

**Merchant Career Decisions:**
- Establish trade posts
- Form trading companies
- Expand operations
- Manage reputation

**Route Management:**
- Create new trade routes
- Cancel unprofitable routes
- Invest in route security
- Reroute during disruptions

**Ruler Trade Decisions:**
- Support local merchants
- Establish trade policies
- Tax merchant activity
- Build trade infrastructure

#### Localization

- **14 localization files**
- **3,750+ lines** of English text
- Full coverage: events, decisions, GUI, tooltips, interactions
- Professional medieval flavor
- Additional languages: Community contributions welcome!

---

### 🔮 **Planned for Future Versions**

- Merchant dynasties and inheritance
- Trade leagues and alliances (Hanseatic League-style)
- Piracy and naval trade
- Trade monopolies and embargoes
- Advanced trade buildings
- AI merchant competition
- Historical trade events
- Regional market specialization
- Trade wars and blockades
- Banking and moneylending

---

## Installation

### Method 1: Steam Workshop (Coming Soon)

1. Subscribe to "Merchants and Traders" on Steam Workshop
2. Launch CK3 and enable the mod in the launcher
3. Start a new game (recommended) or load existing save

### Method 2: Manual Installation

1. Download the latest release from the [Releases page](https://github.com/dangerpotter/merchantsandtraders/releases)

2. Extract the mod folder to your CK3 mod directory:
   - **Windows**: `Documents\Paradox Interactive\Crusader Kings III\mod\`
   - **Linux**: `~/.local/share/Paradox Interactive/Crusader Kings III/mod/`
   - **Mac**: `~/Documents/Paradox Interactive/Crusader Kings III/mod/`

3. Copy `descriptor.mod` to the same `mod` directory and rename it to `merchantsandtraders.mod`

4. Launch CK3 and enable "Merchants and Traders" in the launcher

5. Start a **new game** (highly recommended for v0.1.0)

### Verifying Installation

After enabling the mod, you should see:

- New decisions available for appropriate characters
- "Become a Wandering Merchant" event for unlanded/low-tier rulers
- Merchant-related tooltips and UI elements
- No errors in the CK3 error log (`Documents/Paradox Interactive/Crusader Kings III/logs/error.log`)

---

## How to Play

### Starting as a Merchant Adventurer

**Option 1: New Game Merchant Start (Recommended)**

1. Start a **new game** with any unlanded character or low-tier ruler (count or below)
2. Ensure you have:
   - At least 8 stewardship
   - At least 20 gold
   - Adult age
3. Wait 3-10 days for the merchant start event to fire
4. Choose "Yes, I wish to become a merchant" in the event
5. Begin your journey as a **Wandering Merchant**!

**Option 2: Mid-Game Conversion**

1. Play any character with sufficient stewardship (8+) and gold (50+)
2. Find and use the decision "Become a Wandering Merchant"
3. Pay the conversion cost and receive the merchant trait
4. Begin trading!

**Option 3: Console Commands (Testing)**

```
# Open console with ` or ~
effect = { mt_debug_become_merchant = yes }
```

### Your First Steps as a Merchant

**As a Tier 1 Wandering Merchant:**

1. **Accumulate starting capital:**
   - Use the "Purchase Trade Goods" decision (costs 20-50 gold)
   - Travel to another county (optional, increases profit)
   - Use the "Sell Trade Goods" decision (earns 25-75 gold based on distance and luck)

2. **Build reputation:**
   - Complete successful trades (+reputation)
   - Avoid bankruptcy (−reputation)
   - Fulfill trade agreements (+reputation)

3. **Save for your first trade route:**
   - Accumulate ~200 gold
   - Build reputation to 20+
   - Use "Establish Trade Post" decision to reach **Tier 2**

**As a Tier 2 Trade Post Owner:**

1. **Create your first trade route:**
   - Open the Trade Route Management GUI (decision or hotkey)
   - Select origin county (usually your location)
   - Select destination county (farther = more profit)
   - Choose a trade good
   - Confirm creation (costs ~50 gold)

2. **Manage your routes:**
   - Monitor route health (wars and raids damage routes)
   - Hire guards if routes become dangerous
   - Cancel unprofitable routes
   - Create up to 3 total routes

3. **Save for Trading Company:**
   - Accumulate ~1,000 gold
   - Maintain 3 profitable routes
   - Build reputation to 50+
   - Use decision to reach **Tier 3**

**As a Tier 3 Trading Company Head:**

1. **Expand your network:**
   - Create up to 10 trade routes
   - Diversify goods and destinations
   - Establish trade posts in multiple regions

2. **Respond to economic events:**
   - Adapt to market booms and crashes
   - Take advantage of shortages
   - Avoid flooded markets

3. **Build toward Merchant Prince:**
   - Accumulate ~5,000 gold
   - Maintain 10 profitable routes
   - Build reputation to 100
   - Use decision to reach **Tier 4**

**As a Tier 4 Merchant Prince:**

1. **Dominate the economy:**
   - Create unlimited trade routes (up to 999)
   - Span entire map with trade network
   - Influence global markets

2. **Political power:**
   - High prestige from merchant empire
   - Rulers seek your favor
   - Economic influence over realms

3. **Future expansion:**
   - Form trade leagues (coming in future updates)
   - Establish merchant republic (planned)
   - Pass wealth to dynasty (inheritance system planned)

---

## Merchant Progression Guide

### Tier 1 → Tier 2: Wandering Merchant → Trade Post Owner

**Requirements:**
- Gold: 200
- Reputation: 20+
- Time investment: ~5-10 years of manual trading

**Decision:** "Establish Trade Post"

**Unlocks:**
- 3 trade route maximum (up from 1)
- Trade post ownership
- Enhanced diplomatic weight
- Prestige generation

**Strategy:**
- Focus on short, safe manual trades to build capital
- Avoid risky ventures until you have buffer gold
- Build reputation through successful trades
- Don't rush—solid foundation matters

### Tier 2 → Tier 3: Trade Post Owner → Trading Company Head

**Requirements:**
- Gold: 1,000
- Reputation: 50+
- Active routes: Recommend 3 profitable routes
- Time investment: ~10-20 years

**Decision:** "Form Trading Company"

**Unlocks:**
- 10 trade route maximum (up from 3)
- Company-wide decisions
- Enhanced stewardship
- Significant prestige boost

**Strategy:**
- Maximize use of 3 routes before tier-up
- Diversify goods (don't put all routes on same good)
- Monitor market trends—adapt routes to booming markets
- Build war chest before tier-up (expansion costs gold)

### Tier 3 → Tier 4: Trading Company Head → Merchant Prince

**Requirements:**
- Gold: 5,000
- Reputation: 100
- Active routes: Recommend 10+ routes
- Time investment: ~20-40 years

**Decision:** "Ascend to Merchant Prince"

**Unlocks:**
- Unlimited trade routes (999 maximum)
- Peak merchant bonuses
- Maximum political influence
- Legendary status

**Strategy:**
- Aim for quality over quantity (10 excellent routes > 10 mediocre routes)
- Weather at least one economic crisis successfully
- Establish routes on every continent
- Maintain reserves to survive market crashes

---

## Tips for New Players

### Economic Management

1. **Always keep buffer gold**: Never spend your last 100 gold. Unexpected events can bankrupt you.

2. **Diversify your routes**: Don't trade only silk or only grain—spread risk across goods and regions.

3. **Watch for wars**: Wars devastate trade routes. Cancel or reroute when major conflicts start.

4. **Seasonal thinking**: Some goods (like grain) have seasonal demand. Plan accordingly.

5. **Market timing**: Buy goods when markets crash (low prices), sell during booms (high prices).

### Route Management

1. **Start local, expand gradually**: Your first routes should be short and safe. Expand range as you gain experience.

2. **Monitor route health**: Routes below 50 health are barely profitable. Fix or cancel them.

3. **Hire guards for valuable routes**: A 30 gold guard fee is worth it for a 50 gold/month route.

4. **Check profitability monthly**: Markets change. Last month's profit isn't guaranteed this month.

5. **Don't over-expand**: It's better to have 3 excellent routes than 10 mediocre ones.

### Reputation and Risk

1. **Reputation is precious**: Low reputation locks you out of opportunities. Protect it.

2. **Bankruptcy is devastating**: If you go bankrupt, recovery takes years. Avoid at all costs.

3. **High risk = high reward**: Some decisions offer big payoffs but can backfire. Evaluate carefully.

4. **Build relationships**: Use character interactions to gain protection from rulers.

5. **Competition is coming**: Future updates will add rival merchants. Build strong position now.

### Long-term Strategy

1. **Patience pays off**: Merchant progression is a marathon, not a sprint. Don't rush.

2. **Adapt to events**: Economic events can make or break you. Stay flexible.

3. **Think generationally**: (Future feature) Eventually you'll pass wealth to heirs. Build for the future.

4. **Explore the world**: The best trade opportunities are often in distant, exotic lands.

5. **Learn from failure**: If a route fails or you lose money, understand why. Improve next time.

---

## Compatibility

### CK3 Version

- **Required:** CK3 1.12.* or later
- **Tested on:** CK3 1.12.5
- Check `descriptor.mod` for current supported version

### Save Game Compatibility

- **v0.1.0:** Recommend starting **new games** for best experience
- **Existing saves:** May work but merchant system won't initialize fully
- **Future versions:** Working toward full save compatibility

### Mod Compatibility

**Generally Compatible With:**
- Graphical mods (map graphics, UI improvements, etc.)
- Historical flavor mods
- Character appearance mods
- Most localization mods

**Potential Conflicts:**
- Mods that heavily modify economic systems
- Mods that change character interactions extensively
- Mods that alter decision systems
- Other trade/merchant mods

**Known Compatible Mods:**
- (Testing ongoing—please report compatibility findings!)

**Known Incompatible Mods:**
- (None identified yet—please report issues!)

### Testing Compatibility

To test if another mod is compatible:

1. Enable both mods in the launcher
2. Start a new test game
3. Check error log for conflicts: `Documents/Paradox Interactive/Crusader Kings III/logs/error.log`
4. Test basic merchant functions (become merchant, create route, trigger event)
5. Report findings on GitHub issues page

---

## Known Limitations

### v0.1.0 Limitations

1. **No merchant inheritance**: When a merchant dies, routes and goods are lost. Inheritance system planned for v0.3.0.

2. **AI merchants limited**: AI uses system but not optimized yet. Improved AI coming in v0.3.0.

3. **No trade leagues**: Cooperative merchant organizations planned for v0.6.0.

4. **No merchant republics**: Full government type planned for v1.0.0.

5. **Limited trade buildings**: Special trade infrastructure planned for v0.5.0.

6. **No naval trade specifics**: Coastal vs inland routes function similarly. Naval system planned for v0.7.0.

7. **Static regional specialization**: Regions don't dynamically develop new trade goods yet. Planned for v0.4.0.

8. **No trade wars**: Direct merchant conflict planned for v0.8.0.

### Technical Limitations

- **Route limit**: Maximum 999 routes per character (engine limitation)
- **Save file size**: Heavy merchant activity increases save file size by ~500KB-2MB
- **Performance**: Monthly pulses may cause slight lag with 50+ active merchants globally
- **Localization**: Currently English only (community translations welcome!)

---

## Troubleshooting

### Common Issues

**Issue:** Mod doesn't appear in launcher

**Solution:**
- Verify `descriptor.mod` is in the correct `mod` folder
- Ensure mod folder name matches `path` in descriptor
- Try deleting `dlc_load.json` and restarting launcher

---

**Issue:** Events not firing

**Solution:**
- Confirm you started a NEW game (not loaded existing save)
- Check character meets requirements (adult, sufficient stewardship/gold)
- Verify mod is enabled in launcher
- Check error log for script errors

---

**Issue:** GUI windows not opening

**Solution:**
- Clear GUI cache: Delete `gui.cache` from `Documents/Paradox Interactive/Crusader Kings III/`
- Verify localization files loaded correctly
- Check error log for GUI-related errors

---

**Issue:** Trade routes not generating income

**Solution:**
- Verify route health is above 0 (check merchant portfolio)
- Confirm route variables are set (use debug command: `effect = { mt_debug_show_all_variables = yes }`)
- Check that monthly pulse is firing (enable debug logging)

---

**Issue:** Game crashes or freezes

**Solution:**
- Disable all other mods and test with only Merchants and Traders
- Verify CK3 version compatibility
- Check error log for stack traces
- Report crash with save file and error log to GitHub issues

---

**Issue:** Decisions greyed out or unavailable

**Solution:**
- Hover over decision for tooltip explaining requirements
- Verify character has merchant trait (for merchant decisions)
- Check gold and reputation values
- Some decisions have cooldowns—wait and try again

---

### Getting Help

If you encounter issues not covered here:

1. **Check error log:** `Documents/Paradox Interactive/Crusader Kings III/logs/error.log`
2. **Search existing issues:** [GitHub Issues](https://github.com/dangerpotter/merchantsandtraders/issues)
3. **Report new issue:** Include:
   - CK3 version
   - Mod version
   - Steps to reproduce
   - Error log excerpt
   - Save file (if applicable)
   - List of other enabled mods

---

## Documentation

### For Players

- **[TESTING_GUIDE.md](testing_guide.md)**: Comprehensive guide for testing the mod, console commands, debugging
- **[CHANGELOG.md](CHANGELOG.md)**: Version history and feature additions
- **[TODO.md](TODO.md)**: Planned features and community wishlist

### For Modders

- **[MODDING_GUIDE.md](MODDING_GUIDE.md)**: How to extend this mod or create compatible mods
- **[BALANCING.md](BALANCING.md)**: Economic values, costs, income rates, event frequencies
- **File Structure Reference**: In MODDING_GUIDE.md

### For Developers

- **[GitHub Repository](https://github.com/dangerpotter/merchantsandtraders)**: Source code, issues, pull requests
- **Development Branch**: `claude/mt-final-polish-docs-01CGnFtyS21eDSMVWjhHtNNJ`
- **Contributing**: Pull requests welcome! See MODDING_GUIDE.md for standards

---

## Credits

### Development

- **Design & Implementation**: Created with assistance from Claude Code (Anthropic)
- **Testing**: Community testing ongoing
- **Localization**: English (base), community contributions welcome

### Inspiration

- Real medieval trade routes and merchant practices
- Hanseatic League and Italian merchant republics
- Silk Road trade networks
- Venetian and Genoese trading empires

### Special Thanks

- Paradox Interactive for Crusader Kings 3
- CK3 modding community for tools and documentation
- Testers and early adopters for feedback

### Contributing

Contributions welcome in these areas:

- **Bug reports**: GitHub Issues
- **Localization**: Translate to your language!
- **Balance feedback**: What feels too strong/weak?
- **Feature ideas**: What would make the mod better?
- **Code contributions**: Pull requests accepted
- **Testing**: Try it out and report findings

---

## License

This mod is released under the **MIT License**. See [LICENSE](LICENSE) file for details.

You are free to:
- Use the mod
- Modify the mod
- Distribute the mod
- Create derivative works

Please credit "Merchants and Traders" if you use significant portions of this code.

---

## Support the Project

### How You Can Help

- **Play and provide feedback**: Your experience matters!
- **Report bugs**: Help make the mod stable
- **Suggest features**: What do you want to see?
- **Create content**: AARs, videos, guides
- **Spread the word**: Share with friends and community

### Community

- **GitHub**: [dangerpotter/merchantsandtraders](https://github.com/dangerpotter/merchantsandtraders)
- **Issues/Bugs**: GitHub Issues page
- **Discussions**: GitHub Discussions (coming soon)
- **Steam Workshop**: (Coming soon)

---

## Version History

**v0.1.0 - Foundation (Current)**
- Complete 4-tier merchant progression system
- 30+ trade goods with dynamic pricing
- 70+ events (flavor, career, economic, trade route)
- Trade route creation and management
- Custom GUI windows
- Full English localization (3,750+ lines)
- 40+ decisions
- 5 character interactions
- Global economy simulation
- Debug and testing tools

**Upcoming Versions:**
- v0.2.0 - Enhanced trade goods and regional specialization
- v0.3.0 - Merchant AI and dynasty mechanics
- v0.4.0 - Advanced route management
- v0.5.0 - Trade buildings and infrastructure
- v1.0.0 - Full release with merchant republics and trade leagues

---

**Last Updated:** 2025-11-17
**Mod Version:** 0.1.0
**CK3 Compatibility:** 1.12.*

*Safe travels, merchant adventurer. May your routes be profitable and your ventures prosperous!*
