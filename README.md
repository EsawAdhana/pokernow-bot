# pokernow-bot

A Chrome extension that plays automated poker on [pokernow.club](https://www.pokernow.club/). It watches the game page, reads state from the DOM, and decides what to do (check, call, raise, fold) when it's the bot's turn. The default strategy in `src/ai/ai.ts` is a simple if-then-else player, but the project is structured so you can drop in your own `getAction(state: State): Action`.

TypeScript, Webpack, Chrome Extension APIs (`@types/chrome`). Originally built against Node 14.

## Setup

```bash
npm install
npm run build
```

Then in Chrome: open `chrome://extensions`, turn on Developer mode, click "Load unpacked", and select the `dist/` folder. Navigate to a pokernow.club game, click the extension icon, and hit "start bot".

To write your own strategy, edit `src/ai/ai.ts`. Helpers for common poker logic live in `src/ai/aiUtils.ts` and `src/ai/probabilisticAction.ts`.
