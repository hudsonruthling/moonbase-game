# AI use disclosure

**Project:** Moon Base Trade-Offs (lunar outpost STEM game)  
**Repository:** [`hudsonruthling/moonbase-game`](https://github.com/hudsonruthling/moonbase-game)  
**Game file:** [`index.html`](./index.html)  
**Purpose:** Record AI assistance and human contributions transparently. This is a project disclosure, not legal advice or a claim that the project meets every event rule.

## AI tools used

The project has used more than one AI assistant at different stages:

1. **Claude (Anthropic), web chat.** The project owner reports using Claude Haiku 5.5 in one conversation to generate the starting version of the pixel-art game. The owner supplied the challenge and NASA research context and requested a top-down, Terraria-style lunar base game for ages 7–12 with resources, shielding, power, and storms. The owner reports asking for keyboard and touch movement, a more detailed outdoor map with collisions, and an interior habitat with bunks, communications, rooms, and a sleep function. Claude generated the single-file HTML/CSS/JavaScript game and the associated “Did you know?” facts and source attribution from the supplied research brief. This model/version and workflow are recorded as reported by the project owner; this document does not independently verify them.
2. **GitHub Copilot / OpenAI assistant in this repository conversation.** An earlier prototype was drafted before the owner switched to Claude. After the owner supplied the Claude-generated game source in chat, the assistant replaced the repository’s `index.html` with that source and has assisted with repository documentation. The earlier prototype was superseded and is no longer the current game.

## Prompt and input record

The exact Claude prompts were not supplied in the current project conversation. We therefore do **not** present reconstructed prompt text as verbatim prompts. The following is an accurate summary of the task types and user-provided inputs reported by the owner:

| Stage | Prompt/input summary (not a verbatim transcript) | Reported AI contribution |
|---|---|---|
| Research and concept | Challenge brief and NASA research brief supplied; requested a game concept teaching lunar-outpost trade-offs for children. | Helped synthesize the material into a game concept and educational facts. |
| Game design | Requested a top-down, Terraria-style pixel-art Moon base for ages 7–12, with resources, shielding, power, storms, and trade-offs. | Designed the interactive game structure and mechanics. |
| Initial implementation | Requested a single HTML/CSS/JavaScript file with a canvas map, game logic, and explanatory text. | Generated the starting game implementation and text. |
| Interaction revisions | Requested keyboard and touch movement, a more detailed outdoor map and collisions, plus an interior habitat with bunks, communications, rooms, and a sleep function. | Added or revised those features in the Claude conversation, according to the owner. |
| Repository replacement | Supplied the full new HTML source and asked to replace the previous game with it. | The repository assistant committed the supplied source as `index.html`; this was a repository operation, not a claim that this assistant independently generated or tested Claude’s game. |
| Documentation | Asked for separate AI-use documentation and a project handoff overview. | Repository assistant drafted and updated `AI_USAGE.md` and `PROJECT_OVERVIEW.md`. |

For an exact-prompt audit, paste the original prompts from the Claude conversation into this section and label them as verbatim. Until then, these are summaries only.

## Human contributions and review

According to the project owner, the human contribution included:

- choosing the game concept and setting requirements;
- supplying the challenge prompt and NASA research brief to inform the game;
- reviewing and testing the AI-generated output, deciding which features to keep, and selecting the desired final direction;
- providing the Claude-generated HTML source to this repository conversation and requesting that it replace the earlier game.

The repository assistant has not independently run the current game in a browser or performed a full code, science, or accessibility validation. Human testing is reported by the owner; specific test devices, browsers, and results have not been documented here.

## Current game limitations and factual transparency

- The game is an educational prototype, not a NASA product, mission-planning tool, or validated scientific model.
- It does not retrieve live NASA data. Storm occurrences are randomized in the game and use different probabilities for the selected solar-cycle setting; they are not DONKI forecasts.
- The 1972 solar-storm reference is historical/archived context, not live data.
- Gameplay quantities (resource levels, dose increments and threshold, production rates, power costs, storm chances, mission length, and outcomes) are simplified/invented for play. They must not be presented as NASA engineering values, measured dose estimates, or health guidance.
- Educational facts and source list were generated from the research brief supplied by the owner and need checking against the original NASA references before public submission.
- No NASA logo, insignia, or NASA-generated visual asset was intentionally included in the provided HTML. The game loads the “Press Start 2P” font from Google Fonts; it is an external dependency, not an AI-generated asset.
- The game has not been shown to comply with all NASA Space Apps rules merely by including this disclosure.

## Suggested submission disclosure

> AI assistance was used in development. The project owner reports using Claude (Anthropic) in a web chat to synthesize the supplied challenge/research material, design the pixel-art lunar-base game, and generate its initial single-file HTML/CSS/JavaScript implementation, explanatory text, and NASA-source attribution. The owner reports requesting keyboard/touch controls, outdoor-map detail and collisions, and an interior habitat with rooms and a sleep function. GitHub Copilot / an OpenAI assistant was used earlier for a superseded prototype and later to assist with repository documentation and commit the owner-supplied Claude game source. The project owner selected the concept, provided the research brief, reviewed/tested the output, and selected the final direction. The current game uses no live NASA feed; storm events are randomized and gameplay values are simplified, not NASA measurements. The AI assistant in this repository has not independently tested the current game. NASA sources are credited in the game; NASA does not endorse this project.

Adjust this disclosure if more precise records become available or the tools/contributions change. Do not describe the summarized prompt tasks above as exact quotations.

## Review of official terms

Check the current [NASA Space Apps Challenge Legal / Participant Terms and Conditions](https://www.spaceappschallenge.org/legal/) and applicable challenge-year guidance directly before submission. This page is not a legal interpretation. In particular, verify any requirements about AI disclosure, ownership and licenses, third-party materials, NASA naming/imagery/insignia, source attribution, and required submission fields. Do not imply NASA sponsorship, endorsement, partnership, or official status.

## References

- [NASA Space Apps Challenge — Legal / Participant Terms and Conditions](https://www.spaceappschallenge.org/legal/)
- [NASA Space Apps Challenge](https://www.spaceappschallenge.org/)
- Game source notes and attribution: [`index.html`](./index.html)
- Project handoff: [`PROJECT_OVERVIEW.md`](./PROJECT_OVERVIEW.md)
