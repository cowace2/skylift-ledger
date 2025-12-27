# SKYLIFT LEDGER — Complete Reference Guide
## Version 0.7.00 | Last Updated: December 2024

> **For AI Assistants:** This document contains everything needed to answer questions about Skylift Ledger. It is comprehensive and self-contained. Do not hallucinate features not described here.

---

## WHAT IS SKYLIFT LEDGER?

Skylift Ledger is a **free, single-player, sandbox companion** that runs alongside Microsoft Flight Simulator 2024 (or any flight sim). It's a business simulation where players manage an aviation company — accepting contracts, managing aircraft, hiring staff, building facilities, and (hopefully) turning a profit.

### Core Concept
- Player receives contract offers via an **email inbox interface**
- Player **flies missions in their flight sim** of choice
- Player **self-reports results** back to Skylift (honor system — no sim integration)
- Game tracks finances, reputation, fleet, staff, and career progression
- **Everything is adjustable and customizable**

### The Honor System
Skylift's biggest perk — and biggest limitation — is that it doesn't touch your flight sim. Everything is done externally and is entirely dependent on the user:
- You do your own flight planning
- You record your own fuel states
- You set your own weather
- You track potential issues with your aircraft
- You're your own evaluator on checkrides
- You're your own customer providing reviews

The most fun and interesting results come from being accurate and honest.

### Play Your Way
Skylift works best when you RPG it a bit. Pick a business model and develop it:
- Bush pilot in the wilderness?
- Helicopter pilot in a big city?
- Rural charter operator?
- Corporate jet service?

Choose your home base, acquire your plane, choose your mission types, and fly!

### Technical Details
- **Single HTML file** (~38,000 lines, runs in any modern browser)
- **No server required** — all data stored in browser localStorage/IndexedDB
- **One external dependency:** `airports_global.json` (71,437 airports worldwide)
- Player loads the HTML, selects the airport database once, then plays
- **Sim agnostic** — aircraft database is from MSFS 2024, but you can add any plane

### What It Is NOT
- NOT connected to any flight sim — player manually reports flight completion
- NOT a flight tracker or flight planning tool
- Does NOT verify if you actually flew the mission
- NOT designed for brand new simmers (you need to know what "right" looks like)

---

## GLOSSARY OF TERMS

| Term | Definition |
|------|------------|
| **Block Time** | Total flight time from engine start to engine shutdown |
| **Book Value** | Current market value of an aircraft based on age and condition |
| **Condition** | Aircraft health percentage (0-100%). Affects reliability and value |
| **Direct Ops** | Fixed per-flight costs (landing fees, handling, oil, consumables) |
| **Grounded** | Aircraft cannot fly due to low condition or overdue maintenance |
| **LOC** | Line of Credit — revolving credit facility for cash flow |
| **MX** | Maintenance |
| **MX Reserve** | Segregated savings account funded by % of flight revenue, used for maintenance |
| **Squawk** | Mechanical issue discovered during pre-flight inspection |
| **TBO** | Time Between Overhaul — hours until major engine service required |
| **XP** | Experience points earned from flights, determines tier progression |

### Pilot Certificates (Career Mode)
| Certificate | Description |
|-------------|-------------|
| **Student** | Starting certificate, limited to training and discovery flights |
| **Private (PPL)** | Can fly passengers but not for compensation |
| **Commercial (CPL)** | Can fly for hire, required for most charter work |
| **ATP** | Airline Transport Pilot, required for airliner category |

### Pilot Ratings
| Rating | Unlocks |
|--------|---------|
| **Night** | Night flying missions |
| **Instrument** | IFR / low visibility missions |
| **Multi-Engine** | Multi-engine piston aircraft |
| **Helicopter** | Rotorcraft |
| **Seaplane** | Amphibious aircraft |
| **Turbine** | Turboprops and jets |

---

## GAME MODES

### Career Mode
- Start as Student Pilot with basic Cessna 172
- Progress through certificates via checkrides
- Unlock aircraft categories as you earn ratings
- Build reputation from zero
- Realistic (adjustable) hour requirements

### Sandbox Mode
- All certificates and ratings unlocked
- Full fleet access
- No progression restrictions
- Good for testing or casual play

---

## GAME SYSTEMS

### 1. CONTRACT & MISSION SYSTEM

**How Contracts Work:**
1. Emails arrive in inbox (configurable rate, default 3/day)
2. Each email is an **inquiry** from a potential client
3. Player opens inquiry → sees mission details
4. Player uses **Bid Calculator** to set price (or accepts fixed rate)
5. Client accepts/rejects/counters based on bid vs market rate
6. Accepted contracts go to **Schedule**
7. Player flies mission in MSFS, then reports completion

**Mission Types (33 total):**

| Category | Missions |
|----------|----------|
| **Sightseeing** | Sightseeing Tour, Discovery Flight, Heli Tour, Thrill Flight |
| **Charter** | Charter Flight, Heli Charter, Executive Transport, Executive Shuttle |
| **Cargo** | General Cargo, Mail Run, Freight Haul, Bush Resupply, Hazmat Transport |
| **Medical** | Medical Transfer, Air Ambulance, Organ Transport, CASEVAC, Heli EMS, Hospital Transfer |
| **Emergency** | Heli SAR, Search Support, Humanitarian |
| **Training** | Training Flight |
| **Specialty** | Aerial Photography, Aerial Survey, Part 135 On-Demand |
| **Events** | Airshow Aerobatics, Airshow Rides, Historical Flight |
| **Utility** | Ferry Flight, Island Hopping, Airport Connect |
| **Custom** | Custom Flight (player-defined) |

**Mission Structures:**
- **Point-to-Point:** Fly from A to B
- **Round Trip:** Fly to destination and return
- **Waypoint:** Fly to coordinates (landmark), orbit, return
- **Ferry:** Reposition aircraft (no payload)

**Client Tiers:**
| Tier | Pay Modifier | Expectations |
|------|--------------|--------------|
| Budget | 0.85x | Price-sensitive, lenient on service |
| Regional | 1.0x | Standard expectations |
| Corporate | 1.15-1.25x | Higher standards, better tips |
| VIP | 1.3-1.5x | Premium service expected |

### 2. FINANCIAL SYSTEM

**Cash Flow:**
- **Revenue:** Flight payments, tips
- **Expenses:** Fuel, operating costs, maintenance, insurance, payroll, loan payments, lease payments

**Accounts:**
| Account | Purpose |
|---------|---------|
| **Cash** | Operating account for all transactions |
| **MX Reserve** | Segregated maintenance savings (0-30% of revenue, player-controlled) |
| **Line of Credit** | Revolving credit, 6% APR default, for cash flow gaps |

**Financial Statements (Ledger Tab):**
- **Balance Sheet:** Assets, Liabilities, Equity
- **P&L:** Revenue vs Expenses (Month / YTD / All-Time)
- **Transaction Log:** Every financial event recorded

**Aircraft Financing:**
- **Loans:** 10-20% down, 5-7 year terms, fixed monthly payments
- **Leases:** Lower monthly cost, no equity, return conditions apply

**Insurance:**
- Monthly premium based on fleet value and aircraft types
- Category multipliers (jets cost more to insure than pistons)
- Clean record discount (no damage reports)
- Experience tier discount

**Owner Compensation:**
- Monthly salary draw (default $4,000)
- Tracked separately from business expenses

### 3. FLEET MANAGEMENT

**75 Aircraft across 14 categories:**

| Category | Examples | Typical Use |
|----------|----------|-------------|
| single_piston | C152, C172, DA40 | Training, sightseeing, basic charter |
| single_piston_hp | SR22, Bonanza, Corvalis | Executive, longer range |
| bush | XCub, Beaver, PC-6 | Remote strips, resupply |
| multi_piston | Baron, DA62, DC-3 | Charter, cargo |
| turboprop | King Air, PC-12, Caravan | Corporate, medical, cargo |
| light_jet | CJ4, Longitude, PC-24 | Executive, medical |
| airliner | A320, B737, B787 | Large charter, freight |
| military_cargo | C-17, A400M | Heavy cargo, humanitarian |
| military_fighter | F/A-18, A-10 | Thrill flights, airshows |
| amphibious | Icon A5, Goose, CL-415 | Island hopping, water ops |
| aerobatic | Extra 330, Pitts | Airshows, thrill flights |
| warbird | P-51, T-6 | Historical flights, airshows |
| helicopter | R66, H125, Chinook | Tours, EMS, SAR |
| specialty | AT-802, Optica | Survey, agriculture |

**Fleet Data Tracked:**
- Condition (0-100%)
- Flight hours
- Hours since inspection / overhaul
- Book value (depreciation by age/condition)
- Current fuel level
- Location (which base)
- MX status (airworthy / needs attention / grounded)
- Active squawks

**Aircraft Market:**
- Browse available listings
- Use Aircraft Broker to request specific models (fee + wait time)
- Add custom aircraft definitions

### 4. MAINTENANCE SYSTEM

**Condition Degradation:**
- Condition decreases with flight hours
- Rate varies by aircraft category (jets degrade faster per hour)
- Low condition = higher squawk chance

**Inspections:**
- **100-Hour Inspection:** Required every 100 flight hours
- **Annual Inspection:** Required yearly
- **Progressive Inspection:** Alternative to 100-hr/annual

**Overhauls:**
- Engine TBO varies by type (1,500-5,000 hours typically)
- Major overhaul resets engine hours and restores condition

**Squawks:**
- Random pre-flight issues based on condition and aircraft age
- Severity: Minor / Moderate / Major / Grounding
- Can be deferred (minor) or must be fixed (grounding)
- Mechanics reduce squawk frequency

**MX Scheduling:**
- Schedule inspections/repairs at your base's MX facility
- Contract out if no in-house capability
- MX takes time (days based on labor hours)

### 5. REPUTATION SYSTEM

**Two Reputation Tracks:**

**1. Experience Tier (Hidden XP)**
| Tier | XP Required |
|------|-------------|
| Rookie | 0 |
| Novice | 500 |
| Journeyman | 2,000 |
| Professional | 5,000 |
| Veteran | 12,000 |
| Master | 25,000 |

XP earned from: completing flights, first-time aircraft/mission bonuses, perfect flights

**2. Customer Rating (Public Stars)**
- 1.0 to 5.0 stars
- Based on customer reviews after flights
- Factors: on-time performance, self-reported flight quality, damage incidents
- Rolling average of recent reviews
- Affects which client tiers approach you

**Reviews:**
- ~30% chance after each flight (configurable)
- Review text generated based on flight outcome
- Stored in review log with client name, route, date

**Tips:**
- Chance of tip after good flights
- Based on client tier, rating, and flight assessment
- 5-20% of flight revenue

### 6. STAFF SYSTEM

**Staff Roles:**

| Role | Function |
|------|----------|
| **Pilot** | Fly missions on your behalf (parallel operations) |
| **Mechanic** | Reduce squawk frequency, perform in-house MX |
| **Ops Officer** | Auto-scheduling, operational efficiency |
| **Marketing** | Reputation bonus, contract value bonus |
| **Accountant** | Financial tracking, tax efficiency |

**Staff Attributes:**
- **Experience Level:** Junior / Mid / Senior / Expert
- **Salary:** Based on role + experience
- **XP:** Staff gain experience over time
- **Specializations:** (Mechanics) Airframe, Powerplant, Avionics

**Hiring:**
- Browse Staff Marketplace
- Candidates refresh periodically
- Pay signing bonus, set salary
- Staff can be terminated (severance pay)

**Payroll:**
- Processed monthly
- Deducted from cash automatically

**Staff Pilots:**
- Assign to missions you don't want to fly yourself
- They earn XP and can gain certificates
- Enables parallel operations (multiple simultaneous flights)

### 7. BASE SYSTEM

**Base Components:**

| Facility | Function |
|----------|----------|
| **Base** | Establishes presence at airport ($25,000) |
| **Hangar** | Aircraft storage, protects from weather |
| **MX Facility** | In-house maintenance capability |
| **Fuel Storage** | Bulk fuel at discount |

**Multi-Base Operations:**
- Establish bases at multiple airports
- Aircraft assigned to home base
- Missions can originate from any base with aircraft
- Positioning flights to move aircraft between bases

### 8. CAREER PROGRESSION (Career Mode)

**Certificate Progression:**
1. **Student Pilot** → Discovery flights, training
2. **Private Pilot (PPL)** → Checkride required, unlocks most GA flying
3. **Commercial Pilot (CPL)** → Checkride required, unlocks flying for hire
4. **ATP** → Checkride required, unlocks airliners

**Rating Progression:**
- Each rating requires minimum hours in category
- Checkride to certify
- Unlocks aircraft requiring that rating

**Checkrides:**
- Scheduled in advance
- Pass/fail based on difficulty setting
- Failed checkrides can be retried

---

## USER INTERFACE

### Main Tabs (Left Panel)
- **Inbox:** Contract inquiries, notifications, alerts
- **Schedule:** Accepted contracts, calendar view

### Right Sidebar Tabs
- **Pilot:** Your certificates, ratings, hours, career stats
- **Ledger:** Financial statements, transactions, loans
- **Fleet:** Your aircraft, market, MX status
- **Company:** Staff roster, bases, reputation, reviews

### Key Modals
- **Bid Calculator:** Set contract price with cost breakdown
- **Pre-Flight:** Weather, fuel, squawk check before departure
- **Post-Flight:** Report flight outcome, fuel used, any issues
- **Staff Marketplace:** Browse and hire candidates
- **Aircraft Broker:** Request specific aircraft models

---

## SETTINGS & DIFFICULTY

### Difficulty Sliders
| Setting | Range | Effect |
|---------|-------|--------|
| Review Frequency | Low / Normal / High | How often customers leave reviews |
| Rating Sensitivity | Forgiving / Normal / Harsh | How much issues affect ratings |
| Hour Requirements | Reduced / Normal / Realistic | Hours needed for certificates |
| Mission Thresholds | Low / Normal / High | Requirements to unlock mission tiers |
| Checkride Difficulty | Lenient / Normal / Strict | Pass/fail rates |

### Financial Multipliers (0.25x to 2.0x)
- Owned Revenue
- Contract Revenue
- Fuel Costs
- Operating Costs
- Interest Rates
- Insurance Costs
- MX Costs
- Squawk Frequency
- Condition Degradation

### Other Settings
- **Emails Per Day:** 1-10 (default 3)
- **Fixed Price Mode:** Skip bidding, accept market rate
- **Auto-Save:** Off / Weekly / Monthly

---

## DATA FILES

### airports_global.json
- **71,437 airports worldwide**
- Includes: small airports, medium airports, large airports, heliports, seaplane bases
- Fields: icao, name, type, city, state, country, region, lat, lon, elevation, runways
- Runway data: length, width, surface type, lighted
- Required for mission generation and navigation

### Regions in Database
| Region | Coverage |
|--------|----------|
| northamerica | US, Canada, Mexico, Caribbean, Central America |
| europe | UK, EU, Scandinavia, Eastern Europe |
| asia | Japan, China, SE Asia, India |
| oceania | Australia, New Zealand, Pacific Islands |
| southamerica | Brazil, Argentina, Chile, Colombia, etc. |
| africa_mideast | Africa, Middle East |

---

## LANDMARKS DATABASE

**1,294 landmarks** for sightseeing/waypoint missions:
- National Parks
- Mountains & Peaks
- Lakes & Rivers
- Cities & Skylines
- Bridges & Monuments
- Natural Wonders

Landmarks have: name, coordinates, type, region, altitude, description

---

## COMMON QUESTIONS

**Q: How do I start playing?**
A: Open the HTML file in a browser, load the airport database when prompted, choose Career or Sandbox mode, select your home base. Career mode has several starting scenarios, or you can build your own.

**Q: Does this connect to MSFS?**
A: No. You fly in your flight sim, then report your results to Skylift. It's entirely self-reported.

**Q: Will it work with other flight sims?**
A: Yes. The aircraft database is from MSFS 2024, but you can add any plane you like. The rest is fully sim agnostic.

**Q: How do I make money?**
A: Accept contract inquiries, fly the missions, report completion. Revenue minus expenses = profit.

**Q: What happens if I crash?**
A: You self-report. If you report damage, it affects your insurance and reputation. The game trusts your honesty.

**Q: Can I cheat?**
A: Yes. You don't even need to actually fly the flights if you don't want to. You can add money or planes at will. You're completely unrestricted.

**Q: Is this good for new simmers?**
A: Probably not. You need to have a basic understanding of what "right" looks like. That said, the game provides references for anyone unsure, and should be a great learning tool for anyone willing to read a bit.

**Q: Is this multiplayer?**
A: You could probably figure out how to do a multiplayer setup (maybe with one pilot serving as a kind of Game Master) but the game doesn't have a dedicated multiplayer feature.

**Q: How do I unlock better aircraft?**
A: Earn ratings (instrument, multi-engine, turbine, etc.) through flight hours and checkrides. Each rating unlocks aircraft categories.

**Q: Can staff fly missions for me?**
A: Yes. Hire pilots, assign them to contracts, and they'll complete missions while you do other things.

**Q: Where is my save data?**
A: Browser localStorage. Clearing browser data will erase your save. Use the in-game backup feature.

**Q: Can I play offline?**
A: Yes, once the airport database is loaded and cached.

**Q: Why 71,000 airports?**
A: Because that was easier than filtering, and the database wasn't that big. If you want a smaller database, altering it is simple — just follow the format in the one provided. Any modern LLM can do it in a few minutes.

**Q: Can I speed up the career grind?**
A: Yes. The grind from Student to Commercial takes a while by default, but you can accelerate it through difficulty sliders.

---

## VERSION HISTORY SUMMARY

| Version | Major Features |
|---------|----------------|
| 0.1.x | Core contract system, email inbox, time management |
| 0.2.x | Full financial system, ledger, loans, leases, bid calculator |
| 0.3.x | Reputation system, customer reviews, insurance |
| 0.4.x | Maintenance system, condition tracking, inspections, squawks |
| 0.5.x | Staff system (pilots, mechanics, support roles), multi-base |
| 0.6.x | Base facilities (hangars, MX shops, fuel storage) |
| 0.7.x | Current version, polish and integration |

---

## KNOWN LIMITATIONS

**Not Implemented:**
- No achievement/milestone tracking system (yet)
- No weather integration with real-world data
- No dedicated multiplayer (though creative setups are possible)
- No mobile-optimized UI

**By Design:**
- No flight sim integration (honor system intentional)
- No real-time flight tracking
- Player is responsible for all reporting and self-evaluation
- Requires basic flight sim knowledge to get the most out of it

---

## TECHNICAL NOTES

- **Save Format:** JSON in localStorage key `skylift_ledger`
- **Airport Cache:** IndexedDB for large airport database
- **Browser Support:** Modern browsers (Chrome, Firefox, Edge, Safari)
- **File Size:** ~38,000 lines HTML, ~17MB airport database

---

*This document is the authoritative reference for Skylift Ledger v0.7.00. If information isn't here, it's not in the game. This file is optimized for AI assistants and has been tested with ChatGPT, Gemini, and Claude.*
