# Pokemon Trainer — Teaching Guide & App Blueprint

A web app for 7-year-old twins to learn the Pokemon Trading Card Game (TCG) on iPad.

---

## 1. What We're Building

An interactive, guided iPad web app that teaches kids how to play the Pokemon TCG step by step — from "what is a card?" to playing a real simplified game. No prior knowledge required for the kids or the parent.

**Target audience:** 7-year-olds (can read simple words, short attention span, learn best through play)  
**Device:** iPad (touch-first, large tap targets, landscape orientation)  
**Goal:** Kids can sit down with a real Pokemon deck and play a game after completing the app

---

## 2. The Pokemon TCG — The Essentials

### What's in a Deck
- **60 cards total** per player
- **3 card types:**
  - **Pokemon cards** — your fighters (the characters that battle)
  - **Energy cards** — fuel for attacks (like batteries for your Pokemon)
  - **Trainer cards** — special tools and helpers

### Card Anatomy (what's on a Pokemon card)
- **Name** — the Pokemon's name (e.g., Pikachu)
- **HP** — Hit Points; how much damage it can take before it's knocked out
- **Type** — element (Fire, Water, Grass, Lightning, etc.) — some types are strong against others
- **Attacks** — what the Pokemon can do; costs Energy to use
- **Weakness** — takes extra damage from certain types
- **Retreat Cost** — Energy needed to swap it out for a benched Pokemon

### The Play Area (Board Layout)
```
[OPPONENT]
  Prize Cards (6) | Deck | Discard
  Bench (up to 5 Pokemon)
  [ ACTIVE Pokemon ]
  ---------------------
  [ ACTIVE Pokemon ]
  Bench (up to 5 Pokemon)
  Prize Cards (6) | Deck | Discard
[YOU]
```

- **Active Spot** — one Pokemon fighting at the front
- **Bench** — up to 5 backup Pokemon waiting
- **Prize Cards** — 6 cards set aside at the start; take one each time you knock out an opponent's Pokemon
- **Deck** — your draw pile
- **Discard Pile** — where knocked out/used cards go

---

## 3. How to Play — Step by Step

### Setup (do this before the game starts)
1. Shuffle your 60-card deck
2. Draw **7 cards**
3. Find a **Basic Pokemon** in your hand — place it face-down in the Active Spot
4. Place up to **5 more Basic Pokemon** face-down on your Bench
5. Put the top **6 cards** of your deck face-down as **Prize Cards**
6. Flip a coin — winner decides who goes first
7. Both players flip their Pokemon face-up — game begins!

> **Kid tip:** "If you don't have any Basic Pokemon in your 7 cards, show your hand to your opponent, shuffle, and draw again!"

### Every Turn — Do These 4 Things (in order)
1. **DRAW** — take 1 card from your deck
2. **DO STUFF** (in any order, as many as you want):
   - Put Basic Pokemon on your Bench
   - Evolve a Pokemon (play Stage 1 on a Basic, Stage 2 on a Stage 1)
   - Attach **1 Energy card** to any of your Pokemon (only once per turn!)
   - Play Trainer cards
   - Retreat your Active Pokemon (pay the retreat cost in Energy)
3. **ATTACK** — use one of your Active Pokemon's attacks (costs Energy shown on card)
4. **END** your turn (attacking ends your turn automatically)

> **Kid tip:** "You can only attach ONE energy card per turn — choose wisely!"

### Winning the Game — 3 Ways to Win
1. **Take all 6 Prize Cards** (knock out 6 of your opponent's Pokemon)
2. **Your opponent runs out of Pokemon** (no Pokemon left in play or hand)
3. **Your opponent can't draw a card** (their deck is empty)

---

## 4. Types — Strengths and Weaknesses

Kids only need to know a few to start:

| Type | Strong Against | Symbol Color |
|------|---------------|--------------|
| Fire 🔥 | Grass, Metal | Red/Orange |
| Water 💧 | Fire | Blue |
| Grass 🌿 | Water | Green |
| Lightning ⚡ | Water | Yellow |
| Fighting 👊 | Lightning, Colorless | Brown/Orange |

**Weakness in the game:** If your Pokemon has a Weakness to the attacker's type, the damage is **×2** (doubled). This is printed on the card.

---

## 5. Teaching Approach — Pedagogy for 7-Year-Olds

### Core Principles
- **Learn by doing, not reading** — interactive steps > text walls
- **Small chunks** — introduce one concept at a time; reinforce before moving on
- **Instant feedback** — animations and audio confirm right/wrong actions
- **Celebrate progress** — rewards, badges, and encouragement keep kids engaged
- **Repetition is good** — repeat key rules across multiple lessons
- **Use characters they know** — Pikachu, Charmander, Squirtle make abstract rules concrete

### Recommended Learning Sequence
```
Module 1: Meet the Cards       (~5 min)
  → What is a Pokemon card?
  → What is Energy?
  → What is a Trainer?

Module 2: The Board            (~5 min)
  → Active spot vs. Bench
  → Prize cards, deck, discard pile

Module 3: Setting Up           (~5 min)
  → Step-by-step guided setup with a practice mini-deck

Module 4: Your Turn            (~10 min)
  → Draw, play, attach Energy, attack
  → Practice one turn at a time

Module 5: Battling             (~10 min)
  → HP and damage
  → Knock Outs and Prize Cards
  → Types and Weakness

Module 6: Play a Full Game     (~15 min)
  → Guided game vs. simple AI with hints
  → All rules in play
```

### UI/UX Guidelines for iPad
- **Big, colorful tap targets** — buttons at least 60x60pt
- **Landscape mode** — mirrors real card game table layout
- **Drag-and-drop** — let kids drag cards to zones (Active, Bench, Energy)
- **Tooltips on tap** — tap any card to see what it does in plain language
- **Animated tutor character** — a friendly Pokemon (e.g., Pikachu) gives instructions
- **Voice-over** — read instructions aloud (7-year-olds vary in reading ability)
- **No timers** — kids should feel safe to think
- **Undo button** — forgiving; mistakes are part of learning
- **Progress bar per module** — visible accomplishment

---

## 6. Simplified Starter Rules (for first games)

To avoid overwhelming kids, start with these guardrails:

- Use **pre-built starter decks** (Battle Academy decks recommended)
- Skip: **Stadium cards**, **Special Energy**, **Abilities** (for first few games)
- Skip: **GX/V/ex mechanics** initially
- Focus only on: Draw → Attach Energy → Attack → Take Prize Cards

---

## 7. Real-World Recommendations (for the parent)

### Best Starter Products
- **Pokemon TCG Battle Academy** — comes with 3 full decks + tutorial guides; perfect for two players learning together
- **Pokemon TCG Live** (free app, iPad compatible) — digital version with built-in tutorial; great companion to physical cards

### Helpful Official Resources
- [Official Learn to Play page](https://tcg.pokemon.com/en-us/learn/)
- [Quick Start Rules PDF](https://tcg.pokemon.com/assets/img/learn-to-play/getting-started/quick-start-rules/en-us/quick_start_rulebook.pdf)
- [Parents' Guide](https://tcg.pokemon.com/en-us/parents-guide/)

---

## 8. App Modules — Implementation Plan

### Phase 1 — Learn the Cards (MVP)
- **The app must download the complete Base Set (102 cards)** from the Pokemon TCG API at first launch and use these as the practice cards throughout all modules. This gives kids real, recognizable cards (Pikachu, Charizard, Blastoise, etc.) rather than placeholder art.
- Card viewer: tap card type to learn what it does
- Drag-and-drop sorting game: sort cards into Pokemon / Energy / Trainer piles
- Quiz: "What type of card is this?"

### Phase 2 — Learn the Board
- Animated board with labeled zones
- Tap each zone to hear/see its purpose
- Mini-challenge: place cards in the correct zone

### Phase 3 — Practice a Turn
- Step-by-step turn simulator
- Guided prompts: "It's your turn! First, draw a card. Tap your deck!"
- Visual highlights show where to look/tap

### Phase 4 — Play a Game
- Simplified AI opponent using a fixed beginner deck
- Pikachu tutor hints available on demand
- Post-game recap: "You knocked out 2 Pokemon! Here's what you did great..."

---

## 9. Educational Benefits to Reinforce

Playing Pokemon TCG helps kids develop:
- **Reading** — card text, attack names, rules
- **Math** — adding/subtracting HP, damage calculations, counting Energy
- **Strategy & Planning** — which Pokemon to put in Active, when to retreat
- **Sportsmanship** — winning and losing gracefully
- **Memory** — remembering what cards do, tracking prize cards

---

*Sources used in research:*
- [TCG Protectors: Pokemon TCG Rules for Kids & Parents](https://tcgprotectors.com/blogs/pokemon-blog/pokemon-tcg-rules-for-kids-and-parents)
- [Official Pokemon Learn to Play](https://tcg.pokemon.com/en-us/learn/)
- [Official Pokemon Parents Guide](https://tcg.pokemon.com/en-us/parents-guide/)
- [Mama in the Now: The Parents' Guide to Pokemon Cards](https://mamainthenow.com/play-pokemon-cards/)
- [Levels PTCG: How to Play Pokemon Cards — Beginner's Guide](https://levelsptcg.com/how-to-play-pokemon-cards/)
- [Official Pokemon Rulebook (PDF)](https://www.pokemon.com/static-assets/content-assets/cms2/pdf/trading-card-game/rulebook/mew_rulebook_en.pdf)
