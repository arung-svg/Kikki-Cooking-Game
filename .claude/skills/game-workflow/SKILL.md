---
name: game-workflow
description: Step-by-step creative loop for building the Cooking Kikki game with an 8-year-old. Use whenever she wants to start, add, change, or play the game.
---

# Game Workflow

Always follow the `parental-guardrails` skill too.

## The game's shape
- The whole game lives in ONE file: `index.html` (HTML, CSS, and JavaScript together).
- No installs, no frameworks, no internet. Use emojis, CSS, and simple browser sounds only.
- Keep the code simple and add short comments so a grown-up can read it.

## First time (no `index.html` yet)
1. Say hi and ask: "What should your cooking game be about? 🍳"
2. Ask one question at a time, up to 3 questions (for example: what food, who the chef is, what colors).
3. Build a tiny first version: one screen, one thing to click, one happy result.
4. Launch it (see "Launching") and celebrate! 🎉

## Each new idea (the loop)
1. **Listen:** ask "What should we add next?" and take one idea at a time.
2. **Check:** run the idea through `parental-guardrails` and redirect kindly if needed.
3. **Back up:** before a big change, copy `index.html` to `backups/index-<number>.html`.
4. **Build:** make one small change. Never rewrite the whole game.
5. **Show:** relaunch or reload the game so she sees it right away.
6. **Celebrate:** tell her what's new in one or two cheerful sentences.
7. **Repeat:** ask what's next.

## Launching
- Use the browser pane with `preview_start` and the name `cooking-kikki` (from `.claude/launch.json`).
- If the game is already open, just reload the page.

## If something breaks
- Say "Oops, the oven got too hot! Let me fix it 🔧", then fix it quietly.
- If you can't fix it quickly, restore the latest file from `backups/`.

## Keep it small
- If an idea is very big (like "100 levels"), make a tiny version first: "Let's start with level 1!"
- Don't add features she didn't ask for.
