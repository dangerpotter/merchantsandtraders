# Changelog

All notable changes to the Merchants and Traders mod will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added
- Comprehensive flavor event system (`mt_flavor_events.txt`):
  - 30+ atmospheric flavor events that bring merchant life to life
  - Travel & Encounters (5 events): Random encounters on the road, beautiful scenery, getting lost
  - People (5 events): Old friends, apprentices, rival merchants, artisans, beggars
  - Goods & Products (5 events): Exotic spices, silk quality, local foods, custom items, wine tasting
  - Rumors & News (5 events): Market opportunities, war news, guild gossip, legendary merchants
  - Personal (5 events): Homesickness, celebrations, reflections, ledger keeping, grand dreams
  - Seasonal (5 events): Winter slowdowns, spring renewal, summer festivals, autumn harvest, year-end accounting
  - Events fire every 6-24 months based on triggers
  - Minor stat changes (stress, gold, prestige, opinion)
  - Character trait interactions and consequences
  - Full localization with atmospheric descriptions

### Planned
- Trade goods system implementation
- Merchant traits and character interactions
- Trade route mechanics
- Economic integration with county system
- Merchant progression system

## [0.1.0] - 2025-11-17

### Added
- Initial project structure for CK3 mod
- Complete directory hierarchy for mod organization:
  - `/common/buildings/` - For future trade buildings
  - `/common/decisions/` - For merchant and trade decisions
  - `/common/character_interactions/` - For merchant interactions
  - `/common/traits/` - For merchant traits
  - `/common/modifiers/` - For trade and economic modifiers
  - `/common/scripted_effects/` - Core scripted effects framework
  - `/common/scripted_triggers/` - Core scripted triggers framework
  - `/common/script_values/` - Core calculation values framework
  - `/common/on_actions/` - For event hooks
  - `/events/` - For trade and merchant events
  - `/localization/english/` - For English text localization
  - `/gfx/interface/icons/` - For custom icons
  - `/gui/` - For custom GUI elements

- `descriptor.mod` with mod metadata:
  - Mod name: "Merchants and Traders"
  - Version: 0.1.0
  - Tags: Gameplay, Economy, Trade
  - CK3 compatibility: 1.12.*

- `README.md` with comprehensive documentation:
  - Mod overview and vision
  - Detailed features list
  - Installation instructions for all platforms
  - Development roadmap through version 1.0.0
  - Contributing guidelines

- Core framework files with extensive documentation:
  - `mt_core_effects.txt` - 15 placeholder scripted effects:
    - Merchant management (initialization, upgrades)
    - Trade route creation and management
    - Trade goods handling
    - Economic calculations
    - Utility and cleanup effects

  - `mt_core_triggers.txt` - 25+ placeholder scripted triggers:
    - Merchant status checks
    - Trade route validation
    - Trade goods checks
    - Economic conditions
    - Geographic and political triggers
    - Utility triggers

  - `mt_values.txt` - 20+ placeholder script values:
    - Merchant progression costs
    - Trade route income and costs
    - Trade goods pricing and supply/demand
    - Economic bonuses and modifiers
    - AI behavior values

- `CHANGELOG.md` for tracking development progress

### Technical Details
- All files follow CK3 scripting conventions
- Consistent naming scheme with `mt_` prefix for all mod content
- Comprehensive inline documentation with TODO markers for implementation
- Clean, organized structure ready for feature development

### Notes
- This is a foundation release with framework only
- No gameplay features are implemented yet
- All scripted effects, triggers, and values are placeholders with detailed comments
- Compatible with CK3 version 1.12.*

---

## Version History

- **0.1.0** (2025-11-17) - Initial project structure and framework
