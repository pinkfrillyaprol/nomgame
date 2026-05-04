# Nom Knight — Full Game Design Document
> A 3D third-person adventure game. She is the knight. You are the princess. Love is the magic.

---

## Overview

| Field | Detail |
|---|---|
| Engine | Three.js (browser-based, single HTML file to start) |
| Perspective | Third-person 3D |
| Genre | Adventure / turn-based RPG |
| Length | ~30–45 minutes to complete |
| Player character | [HER REAL NAME] — sleek, elegant knight with flowing armor details |
| Captured character | [YOUR REAL NAME] — the princess, taken mid-picnic |
| Villain | The Mon — chaos-dragon-goblin demon |
| Core magic | Nom power — a sacred energy only the knight possesses |

---

## The Sacred Rule — Nom Language

Nom language is a private language between the two characters. It must be treated as sacred throughout the entire game.

- **No NPC ever speaks nom language or references it by name**
- Nom language appears ONLY in: spell names, the nom gauge UI label, and the ending credits music title
- Every time she casts a nom spell it should feel intimate — like whispering something only they know, in the middle of a battle
- The nom language appearing in the credits music title is its only appearance outside of gameplay mechanics — nowhere else in the world, dialogue, or environment

---

## Opening Cutscene — Before Chapter 1

No gameplay. Pure cinematic. This sets everything she is fighting to get back to.

### Beat 1 — The Picnic
- A sunny afternoon. A wide sunlit meadow.
- [HER NAME] and [YOUR NAME] sit together on a blanket with food spread around them.
- Peaceful, warm. No dialogue needed. Just the two of them existing together.
- Camera is gentle — wide shot, then slowly closer.

### Beat 2 — The Shadow Arrives
- Without warning the sky darkens.
- The Mon descends — a horrifying silhouette against the sun. Massive. Wrong.
- Food scatters. The world goes completely silent for exactly one second.

### Beat 3 — The Grab
- The Mon snatches [YOUR NAME] mid-reach for a sandwich.
- No speech. No warning. Just chaos.
- A distant scream fades into the dark sky as the Mon vanishes.

### Beat 4 — She Stands Up
- [HER NAME] is alone in the ruined picnic.
- Close-up on her face.
- She reaches down and picks up her sword — it was lying in the grass beside her the whole time.
- **Title card drops. The game begins.**

> **Developer note:** The picnic blanket should still be visible on the ground at the very start of Chapter 1 before she walks away from it. This costs nothing to implement and will hit hard emotionally.

---

## Combat System — Turn-Based

Combat triggers when the player walks into an enemy in the 3D world. The screen transitions to a turn-based combat view.

### Turn Order
1. Player picks an action (Attack, Nom Spell, Use Item, Defend)
2. Action resolves
3. Enemy takes their turn
4. Repeat until one side reaches 0 HP

### Player Actions
| Action | Description |
|---|---|
| **Sword Strike** | Standard physical attack. Free. Always available. Generates +10 nom gauge. |
| **Nom Spell** | Opens spell submenu showing unlocked spells and their gauge costs. |
| **Use Item** | Opens inventory. Using an item costs the player their turn. |
| **Defend** | Reduces incoming damage by 50% this turn. Generates +5 nom gauge. |

### On Winning a Fight
- Small XP reward
- Chance of herb drop
- Short flavor text line — sometimes funny, sometimes from the enemy
- Nom gauge carries over to the next fight (does NOT reset between battles)

### On Losing a Fight
- Respawn at the last campfire checkpoint
- HP restored to full
- Nom gauge resets to 0

---

## The Nom Gauge — Full Specification

The nom gauge is a bar displayed beneath the player's HP bar during combat. It fills from 0 to 100.

### Visual Design
- Soft glow at low levels
- Brightens and pulses gently at full (100)
- A subtle sound cue plays when it reaches full — something soft, just for her
- Label: use nom language here (e.g. "NOM" or whatever their word is)

### How It Fills
| Trigger | Gauge Gained |
|---|---|
| Sword strike lands | +10 |
| Player takes a hit | +15 |
| Player uses Defend | +5 |
| Regular enemy defeated | +20 |
| Chapter boss defeated | +30 |
| Each turn that passes in combat | +5 |

> **Key design intention:** Taking damage fills the gauge faster than attacking. The harder she struggles, the stronger nom power grows. Pain fuels the magic.

### How It's Spent
| Spell | Cost |
|---|---|
| Nom Spark | 20 |
| Nom Shield | 30 |
| Nom Pulse | 40 |
| Nom Bind | 50 |
| Nom Burst | 100 (full gauge) |

### Carry-Over Rule
The gauge does NOT reset between individual fights. It carries over. A long hard stretch of combat can mean she enters a boss with power already accumulated. This is intentional — it rewards endurance.

The gauge DOES reset to 0 on death/respawn.

---

## Healing System

Healing is never free. Every method has a tradeoff.

### Method 1 — Forage Herbs
- Small glowing plants scattered through each chapter's 3D world
- Collected by walking over them during exploration
- Used from inventory during combat — costs the player their full turn
- Heals **25 HP**
- Maximum **4 herbs** can be carried at once

### Method 2 — NPC Gifts
- Some NPCs give a healing item after their dialogue
- One-time use, cannot be farmed or re-triggered
- Heals **50 HP**
- These are emotional story moments, not a resource system

### Method 3 — Campfire Rest
- One campfire per chapter, placed approximately halfway through
- Resting fully restores HP to maximum
- **Costs 20 nom gauge points** — she gives a little of the magic to heal herself
- This is a real decision: heal now and lose gauge, or push forward and hope

---

## The Nom Spell Arsenal

Spells are unlocked by defeating each chapter's boss. She enters every chapter with the spells she has already earned.

### Sword Strike (always available)
- No gauge cost
- Standard damage
- Generates +10 nom gauge per hit
- The foundation of everything

### Nom Spark (unlocked: end of Chapter 1)
- **Gauge cost: 20**
- Quick directional burst of nom energy
- Fast cast, moderate damage
- Her first instinct — the first time love becomes a weapon
- Good for: general combat, finishing weakened enemies

### Nom Shield (unlocked: end of Chapter 2)
- **Gauge cost: 30**
- Creates a bubble of nom energy that absorbs the next incoming hit completely (100% damage block)
- Visual: a warm soft glow wraps around her like a hug
- Lasts until she takes one hit or the combat ends
- Good for: surviving boss one-shot moves

### Nom Pulse (unlocked: end of Chapter 3)
- **Gauge cost: 40**
- Radial burst of nom energy — hits ALL enemies in range simultaneously
- Knocks every enemy back
- Feels like a scream of pure determination
- Good for: crowd control, grouped enemies

### Nom Bind (unlocked: end of Chapter 4)
- **Gauge cost: 50**
- Chains of nom energy root one target in place for **2 full turns**
- Enemy cannot move or attack while bound
- Good for: setting up combos, neutralizing high-threat enemies

### Nom Burst (unlocked: entering Chapter 5)
- **Gauge cost: 100 (full gauge)**
- The ultimate spell. Cannot be cast until gauge is completely full.
- Screen flashes white. A moment of silence.
- Massive damage to everything in range
- Reserved for The Mon
- The whole game has been building to this one cast

---

## Chapter 1 — The Verdant Vale

**Environment:** She starts exactly where the picnic was — the same meadow, now empty and strange. The world has already changed around her absence.

**Visual tone:** Sunlit forest turning dark at the edges. Mossy ruins. Fireflies at dusk. Ancient trees. The picnic blanket is still on the ground at the very start of the chapter.

**Enemies:** Forest imps, corrupted deer, vine creatures. Tutorial difficulty. They taunt her for thinking one person with a sword can do anything.

**Campfire location:** Halfway through — a small clearing with a warm fire, safe from enemies.

**Nom spell unlocked:** Nom Spark (after defeating the chapter boss)

**NPC — Perrin the Chronicler**
- Location: Near the ruined picnic, early in the chapter
- Role: Teaches the combat system (tutorial NPC)
- Dialogue: *"I saw what happened. I couldn't stop it. But I can show you how to fight. The princess left no note — only the feeling that someone who loves them very much will come. I suppose that's you."*

---

### Chapter 1 Boss — The Warden of Distance

**What it represents:** The physical distance that once kept them apart. The miles. The waiting. The ache of being far away.

**Appearance:** A towering stone giant wreathed in cold mist. Slow and crushing.

**Signature attack:** Literally drags her backward across the arena — she loses ground and has to close distance again.

**Other attacks:** Mist slam (heavy damage, telegraphed slowly), cold breath (reduces nom gauge gain by half for 2 turns)

**Weakness:** Nom Spark breaks his mist shell and exposes him to full damage

**Defeat:** He crumbles slowly. The mist clears. The world feels a little less cold.

---

## Chapter 2 — The Drowned Dungeon

**Environment:** A flooded underground labyrinth. Half-submerged corridors. Beautiful and melancholy. She finds the first letter from [YOUR NAME] here.

**Visual tone:** Bioluminescent water, ancient statues of forgotten rulers, echoing silence broken only by drips and distant rumbles.

**Enemies:** Water shades, dungeon crawlers, lost soldiers still guarding posts for a kingdom that no longer exists. More aggressive than Chapter 1. They try to disorient her.

**Campfire location:** A dry alcove above the water line, midway through.

**Letter from [YOUR NAME] — Letter 1:** Pinned to a stone pillar. She left it knowing the knight would come.
> **[YOU WRITE THIS.] Make it feel like something you'd actually leave for her to find.**

**Nom spell unlocked:** Nom Shield (after defeating the chapter boss)

**NPC — Willa the Nervous Witch**
- Location: A small dry room she's made into a home, deep in the dungeon
- Role: Gives a healing herb, hints at the path forward
- Dialogue: *"I've lived down here twenty years and I still get lost. You'll be fine. Probably. You have that look about you."*

---

### Chapter 2 Boss — The Tide of Doubt

**What it represents:** The moments of uncertainty. The times either of them wondered if it was going to be okay.

**Appearance:** A writhing mass of dark water that forms a vaguely human silhouette. Never fully solid. Always shifting.

**Behavior:** Whispers during the fight. The whispers don't say specific words — just a low murmur that fills the room. Unsettling.

**Attacks:** Flood of shadow (reduces player vision for 2 turns), doubt wave (hits for moderate damage and temporarily lowers attack power), reform (if not defeated fast enough, heals itself once)

**Weakness:** Nom Shield is key — absorb its big attacks and counter hard

**Defeat:** The water stills. The whispers stop. The dungeon feels quieter.

---

## Chapter 3 — The Ashen Wastes

**Environment:** A volcanic badlands. Cracked earth, ember skies, slow rivers of lava. For the first time, the Mon's castle is visible as a dark spire on the horizon.

**Visual tone:** Ash falls like snow. Charred ruins of a once-great kingdom. The castle in the distance grows slightly larger as she moves through the chapter.

**Enemies:** Lava golems, fire imps, scorched knights. Fast and aggressive. Hit harder than anything she's faced. The world knows she's getting close.

**Campfire location:** Inside a crumbled stone archway, sheltered from the ash.

**Letter from [YOUR NAME] — Letter 2:** Written in the ash on a crumbled wall. Still legible.
> **[YOU WRITE THIS.] She's halfway there. What does that deserve?**

**Nom spell unlocked:** Nom Pulse (after defeating the chapter boss)

**NPC — Old Bram**
- Location: Sitting alone in the ruins of what was once a home
- Role: Gives a healing item. Most emotionally weighted NPC in the game.
- Dialogue: *"Everyone I loved burned with this place. You still have yours out there. Don't you dare stop walking."*

---

### Chapter 3 Boss — The Ember of Anger

**What it represents:** The hard moments. Fights. Frustration. The times things got heated. Not evil — just hurt and burning.

**Appearance:** A raging fire elemental. Tall, unstable, furious. Cracks of bright orange light along its body.

**Behavior:** The most aggressive boss so far. Attacks relentlessly. But there are moments — brief pauses — where it seems to hesitate.

**Attacks:** Fire slam (high damage, wide area), ember storm (hits multiple times, each hit small but the chain adds up), heat wave (reduces her max HP temporarily)

**Special mechanic:** When brought below 25% HP it stops attacking for one full turn. A visual of it trembling. Then the fight resumes — this is the emotional beat.

**Defeat:** It doesn't shatter violently. It slowly dims. The arena cools. The ash stops falling for a moment.

> **Developer note:** This boss should feel like resolution, not destruction. The dimming animation matters.

---

## Chapter 4 — The Shadow Spires

**Environment:** The outer walls and towers of the Mon's domain. Dark architecture with impossible geometry. She is almost there.

**Visual tone:** Twisted black spires, corrupted gardens where plants grow wrong, statues that seem to track movement. The Mon's influence is everywhere. The air itself feels wrong.

**Enemies:** Shadow knights (mirror her moveset), corrupted familiars, Mon-touched creatures. The strongest enemies in the game so far. Some copy her exact fighting style back at her.

**Campfire location:** A small forgotten room behind a collapsed wall — the Mon doesn't know it's there.

**Letter from [YOUR NAME] — Letter 3:** Tucked into the cracked hand of a stone statue near the chapter's midpoint.
> **[YOU WRITE THIS.] She's at the door of his world now. What do you want her to know before she goes in?**

**Nom spell unlocked:** Nom Bind (after defeating the chapter boss)

**NPC — Sable the Deserter**
- Location: Hiding in the forgotten campfire room
- Role: Former soldier of the Mon. Gives information and a healing item.
- Dialogue: *"I served him for years. You want to know what he actually fears? Not armies. Not swords. Just people who refuse to stop loving each other."*

---

### Chapter 4 Boss — The Mirror of Fear

**What it represents:** Self-doubt. The fear of not being enough. The internal voice that says maybe she can't do this.

**Appearance:** An exact copy of the knight. Her face. Her armor. Her weapon. Everything — but corrupted, darkened, wrong.

**Behavior:** Uses her own moves against her. Copies her attack patterns. Fights like she fights.

**Attacks:** Everything the player has done — sword strikes, even the animations. It mirrors her completely.

**Special mechanic:** Looking at it lowers nom gauge gain by 50% — self-doubt weakening the magic. The only counter is to keep attacking anyway.

**Key spell:** Nom Bind is crucial. Root it in place and attack hard. Break the mirror.

**Defeat:** The copy shatters like glass. Each shard fades before hitting the ground. Silence.

> **Developer note:** This is emotionally the hardest fight in the game. The visuals of fighting yourself should feel genuinely uncomfortable. That discomfort is the point.

---

## Chapter 5 — The Mon's Castle

**Environment:** The final fortress. Grand halls. Crumbling throne rooms. A spiral staircase that seems to go up forever. She is so close.

**Visual tone:** Everything from the previous four chapters is echoed here — stone like Chapter 1, dark water in the basement like Chapter 2, heat and embers like Chapter 3, impossible architecture like Chapter 4. The Mon's castle is a summary of everything she's already defeated.

**Enemies:** Every enemy type from all four previous chapters appears in harder, corrupted forms. All of them, together, throwing everything at her.

**Campfire location:** The base of the spiral staircase. The last rest before the top.

**Letter from [YOUR NAME] — Letter 4 (the last one):** On the door at the very top of the spiral staircase. She has to read it before she can enter.
> **[YOU WRITE THIS.] This is the last thing she reads before she faces The Mon. Make it count.**

**Nom spell unlocked:** Nom Burst (upon entering the castle — she feels it, the full power available for the first time)

**NPC — The Handmaiden**
- Location: Just inside the castle entrance
- Role: Survived the Mon's castle somehow. Gives the player Letter 4 directions and a final healing item.
- Dialogue: *"She left something for you. At the top. She knew you'd make it. She always knew."*

---

### Final Boss — The Mon

**What it represents:** Everything that ever tried to keep them apart. Distance. Doubt. Anger. Fear. All of it, given one horrific body.

**Appearance:** A chaos-dragon-goblin demon. Enormous. Wrong in every dimension. Makes sounds that shouldn't exist.

---

#### Phase 1 — Goblin Chaos
- The Mon is small, fast, erratic
- Darts around the arena constantly
- Attacks from unexpected angles, hard to predict
- Attacks: frantic swipes, bite attacks, chaos bolts (random trajectory)
- Transition to Phase 2: brought below 66% HP

#### Phase 2 — Dragon Form
- The Mon swells to massive size
- Slow, deliberate, devastating
- AOE fire breath, shadow slam, wing gust (pushes her back across the arena like Chapter 1's boss)
- Can hit multiple times per turn
- Transition to Phase 3: brought below 33% HP

#### Phase 3 — True Form
- The Mon becomes a writhing amalgam of all three forms — goblin speed, dragon size, chaotic unpredictability
- Attacks pull from both previous phases, mixed and escalated
- The arena itself begins to shake
- **Only Nom Burst at full gauge (100) can end Phase 3**
- If she doesn't have full gauge yet, she must build it while surviving Phase 3
- When Nom Burst lands: screen goes white, silence, then the damage resolves, the Mon screams, and falls

**Defeat:** The Mon collapses. The castle begins to shake. Debris falls. She runs.

---

## The Ending

### The Run
- No combat. Just running.
- The castle is collapsing around her.
- She reaches the base of the spiral staircase and runs up.

### The Door
- The door at the top. Light underneath it.
- She pushes it open.

### The Cutscene
- [YOUR NAME] is there.
- Simple. Just the two characters.
- [YOUR NAME] speaks. **You write every word.**
- The words you write here are the most important writing in the entire game.

### Credits
- Her name: **"The Knight Who Made It"**
- Your name: **"Worth Every Step"**
- The ending theme music title: **[NOM LANGUAGE WORD HERE]**
  - This is the only place nom language appears outside of spell names and the gauge UI
  - Nowhere else in the entire game
  - Sacred. Untouched by the world.

---

## NPC Roster — Complete

| Name | Location | Role | Tone |
|---|---|---|---|
| Perrin the Chronicler | Ch. 1 — near ruined picnic | Tutorial, first encouragement | Warm, gentle |
| Willa the Nervous Witch | Ch. 2 — dry room in dungeon | Hints + herb gift | Funny, endearing |
| Old Bram | Ch. 3 — ruins of his home | Emotional gut-punch, healing gift | Quiet, heavy |
| Sable the Deserter | Ch. 4 — hidden campfire room | Intel + healing gift | Weathered, honest |
| The Handmaiden | Ch. 5 — castle entrance | Final letter delivery, healing gift | Tender, certain |
| [YOUR REAL NAME] | Top of the tower | The ending | **You write this entirely** |

---

## Player-Written Content — Everything You Need to Fill In

Before giving this document to an LLM to code, fill in the following:

1. **[HER REAL NAME]** — the knight's name, appears on title screen and in dialogue
2. **[YOUR REAL NAME]** — the princess's name, appears in all dialogue and letters
3. **Letter 1** (Ch. 2 dungeon pillar) — what you left for her to find
4. **Letter 2** (Ch. 3 ash wall) — what she deserves to read halfway there
5. **Letter 3** (Ch. 4 statue's hand) — what you want her to know before she enters his world
6. **Letter 4** (Ch. 5 door at the top of the stairs) — the last thing before the final fight
7. **The ending dialogue** — what [YOUR NAME] says when she opens that door
8. **The credits music title** — the nom language word that appears once and only once

---

## Tech Recommendations for Vibe Coding

- **Engine:** Three.js — runs entirely in the browser, no install needed, great for 3D third-person
- **Combat:** Handle as a 2D overlay UI on top of the 3D scene (like classic Pokémon) — cleaner to code than 3D combat
- **Models:** Start with simple geometric shapes (capsule for the knight, box for enemies) — add proper models later if you want
- **Dialogue:** Store all NPC lines in a plain JS object — easy to edit without touching game logic
- **Save state:** localStorage for chapter progress and inventory
- **Audio:** Tone.js for simple sound effects and music if you want in-browser audio

### Suggested Build Order

**Phase 1 — Get her moving**
- Three.js scene with a ground plane and basic lighting
- Third-person camera that follows the player
- Knight model (start with a capsule) + WASD movement
- Sword swing animation + a basic enemy with HP
- Nom gauge UI bar (fills on hit/attack/turn)

**Phase 2 — Make it a game**
- Turn-based combat overlay (triggered on enemy collision)
- Nom Spark spell + gauge spending logic
- Herb inventory system + campfire heal
- NPC dialogue system (click to advance text boxes)
- Chapter 1 environment + Warden of Distance boss fight
- Chapter transition screen

**Phase 3 — Add the heart**
- All 5 chapters + environments
- All 5 bosses including three-phase Mon
- Full nom spell arsenal (all 5 spells)
- Opening picnic cutscene
- All letters (you write the content)
- All NPC dialogue (you write the content)
- Ending cutscene + credits roll

---

## Prompting Tips for Your LLM

When vibe coding section by section, feed the relevant chapter section + the combat system section + the tech recommendations together. Good starting prompt:

> *"I'm building a 3D third-person browser game in Three.js. Here is the full game design document: [paste this file]. Start with Phase 1: set up a Three.js scene with a ground plane, a third-person follow camera, a capsule mesh as the player character, WASD movement, and a nom gauge UI bar at the bottom of the screen that fills when I press a test key. No combat yet — just get her moving."*

Then build section by section from there.

---

*This game is a love letter. Build it like one.*