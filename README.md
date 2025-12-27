[README.md](https://github.com/user-attachments/files/24355430/README.md)
# Skylift Ledger

## What Is This?

Skylift Ledger is a free, single-player, sandbox companion that runs alongside Microsoft Flight Simulator 2024. You play as the owner of a small aviation company — accepting contracts, managing aircraft, hiring staff, building facilities, and (hopefully) turning a profit.

---

## Why Does This Exist?

There are several outstanding career mode software options for modern flight sims, including the one built-in to MSFS24. None of these really hit exactly what I wanted them too -- they were either too restrictive or too finicky for me. So, I decided to build a very simplistic spreadsheet game that runs alongside MSFS24 (or really, any flight sim) that lets you fly however you'd like. Everything in Skylift is adjustable and customizable.

Skylift's biggest perk -- and biggest limitation -- is that it doesn't actually touch your flight sim. Everything is done externally, and is entirely dependent on the user. You do your own planning, your own management, your own reporting. You're not dependent on the program recognizing datapoints inside the flight.

This DOES mean that the player has some more responsibilities. You need to record fuel states, set your own weather, and track potential issues with your aircraft. You're your own evaluator on checkrides and your own customer providing reviews.  

Skylift attempts to model realistic consequences for bad decisions. A rough landing might result in a bad  customer review and some costly repairs to your aircraft. Running out of fuel means explaining that to your insurance company. Buying a jet you can't really afford means dealing with huge lease payments while you scramble for contracts.

Skylift works best when you RPG it a bit. Pick a business model, and develop it. Bush pilot in the wilderness? Helicopter pilot in a big city? Rural charter pilot? Choose your home base, acquire your plane, choose the mission types you want to do, and fly!

---

## How Does It Work?

1. **Skylift sends you contract offers** — charter flights, cargo runs, medical transfers, sightseeing tours
2. **You bid on contracts** and manage your schedule
3. **You fly the mission in MSFS 2024** — for real, in the sim
4. **You come back and tell Skylift how it went** — Did you make it? Use too much fuel? Scratch the paint?
5. **Skylift calculates the consequences** — revenue, reputation, maintenance costs


---

## FAQ

**Is this a mod?**
No. It's a standalone web page that runs in your browser. MSFS doesn't know it exists.

**Do I need to install anything?**
No. Open the HTML file in Chrome/Firefox/Edge, load the airport database once, and play.

**Does it track my actual flights?**
No. You fly in your flight sim, then manually report the results. It is all self-reported. However, the most fun and interesting results come from when you're accurate and honest. 

**Can I cheat?**
Of course. You don't even need to actually fly the flights if you don't want to. You can add money or planes at will. You're completely unrestricted. 

**Is this good for new simmers?**
Probably not. You need to have a basic understanding of what right looks like. That said, the sim provides references for anyone unsure of this, and should be a great learning tool for anyone willing to read a bit. 

**Is this multiplayer?**
You could probably figure out how to do a multiplayer setup (maybe with one pilot serving as a kind of Game Master) but the game doesn't have a dedicated multiplayer feature. 

**Does it cost money?**
No. It's free.

**I'm an actual software developer Can I modify/improve on this?**
Absolutely! I don't care what you do with it, but if you do something cool, please share with me.

**Will it work with other flight sims?**
Sure. The aircraft database is from MSFS2024, but you can add any plane you like. The rest of it is fully sim agnostic. 

**Where's my save data?**
In your browser's local storage. Don't clear your browser data unless you've backed up your save.

**Can I play offline?**
Yes, after you load the airport database once.

**Why 71,000 airports?**
Because that was easier than filtering, and the database wasn't that big. If you want to create a smaller database, altering it is fairly simple: just follow the format in the one provided. Any modern LLM can do it in a few minutes. 

**There are bugs!**
Hell yes there are. Probably lots of them. Please report through GitHub.

**Will development continue?**
Sure! I'm not a professional developer (if that wasn't obvious) and this thing has some clear limitations, but there's still some interesting stuff to be added. 

---

## Who Made This?

Just a simmer who wanted a better career mode. Built with help from Claude (AI assistant) over several weeks of development.

---

## Getting Started

### Setup
1. Download `index.html` and `airports_global.json`
2. Open `index.html` in your browser
3. Select the airport file when prompted
4. Pick **Career Mode** (recommended) or Sandbox
5. Choose your home airport

### Your First Hours (Career Mode)

You have several starting scenarios, or you can build your own. Your first step is to earn your Private Pilot License.

**Step 1: Build flight time**
- Accept **Discovery Flights** and **Training Flights** from your inbox
- These are the only missions available to student pilots
- Fly them in MSFS, report completion, repeat
- You need ~40 hours to qualify for your PPL checkride

**Step 2: Pass your PPL checkride**
- Once you have enough hours, schedule your Private Pilot checkride
- Pass it 
- Now you can fly passengers — but still not for money

**Step 3: Build toward Commercial**
- With your PPL, more mission types open up
- Keep flying, keep logging hours
- You need ~150-250 hours for your Commercial checkride (depending on difficulty settings)

**Step 4: Get your Commercial certificate**
- Schedule and pass your CPL checkride
- **Now you're in business** — you can legally fly for hire
- Charter flights, executive transport, cargo runs — they're all available
- Name your company and start building your reputation

**Step 5: Expand**
- Earn ratings (Instrument, Multi-Engine, Turbine) to unlock more aircraft
- Buy or lease additional planes
- Hire staff pilots to fly missions for you
- Open additional bases
- Work toward your ATP for the big iron

The grind from Student to Commercial takes a while, but you can accelerate this through sliders if you wish. 

---

The full reference guide is in `SKYLIFT_CONTEXT.md` if you want details on every system. That file is optimized for AI assistants, and has been tested with ChatGPT, Gemini, and Claude.

---

*Happy flying.*
