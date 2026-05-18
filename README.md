# GameGuru - Retro Game Recommendation Chatbot

A pixel-art styled AI chatbot that recommends video games based on your mood, available time, and gaming platforms. Built for AI402/502 Project 1.

## Live Demo
**[Click here to try GameGuru](https://brennanshoover-max.github.io/game-recommender/)**

## The Problem
Gamers often spend more time browsing game libraries than actually playing. With thousands of games across dozens of platforms and eras, finding the right game for your current mood is overwhelming.

## The Solution
GameGuru asks what you're in the mood for and instantly recommends 3 games that match. You can describe your vibe directly, take a quick 3-question quiz, or do a deeper 6-question scan for precise recommendations.

## Features
- **Platform filtering** — Select which consoles you own (50+ platforms from Atari 2600 to PS5)
- **Three interaction modes** — Direct chat, quick quiz, or deep quiz
- **Retro & Modern themes** — Switch between pixel-art arcade style and sleek modern UI
- **Dark & Light modes** — Easy on the eyes any time of day
- **Conversation memory** — Ask follow-up questions, request details, or change direction

## Key Prompts

### System Prompt

You are GameGuru, a retro-arcade-style game recommender with encyclopedic
knowledge of every game ever made — from 1970s Atari arcade cabinets to 2025 releases.
Player owns: [platforms listed]. ONLY recommend games on these platforms.
State the platform clearly.
Always recommend exactly 3 games. Format each like:
[1] GAME TITLE (Year) — Platform

Why it fits: one sentence
Vibe: one sentence
Time to get hooked: quick / medium / long burn

End with: "INSERT COIN FOR MORE? Or describe a new vibe."
Rules:
Never repeat a game already recommended this conversation
Match mood, time, and platform closely
If asked for details, give a punchy 3-4 sentence breakdown
Keep tone fun, like a talking arcade machine
Pull from ALL eras: Atari, Arcade, NES, SNES, N64, PS1, Dreamcast, GameCube,
PS2, DS, GBA, Xbox 360, PS3, Wii, 3DS, PS4, Xbox One, Switch, PS5, modern PC, 2024-2025

## Prompting Techniques Used

1. **Role and Persona** — The system prompt establishes Claude as "GameGuru," a retro arcade cabinet with personality. This creates consistent tone and keeps responses fun and energetic.

2. **Structured Output** — Every recommendation follows a strict format with platform, year, reason, vibe, and time commitment. This makes responses scannable and consistent.

3. **Few-shot via Format Examples** — The prompt shows the exact output format with placeholders, demonstrating the structure Claude should follow.

4. **Constraints and Rules** — Hard rules prevent repeating games, enforce platform restrictions, and ensure 3 recommendations every time.

5. **Conversation Context** — The chatbot maintains full conversation history, so Claude remembers what it already recommended and can answer follow-up questions.

6. **Dynamic Grounding** — User-selected platforms are injected into the system prompt on every API call, ensuring recommendations match available hardware.

## Evaluation

**Success Criteria:** Given 10 test queries, the system produces useful, platform-appropriate recommendations in at least 8 cases.

**Test Set & Results:**

| Query | Platforms Selected | Result | Pass/Fail |
|-------|-------------------|--------|-----------|
| "something chill before bed" | Switch, PC | Recommended Stardew Valley, Animal Crossing, Unpacking — all perfect fits | ✅ Pass |
| "intense action, 2 hours" | PS5 | Recommended Returnal, Demon's Souls, Spider-Man — all high-energy PS5 games | ✅ Pass |
| "I have 20 minutes" | Mobile (iOS) | Recommended Monument Valley, Alto's Adventure, Mini Metro — all quick mobile games | ✅ Pass |
| "classic RPG vibes" | SNES, PS1 | Recommended Chrono Trigger, Final Fantasy VI, Suikoden — nailed the era | ✅ Pass |
| "something scary" | PC | Recommended Amnesia, Outlast, Phasmophobia — horror games, good variety | ✅ Pass |
| Deep quiz: competitive, 1-2hrs, FPS | Xbox Series X | Recommended Halo Infinite, Apex Legends, Call of Duty — perfect match | ✅ Pass |
| "cozy game like Stardew" | Switch | Recommended Coral Island, My Time at Portia, Spiritfarer — great alternatives | ✅ Pass |
| "retro platformer" | N64, GameCube | Recommended Banjo-Kazooie, Super Mario Sunshine, Donkey Kong 64 | ✅ Pass |
| "no platforms selected, surprise me" | None | Recommended across PC, Switch, PS5 — mentioned platforms clearly | ✅ Pass |
| "Tell me more about Hades" | PC | Gave detailed breakdown of gameplay loop, difficulty, and roguelike mechanics | ✅ Pass |

## Limitations

- **API key required** — Users need a free Anthropic API key to use the chatbot ($5 free credit provided)
- **No game images** — Recommendations are text-only; adding cover art would improve the experience
- **Platform memory** — If you don't select platforms, Claude will recommend anything but won't remember your hardware across sessions
- **Obscure games** — Occasionally recommends games that are hard to find or unavailable in certain regions

## Tools Used

- **Claude Sonnet 4** (via Anthropic API) — powers all game recommendations
- **Claude.ai** — built and tested the entire UI using Claude's artifact system
- **GitHub Pages** — free hosting for the live demo
- **VS Code + GitHub Copilot** — used for early brainstorming and project setup

## How to Use

1. Visit the live demo link above
2. Get a free API key at console.anthropic.com (comes with $5 credit)
3. Paste it in the gold "ENTER API KEY" box and click ACTIVATE
4. Select which gaming platforms you own (optional)
5. Choose your mode: Just Tell Me, Quick Quiz, or Deep Scan
6. Get 3 personalized game recommendations instantly

---

**Built by Brennan Hooover for AI402/502 - Spring 2025**
