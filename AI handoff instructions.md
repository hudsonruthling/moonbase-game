# AI handoff instructions

## Project direction

Continue developing **Moon Base Trade-Offs** as an expandable game. New features are welcome, provided they fit the existing game and do not replace its core purpose.

## Preserve the existing game

- Keep the current visual style and visuals exactly the same. This means preserving the retro pixel-art look, existing canvas artwork and animations, palette, typography, UI styling, layout, and responsive/touch presentation.
- Do not redesign, restyle, or replace existing visual elements. Avoid visual changes as part of feature work; if a proposed feature seems to require one, ask first.
- Preserve the game’s core ideals: an accessible, educational lunar-outpost survival game about balancing resources, crew time, science, and radiation risk.
- Keep the existing 12-day mission, resource-management premise, and success/failure goals intact unless the user specifically asks to change them.
- Treat `index.backup.html` as a backup snapshot. Do not edit it when implementing a feature unless explicitly asked.

## Adding features

- New features are encouraged. Prefer additive changes that extend the existing mechanics, choices, interactions, educational content, or replayability without undermining the core game.
- Integrate additions into the current code structure and interaction model. Keep the game playable with both keyboard and touch controls, and keep accessibility in mind.
- Keep the science explanations understandable and distinguish simplified game rules from real-world facts. Do not imply that the game uses live NASA data.
- Avoid unrelated refactors and preserve existing behavior wherever possible.
- Before making a change, identify which files and existing mechanics it affects. Afterward, check that the original layout and artwork remain untouched and that the new feature works alongside the existing game.
- If a requested feature conflicts with these principles or requires changing the visuals or core ideals, ask the user before proceeding.

## Source of truth

Use the current `index.html` as the live game. These handoff notes guide future work; they do not restrict the user from requesting specific changes to the game’s style, visuals, or core mechanics.