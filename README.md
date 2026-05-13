# pokernow-bot

Chrome extension that plays automated poker on [pokernow.club](https://www.pokernow.club/).

## Overview

A TypeScript Chrome extension that watches pokernow.club, reads the game state from the DOM, and decides on actions (check, call, raise, fold) on the bot's turn. The default strategy lives in `src/ai/ai.ts` and is a simple if-then-else bot; the project is structured so you can drop in your own `getAction(state: State): Action` implementation.

## Stack

- TypeScript
- Webpack
- Chrome Extension APIs (`@types/chrome`)

## Getting started

Requires Node.js (originally built against v14).

```bash
npm install
npm run build
```

Then in Chrome: load `dist/` as an unpacked extension (`chrome://extensions` → Developer mode → Load unpacked).

To use, navigate to a pokernow.club game, click the extension icon, and press "start bot".

To customize behavior, edit or replace `src/ai/ai.ts`. Helpers for common poker logic live in `src/ai/aiUtils.ts` and `src/ai/probabilisticAction.ts`.

## Status

Hobby project, not actively maintained.

## Links

- [pokernow.club](https://www.pokernow.club/)
