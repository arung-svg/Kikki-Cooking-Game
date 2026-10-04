---
name: session-wrap-up
description: End-of-session routine for Cooking Kikki. Saves the code to GitHub and checks that the Desktop app shows the latest game. ALWAYS use it when anyone says "I am done for today" (or "I'm done", "done for today", "that's all for today"), and also for "save", "bye", "I'll come back later", or when asked to push to GitHub.
---

**Trigger:** whenever someone says **"I am done for today"** (or something that means the same), run every step below. Don't wait to be asked twice.

# Session Wrap-Up 💾

Run this at the end of every session. Also follow `parental-guardrails`, and talk to her kindly and briefly.

## 1. Make sure the game works
- Reload the game in the browser pane (`preview_start` with the name `cooking-kikki`).
- Check `read_console_messages` for errors. If something is broken, fix it first, or restore the latest file from `backups/`.

## 2. Protect her saved game
- Her progress lives in the browser's localStorage (`kikkiSave`, `kikkiRecipes`). It is never in git.
- If you tested anything this session, make sure her real save wasn't changed. Copy the save before testing, then reload the page and restore it afterwards.

## 3. Check the Desktop app shows the latest game
The Desktop app opens `index.html` straight from this folder, so it always uses the newest code. You don't need to copy anything.
- Check that the Desktop shortcut still points here:
  ```powershell
  $s = (New-Object -ComObject WScript.Shell).CreateShortcut("$([Environment]::GetFolderPath('Desktop'))\Cooking Kikki.lnk")
  "$($s.TargetPath) | $($s.Arguments) | $($s.IconLocation)"
  ```
  The arguments should include `--app="file:///C:/Users/arung/OneDrive/Desktop/Kikki/Cooking_Kikki/index.html"`, and the icon should be `app\kikki.ico`.
- If the shortcut is missing or wrong, recreate it from `Cooking Kikki.lnk` in this folder. Ask before writing to the Desktop.
- Tell her: "If the game is open, close it and open it again (or press Ctrl+R) to see the newest version!"
- The app and the Claude preview pane keep separate saved games. Never overwrite the app's save.

## 4. Privacy check before saving to GitHub
- Search the project for personal details (real names, school, address, phone, email, photos). Remove anything you find.
- Remind the grown-up if the GitHub repo is **Public**: they wanted it private. To change it: Settings → Danger Zone → Change visibility.

## 5. Commit
- `git status`, then stage the game and its files: `index.html`, `backups/`, `app/`, `Cooking Kikki.lnk`, `skill-drafts/`, `CLAUDE.md`.
- No git identity is set up on this computer, so commit with:
  `git -c user.name="arung-svg" -c user.email="arung@convrzai.com" commit -m "<what she added today>"`
- Write a commit message that lists the new features from this session, and end it with the attribution line the session asks for.

## 6. Push to GitHub
- The remote is `origin` → `https://github.com/arung-svg/Kikki-Cooking-Game.git`, branch `main`.
- This project's `.claude/settings.json` denies `git push`. Don't work around it. Give the grown-up this one command to run:
  ```bash
  git push
  ```
- If pushing is allowed one day, run `git push` and check that `git status -sb` shows `main...origin/main` with nothing ahead.

## 7. Say goodbye 👋
- Tell her in one or two cheerful sentences that her game is saved, and what she built today.
- Give the grown-up a short note: the commit hash, whether the push still needs to happen, and anything that needs their attention.
