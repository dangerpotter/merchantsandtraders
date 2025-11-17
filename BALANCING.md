# Merchants and Traders - Balancing Documentation

This document provides comprehensive documentation of all economic values, costs, income rates, event frequencies, and balancing decisions in the Merchants and Traders mod.

**Version:** 0.1.0
**Last Updated:** 2025-11-17

---

## Table of Contents

1. [Merchant Tier Progression](#merchant-tier-progression)
2. [Trade Goods Values](#trade-goods-values)
3. [Decision Costs](#decision-costs)
4. [Trade Route Economics](#trade-route-economics)
5. [Event Frequencies](#event-frequencies)
6. [AI Behavior Weights](#ai-behavior-weights)
7. [Risk and Reward Ratios](#risk-and-reward-ratios)
8. [Progression Pacing](#progression-pacing)
9. [Global Economy Parameters](#global-economy-parameters)
10. [Balancing Philosophy](#balancing-philosophy)

---

## Merchant Tier Progression

### Tier 1: Wandering Merchant

**Base Stats:**
- Max Trade Routes: **1**
- Monthly Income Bonus: **+5%**
- Diplomacy: **+2**
- Stewardship: **+0**
- Prestige/Month: **+0**

**Tier-Up Requirements to Tier 2:**
- Gold Required: **200**
- Reputation Required: **20**
- Decision: "Establish Trade Post"
- Recommended Time: **5-10 years**

**Expected Income:**
- Manual Trading: **5-15 gold/month**
- 1 Trade Route: **10-25 gold/month**
- **Total Yearly: 60-180 gold**

---

### Tier 2: Trade Post Owner

**Base Stats:**
- Max Trade Routes: **3**
- Monthly Income Bonus: **+10%**
- Diplomacy: **+3**
- Stewardship: **+1**
- Prestige/Month: **+0.25**

**Tier-Up Requirements to Tier 3:**
- Gold Required: **1,000**
- Reputation Required: **50**
- Owned Trade Posts: **1+**
- Decision: "Form Trading Company"
- Recommended Time: **10-20 years** from Tier 2

**Expected Income:**
- 3 Trade Routes: **30-100 gold/month**
- Trade Post Income: **10-20 gold/month**
- **Total Yearly: 480-1,440 gold**

---

### Tier 3: Trading Company Head

**Base Stats:**
- Max Trade Routes: **10**
- Monthly Income Bonus: **+15%**
- Diplomacy: **+4**
- Stewardship: **+2**
- Prestige/Month: **+0.5**

**Tier-Up Requirements to Tier 4:**
- Gold Required: **5,000**
- Reputation Required: **100**
- Active Routes: **10** (recommended)
- Decision: "Ascend to Merchant Prince"
- Recommended Time: **20-40 years** from Tier 3

**Expected Income:**
- 10 Trade Routes: **100-300 gold/month**
- Company Bonuses: **20-50 gold/month**
- **Total Yearly: 1,440-4,200 gold**

---

### Tier 4: Merchant Prince

**Base Stats:**
- Max Trade Routes: **999** (unlimited)
- Monthly Income Bonus: **+20%**
- Diplomacy: **+6**
- Stewardship: **+3**
- Prestige/Month: **+1.0**

**No Further Tier-Up** (Maximum rank)

**Expected Income:**
- 20+ Trade Routes: **250-600 gold/month**
- Empire-Wide Operations: **50-150 gold/month**
- **Total Yearly: 3,600-9,000+ gold**

---

## Trade Goods Values

### Luxury Goods (High Value)

| Good | Base Price | Income Modifier | Prestige Modifier | Regional Specialization |
|------|-----------|-----------------|-------------------|------------------------|
| **Silk** | 80 | +0.15 gold | +0.10 prestige | Asia, Persia |
| **Spices** | 75 | +0.14 gold | +0.09 prestige | India, Southeast Asia |
| **Jade** | 85 | +0.16 gold | +0.11 prestige | China, Mongolia |
| **Pearls** | 90 | +0.17 gold | +0.12 prestige | Persian Gulf, Indian Ocean |
| **Gemstones** | 88 | +0.16 gold | +0.11 prestige | India, Africa |
| **Dyes** | 70 | +0.13 gold | +0.08 prestige | Mediterranean, Levant |
| **Incense** | 65 | +0.12 gold | +0.08 prestige | Arabia, India |
| **Perfume** | 72 | +0.13 gold | +0.09 prestige | Arabia, Byzantium |
| **Ivory** | 78 | +0.14 gold | +0.10 prestige | Africa, India |
| **Amber** | 68 | +0.12 gold | +0.08 prestige | Baltic, Northern Europe |
| **Fine Wine** | 62 | +0.11 gold | +0.07 prestige | France, Italy |
| **Glassware** | 60 | +0.11 gold | +0.07 prestige | Venice, Byzantium |

**Average Luxury Price:** **73**
**Price Range:** **40-120** (with market fluctuations)

---

### Common Luxuries (Medium-High Value)

| Good | Base Price | Income Modifier | Prestige Modifier | Regional Specialization |
|------|-----------|-----------------|-------------------|------------------------|
| **Wine** | 50 | +0.09 gold | +0.05 prestige | Mediterranean |
| **Fur** | 55 | +0.10 gold | +0.06 prestige | Russia, Scandinavia |
| **Wool** | 45 | +0.08 gold | +0.04 prestige | England, Iberia |
| **Leather** | 42 | +0.07 gold | +0.04 prestige | Universal |
| **Salt** | 48 | +0.09 gold | +0.05 prestige | Coast, Mines |
| **Honey** | 46 | +0.08 gold | +0.05 prestige | Forest regions |
| **Wax** | 44 | +0.08 gold | +0.04 prestige | Forest regions |

**Average Common Luxury Price:** **47**
**Price Range:** **25-80** (with market fluctuations)

---

### Common Goods (Medium-Low Value)

| Good | Base Price | Income Modifier | Prestige Modifier | Regional Specialization |
|------|-----------|-----------------|-------------------|------------------------|
| **Grain** | 25 | +0.05 gold | +0.02 prestige | Agricultural regions |
| **Timber** | 30 | +0.06 gold | +0.02 prestige | Forests |
| **Iron** | 38 | +0.07 gold | +0.03 prestige | Mining regions |
| **Copper** | 35 | +0.06 gold | +0.03 prestige | Mining regions |
| **Tin** | 32 | +0.06 gold | +0.02 prestige | Mining regions |
| **Fish** | 28 | +0.05 gold | +0.02 prestige | Coastal regions |
| **Pottery** | 22 | +0.04 gold | +0.01 prestige | Universal |
| **Textiles** | 36 | +0.07 gold | +0.03 prestige | Urban centers |

**Average Common Goods Price:** **31**
**Price Range:** **15-65** (with market fluctuations)

---

### Bulk Goods (Low Value)

| Good | Base Price | Income Modifier | Prestige Modifier | Regional Specialization |
|------|-----------|-----------------|-------------------|------------------------|
| **Stone** | 18 | +0.03 gold | +0.01 prestige | Quarries |
| **Clay** | 12 | +0.02 gold | +0.01 prestige | River valleys |
| **Rope** | 15 | +0.03 gold | +0.01 prestige | Coastal, hemp regions |
| **Tar** | 14 | +0.02 gold | +0.01 prestige | Forests |

**Average Bulk Price:** **15**
**Price Range:** **5-40** (with market fluctuations)

---

## Decision Costs

### Merchant Career Decisions

| Decision | Gold Cost | Prestige Cost | Other Requirements | Cooldown |
|----------|-----------|---------------|-------------------|----------|
| **Become Wandering Merchant** | 50 | - | 8 Stewardship, Adult | - |
| **Purchase Trade Goods** (Tier 1) | 20-50 | - | Wandering Merchant | 30 days |
| **Sell Trade Goods** (Tier 1) | - | - | Carrying goods | 30 days |
| **Establish Trade Post** (T1→T2) | 200 | 50 | 20 Reputation | - |
| **Form Trading Company** (T2→T3) | 1,000 | 100 | 50 Reputation, 1 trade post | - |
| **Ascend to Merchant Prince** (T3→T4) | 5,000 | 250 | 100 Reputation, 10 routes | - |

---

### Trade Route Management Decisions

| Decision | Gold Cost | Requirements | Notes |
|----------|-----------|--------------|-------|
| **Create Trade Route** | 50 | Available route slot | One-time setup cost |
| **Cancel Trade Route** | - | Active route | No refund |
| **Hire Caravan Guard** | 30 | Active route | Monthly cost (auto-renew) |
| **Invest in Route Security** | 100 | Active route, Tier 3+ | One-time, +10 route health |
| **Reroute Trade Goods** | 25 | Active route | Change route destination |

---

### Ruler Trade Decisions

| Decision | Gold Cost | Requirements | Effects |
|----------|-----------|--------------|---------|
| **Support Local Merchants** | 100 | Any ruler | +10 merchant opinion, +5% trade income |
| **Establish Trade Policy** | 200 | Duke+ | County modifiers |
| **Tax Merchant Activity** | - | Any ruler | +20 gold, -15 merchant opinion |
| **Build Trade Infrastructure** | 500 | County capital | Trade post building |
| **Grant Trade Rights** | - | Any ruler | +20 merchant opinion |

---

### Character Interaction Costs

| Interaction | Gold Cost | Opinion Change | Success Chance |
|-------------|-----------|----------------|----------------|
| **Request Trade Rights** | 20 | +5 (if accepted) | 50-80% (based on diplomacy) |
| **Negotiate Trade Deal** | 50 | +10 (mutual) | 40-70% |
| **Hire Caravan Guard** | 30/month | +5 | 90% |
| **Seize Merchant Assets** | - | -50 merchant, +20 gold | 100% (ruler only) |
| **Offer Merchant Protection** | - | +15 merchant | 100% |

---

## Trade Route Economics

### Route Profitability Formula

**Base Profit = (Good Value × Distance Multiplier × Health Factor) - Maintenance**

#### Distance Multiplier

| Distance (counties) | Multiplier | Example Profit (Silk) |
|---------------------|------------|----------------------|
| 1-3 (Local) | 1.0× | 10-15 gold/month |
| 4-7 (Regional) | 1.3× | 15-25 gold/month |
| 8-12 (Long) | 1.6× | 25-40 gold/month |
| 13-20 (Very Long) | 2.0× | 40-60 gold/month |
| 21+ (Continental) | 2.5× | 60-100 gold/month |

#### Health Factor

| Route Health | Profit Multiplier | Notes |
|--------------|------------------|-------|
| 90-100 (Excellent) | 1.0× | Perfect conditions |
| 70-89 (Good) | 0.85× | Minor issues |
| 50-69 (Fair) | 0.65× | Noticeable problems |
| 30-49 (Poor) | 0.40× | Major disruptions |
| 10-29 (Critical) | 0.20× | Barely functional |
| 0-9 (Failed) | 0× | Route closed |

#### Route Health Modifiers

| Condition | Health Change | Duration |
|-----------|---------------|----------|
| **War in route county** | -20 to -40 | Duration of war |
| **Raid in route county** | -10 to -20 | 1-3 months |
| **Bandit attack event** | -5 to -15 | 1-6 months |
| **Low county control** | -5 per month | Ongoing |
| **Caravan guard hired** | +10 | While employed |
| **Peaceful conditions** | +5 per month | Max 100 |
| **Trade agreement** | +15 | While active |

#### Maintenance Costs

| Route Type | Monthly Maintenance | Notes |
|------------|-------------------|-------|
| **Basic Route** | 2 gold | No guards |
| **Guarded Route** | 32 gold | With caravan guard (30 + 2 base) |
| **Premium Route** | 5 gold | Tier 4 routes with infrastructure |

---

### Route Profit Ranges by Tier

#### Tier 1 (Wandering Merchant) - 1 Route Max

| Route Quality | Gold/Month | Gold/Year |
|--------------|-----------|-----------|
| Poor (local, bulk goods) | 5-10 | 60-120 |
| Average (regional, common) | 10-18 | 120-216 |
| Good (long, luxury) | 18-25 | 216-300 |

**Expected Average: 12 gold/month, 144 gold/year**

---

#### Tier 2 (Trade Post Owner) - 3 Routes Max

| Route Quality | Gold/Month (3 routes) | Gold/Year |
|--------------|---------------------|-----------|
| Poor | 15-30 | 180-360 |
| Average | 30-60 | 360-720 |
| Good | 60-90 | 720-1,080 |

**Expected Average: 45 gold/month, 540 gold/year**

---

#### Tier 3 (Trading Company Head) - 10 Routes Max

| Route Quality | Gold/Month (10 routes) | Gold/Year |
|--------------|----------------------|-----------|
| Poor | 50-100 | 600-1,200 |
| Average | 100-200 | 1,200-2,400 |
| Good | 200-350 | 2,400-4,200 |

**Expected Average: 150 gold/month, 1,800 gold/year**

---

#### Tier 4 (Merchant Prince) - Unlimited Routes

| Route Quality | Gold/Month (20 routes) | Gold/Year |
|--------------|----------------------|-----------|
| Poor | 100-200 | 1,200-2,400 |
| Average | 200-400 | 2,400-4,800 |
| Good | 400-750 | 4,800-9,000 |

**Expected Average: 300 gold/month, 3,600 gold/year**

---

## Event Frequencies

### MTTH (Mean Time To Happen)

Events in CK3 use MTTH (Mean Time To Happen) - the average time before an event fires.

#### Flavor Events

| Event Category | MTTH | Expected Frequency |
|---------------|------|-------------------|
| **Travel Events** | 8 months | ~1.5 per year |
| **People Events** | 10 months | ~1.2 per year |
| **Goods Events** | 12 months | ~1 per year |
| **Rumor Events** | 15 months | ~0.8 per year |
| **Personal Events** | 18 months | ~0.7 per year |
| **Seasonal Events** | 6 months | ~2 per year |

**Overall Flavor Event Rate: ~1 event every 1-2 months** for active merchants

---

#### Trade Route Events

| Event Type | MTTH | Trigger Condition |
|-----------|------|------------------|
| **Random Complication** | 20 months | Per active route |
| **Bandit Attack** | 30 months | Per route through low-control counties |
| **Unexpected Profit** | 24 months | Per route through high-development counties |
| **Route Critical Warning** | Instant | Route health < 30 |

**Per-Route Event Rate: ~1 event every 2 years per route**

With 3 routes: ~1.5 events per year
With 10 routes: ~5 events per year

---

#### Economic Events

| Event Type | MTTH | Conditions |
|-----------|------|-----------|
| **Market Boom** | 60 months | 2% base chance per month |
| **Market Crash** | 60 months | 2% base chance per month |
| **Supply Shortage** | 36 months | Regional, specific goods |
| **Demand Surge** | 36 months | Regional, specific goods |
| **Economic Cycle Shift** | 7 years | Yearly pulse |

**Expected Economic Event Rate: ~1 major event every 5 years**

---

#### Career Events

| Event Type | Trigger | MTTH |
|-----------|---------|------|
| **Tier-Up Celebration** | Immediate | On tier upgrade |
| **Bankruptcy Warning** | Immediate | Gold < 10, 2+ failed routes |
| **Reputation Milestone** | Immediate | Reputation reaches 25/50/75/100 |
| **Rival Merchant** | 24 months | Tier 3+ |
| **Partnership Offer** | 18 months | Tier 2+ |

---

### Event Weights and Modifiers

Most events use weighted random selection:

```
random_list = {
    60 = { # Most common outcome (60% chance) }
    30 = { # Less common (30% chance) }
    10 = { # Rare (10% chance) }
}
```

#### Flavor Event Weights

| Outcome Type | Weight | Effective Chance |
|-------------|--------|-----------------|
| Positive (minor) | 40 | 40% |
| Neutral/Flavor | 35 | 35% |
| Negative (minor) | 20 | 20% |
| Rare (very positive/negative) | 5 | 5% |

---

## AI Behavior Weights

### AI Merchant Decision-Making

AI characters with merchant traits will make decisions based on weighted chances:

#### Tier 1 AI Behavior

| Action | Weight | Frequency |
|--------|--------|-----------|
| Purchase goods | 40 | ~monthly |
| Sell goods | 35 | ~monthly (if carrying) |
| Save gold | 20 | Passive |
| Risk investment | 5 | Rarely |

#### Tier 2+ AI Behavior

| Action | Weight | Frequency |
|--------|--------|-----------|
| Create new route | 30 | When slot available |
| Cancel unprofitable route | 40 | If profit < 5 gold/month |
| Hire guard | 20 | If route health < 50 |
| Tier up (if possible) | 50 | High priority |
| Expand operations | 35 | Medium priority |

#### AI Ruler Trade Decisions

| Action | Weight | Notes |
|--------|--------|-------|
| Support merchants | 30 | If high trade income |
| Tax merchants | 25 | If low gold |
| Seize assets | 5 | Rare, if desperate |
| Grant trade rights | 40 | Common, builds relations |

---

## Risk and Reward Ratios

### Decision Risk Analysis

Each decision has an expected value (EV) calculation:

**EV = (Success Chance × Reward) - (Failure Chance × Cost)**

#### High-Risk, High-Reward Decisions

| Decision | Cost | Success Chance | Success Reward | Failure Penalty | EV |
|----------|------|---------------|---------------|----------------|-----|
| **Risky Trade Venture** | 100 gold | 50% | 250 gold | -100 gold | +25 gold |
| **Invest in Rare Goods** | 200 gold | 40% | 600 gold | -200 gold | +40 gold |
| **Speculate on Market** | 50 gold | 60% | 150 gold | -50 gold | +70 gold |

#### Low-Risk, Low-Reward Decisions

| Decision | Cost | Success Chance | Success Reward | Failure Penalty | EV |
|----------|------|---------------|---------------|----------------|-----|
| **Local Trade** | 20 gold | 85% | 35 gold | -5 gold | +22 gold |
| **Stable Route** | 50 gold | 90% | 70 gold | -10 gold | +52 gold |
| **Conservative Investment** | 100 gold | 95% | 120 gold | -20 gold | +95 gold |

### Route Risk Levels

| Risk Level | Setup Cost | Expected Profit | Failure Chance | Notes |
|-----------|-----------|----------------|----------------|-------|
| **Very Safe** (local, stable) | 50 | 10-15/month | 5% | Boring but reliable |
| **Safe** (regional, peaceful) | 50 | 15-25/month | 10% | Good balance |
| **Moderate** (long, some risk) | 75 | 25-40/month | 20% | Most common |
| **Risky** (very long, unstable) | 100 | 40-65/month | 35% | High reward potential |
| **Very Risky** (war zones) | 150 | 65-100/month | 50% | For desperate/bold |

---

## Progression Pacing

### Expected Timeline (Normal Play)

| Milestone | Time from Start | Cumulative Gold Needed | Key Challenges |
|-----------|----------------|----------------------|----------------|
| **Become Merchant** | Day 1-10 | 50 | Initial investment |
| **First Profitable Trade** | Month 1-2 | 70 | Learning mechanics |
| **Tier 1 → Tier 2** | Year 5-10 | 200 | Building capital |
| **First Trade Route** | Year 5-10 | 250 | Route management |
| **3 Active Routes** | Year 8-15 | 400 | Diversification |
| **Tier 2 → Tier 3** | Year 15-30 | 1,000 | Major investment |
| **10 Active Routes** | Year 20-40 | 1,500 | Complex management |
| **Tier 3 → Tier 4** | Year 35-75 | 5,000 | Massive accumulation |
| **Trade Empire (20+ routes)** | Year 50-100 | 10,000+ | Maintenance challenge |

### Speedrun Potential (Optimal Play)

| Milestone | Time from Start | Strategy |
|-----------|----------------|----------|
| **Tier 1 → Tier 2** | Year 2-3 | Aggressive trading, perfect markets |
| **Tier 2 → Tier 3** | Year 7-10 | Max routes immediately, optimize goods |
| **Tier 3 → Tier 4** | Year 20-30 | Risk tolerance, market manipulation |

### Casual Play Expectations

| Milestone | Time from Start | Strategy |
|-----------|----------------|----------|
| **Tier 1 → Tier 2** | Year 10-15 | Learning, mistakes, safe choices |
| **Tier 2 → Tier 3** | Year 30-50 | Gradual expansion |
| **Tier 3 → Tier 4** | Year 75-150 | Long-term goal, may not reach |

---

## Global Economy Parameters

### Market Price Ranges

| Good Category | Min Price | Base Price | Max Price | Volatility |
|--------------|-----------|-----------|-----------|------------|
| **Luxury** | 40 | 60-90 | 120 | High (±30%) |
| **Common Luxury** | 25 | 40-60 | 80 | Medium (±20%) |
| **Common** | 15 | 20-40 | 65 | Low (±15%) |
| **Bulk** | 5 | 10-20 | 40 | Very Low (±10%) |

### Supply and Demand Scale

**Range: 0-100** (50 is equilibrium)

| Supply Level | Demand Level | Price Effect | Notes |
|-------------|--------------|--------------|-------|
| 0-20 (Critical Shortage) | 80-100 (High) | +40% price | Rare, major events |
| 21-40 (Low) | 60-79 (Above Average) | +20% price | Common in booms |
| 41-60 (Normal) | 40-59 (Normal) | ±0% price | Baseline |
| 61-80 (High) | 21-39 (Below Average) | -20% price | Common in recessions |
| 81-100 (Oversupply) | 0-20 (Very Low) | -40% price | Crashes |

### Economic Cycle States

| State | Value | Global Effect | Duration |
|-------|-------|---------------|----------|
| **Depression** | 0 | -30% all prices, -50% trade income | 2-4 years |
| **Recession** | 1 | -15% prices, -20% income | 3-5 years |
| **Stable** | 2 | Baseline | 2-3 years |
| **Growth** | 3 | +15% prices, +20% income | 3-5 years |
| **Boom** | 4 | +30% prices, +50% income | 1-3 years |

**Full Cycle: ~7 years average**

---

## Balancing Philosophy

### Core Principles

1. **Progression Should Feel Rewarding**
   - Each tier unlock is a significant achievement
   - Income scales meaningfully with tier
   - Player feels tangibly more powerful

2. **Risk and Reward Are Balanced**
   - Higher risk = higher potential reward
   - Safe routes still viable, just less profitable
   - Failure should hurt but not devastate

3. **Player Agency Matters**
   - Decisions have meaningful consequences
   - Player can recover from mistakes
   - Multiple viable strategies exist

4. **Economic Simulation Feels Real**
   - Prices fluctuate realistically
   - Wars and events affect trade naturally
   - Supply/demand makes intuitive sense

5. **Not Pay-to-Win**
   - Gold investment helps but skill matters
   - Smart route management > brute force gold
   - Reputation earned through play, not bought

### Comparison to Vanilla CK3

| Aspect | Vanilla CK3 | Merchants & Traders |
|--------|------------|-------------------|
| **Monthly Income (Count)** | 5-15 gold | 10-50 gold (with routes) |
| **Wealth Accumulation** | Slow, from domain | Faster, active trading |
| **Economic Gameplay** | Minimal | Central focus |
| **Trade Mechanics** | Non-existent | Deep simulation |
| **Merchant Characters** | Not viable | Primary playstyle |

**Design Goal:** Merchant gameplay should be **equally viable** to traditional landed play, not strictly better or worse.

### Testing Benchmarks

**Income Targets (to feel balanced):**

| Character Type | Tier | Target Income/Year | Notes |
|---------------|------|-------------------|-------|
| **Small Count** (vanilla) | - | 120-300 gold | Baseline |
| **Wandering Merchant** | 1 | 100-200 gold | Slightly below count |
| **Trade Post Owner** | 2 | 300-600 gold | Equal to count |
| **Trading Company Head** | 3 | 1,000-3,000 gold | Equal to duke |
| **Merchant Prince** | 4 | 3,000-8,000 gold | Competitive with king |

**Progression Speed (to feel balanced):**

| Tier | Vanilla Equivalent | Time Investment |
|------|-------------------|----------------|
| Tier 1 | Unlanded | 0 years |
| Tier 2 | Count | 5-10 years |
| Tier 3 | Duke | 15-30 years |
| Tier 4 | King | 35-75 years |

---

## Tuning Notes

### If Players Report "Too Easy"

1. **Increase tier-up costs** by 25-50%
2. **Reduce route profitability** by 10-20%
3. **Increase event failure chances** by 5-10%
4. **Add more random disruptions** (more bandits, wars)

### If Players Report "Too Hard"

1. **Reduce tier-up costs** by 15-25%
2. **Increase route profitability** by 10-15%
3. **Reduce failure penalties** (less gold lost)
4. **Increase success chances** for risky decisions

### If Players Report "Too Grindy"

1. **Increase base route income** by 20-30%
2. **Reduce tier-up gold requirements** by 25-40%
3. **Add more high-reward events**
4. **Faster reputation gain**

### If Players Report "Too Random"

1. **Reduce MTTH variance** on events
2. **Increase success chances** for decisions
3. **Make routes more stable** (less health fluctuation)
4. **Reduce extreme market swings**

---

## Version History

**v0.1.0 - Initial Balance**

- Base values established through theoretical modeling
- Awaiting player feedback for tuning
- Expected iteration in v0.2.0 based on testing

**Future Balance Changes:**

- Will be documented in CHANGELOG.md
- Major changes will include reasoning
- Community feedback will drive adjustments

---

**Questions or Balance Concerns?**

Please report on GitHub Issues with:
- What feels unbalanced
- Your playstyle (aggressive/conservative)
- Current tier and income
- Suggested adjustment

---

*Balance is an ongoing process. Your feedback helps make the mod better!*
