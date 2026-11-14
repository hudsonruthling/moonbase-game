# Moonbase: Every Choice Costs — project handoff

This is the persistent handoff document for continuing work on the game in a new chat. It records the user's goals, repository state, current implementation, known limitations, AI disclosure, prior decisions, and instructions for future edits. A new assistant should read this file before changing the project.

## Quick start for a new chat

1. Open or share this repository and this file: [`PROJECT_OVERVIEW.md`](./PROJECT_OVERVIEW.md).
2. The playable game is [`index.html`](./index.html). Make requested game changes directly in this existing file; do not make a new downloadable copy unless asked.
3. The separate AI disclosure is [`AI_USAGE.md`](./AI_USAGE.md). Keep it consistent with actual project work and update it when AI tools or contributions change.
4. Check the latest versions of the files in the repository before editing. This handoff is a summary, not a substitute for inspecting current code.
5. The user has asked for persistent repository-based editing so future chats can continue from this project.

## Repository and hosting status

- **Repository:** [`hudsonruthling/moonbase-game`](https://github.com/hudsonruthling/moonbase-game)
- **Visibility:** Private
- **Default branch:** `main`
- **Game:** [`index.html`](./index.html)
- **Project handoff:** [`PROJECT_OVERVIEW.md`](./PROJECT_OVERVIEW.md)
- **AI use disclosure:** [`AI_USAGE.md`](./AI_USAGE.md)
- The user originally asked to save and host the game locally so future edits would not require a new download. The repository is the persistent shared source of truth, but it does not by itself host a page locally on the user's device.
- **No local web server or GitHub Pages deployment has been configured.** To view the file, the user can open the repository's `index.html` in GitHub or download/open it in a browser. Do not claim it has a stable deployed game URL unless one is actually set up.
- The user confirmed creation of the private repository and confirmed adding the game plus the separate overview. The user later asked for a separate AI-use page and confirmed its addition, then asked for specific AI prompts and more complete handoff context.

## Project goal and challenge context

Build an interactive, browser-friendly STEM game for children ages 7–12 that makes real lunar (or potentially Martian) outpost engineering trade-offs tangible and engaging. The challenge asks players to balance life support, radiation shielding, power, food production, and communications. A meaningful choice should cost another resource, time, or opportunity. Explain technical terms plainly and help a young player learn at least one real constraint of deep-space survival.

The user supplied the challenge statement and a detailed “Lunar Outpost Trade-Off Game: Research Brief” (prepared Nov. 14, 2026). It covers lunar south-pole power and darkness, solar energetic particles (SEPs) and galactic cosmic rays (GCRs), shielding with regolith, solar-cycle differences, environment, habitats and rovers, potential lunar resources, Moon communication delay, NASA source attribution, and cautions against inventing dose/shielding figures. The brief recommends DONKI and OSDR as possible data sources, and clearly labeling embedded information as archived rather than live.

## Current HTML game: what is implemented

`index.html` is a standalone HTML document using inline CSS and JavaScript. It needs no build system or package dependencies. The interface is dark, responsive, keyboard-focus styled, and framed as a lunar mission-control game.

### Setup

- Select a **sunlit ridge** or **shadowed crater**.
- Select **solar maximum** or **solar minimum**.
- Site selection only changes the game's simulated sunlight rate (ridge starts at 3 units/day, crater at 1 unit/day before array maintenance). It is not a validated or site-specific NASA power model.
- Solar maximum uses a 48% random storm-warning chance on non-night days; solar minimum uses 18%. These probabilities are invented gameplay mechanics, not NASA forecast statistics.
- The mission starts with power 8, supplies 10, shielding 1, risk 0, and science 0. Meters are capped at 12 power, 12 supplies, and 8 shielding.

### Turn loop and actions

- The mission lasts six days; day 4 is always a scripted lunar night with zero solar input.
- At the start of a turn, the game randomly chooses whether there is a storm warning (except on night) and displays the condition.
- The player selects one of five actions, then clicks **Use this plan**:
  1. **Pile on moon dirt:** action power cost 2, action supply cost 1, shielding +2.
  2. **Grow crew supplies:** action power cost 2, supplies +2 before the daily consumption is applied. Net supplies change is +1 for that turn.
  3. **Go explore:** action power cost 1, action supply cost 1, science +2, and risk increases by 1 without a storm; with a storm, risk increases by 1 if shielding is at least 3, otherwise by 3.
  4. **Tune the solar array:** action power cost 2, action supply cost 1, and future sunlight is increased by 1 per completed repair, up to 2 repairs total. Despite the choice-card copy saying “+2,” the code increments future solar by **+1** each time; this discrepancy should be fixed in a future code cleanup or accurately reflected in the card.
  5. **Stay inside and monitor:** action power cost 1, no science, and a log message. It does not currently directly reduce risk or improve shielding.
- Every resolved day also charges **2 power** for basic life support and deducts **1 supply** for the crew. Therefore total power cost is 2 + action power cost. Net supply change is daily -1 plus the selected action's supply change.
- If available power or supplies are insufficient, the mission ends immediately with an explanatory message.
- Storm warnings affect risk only if the player chooses to explore. Choosing to stay inside does not otherwise alter game risk.
- Science notes are randomly selected from a small set of educational facts.
- The end state shows mission success/failure, collected science, and a replay suggestion. A surviving mission with 4 or more science gets a stronger success message.
- Risk at 8 ends the mission. This meter is explicitly described as illustrative, not a radiation dose or health prediction.

### Known implementation details and possible fixes

- The action cards are not disabled when unaffordable. The player can select an impossible action and then gets a mission-failure outcome on resolve. Consider showing affordability before a child commits or adding an undo/confirm step.
- The repair action's card currently says future sunlight “+2” even though code adds +1 per repair. Correct one side so the UI and mechanic agree.
- The code's “shielding” meter and storm-risk reduction rule are highly simplified. It should not be presented as a dose-vs-thickness relationship; the supplied research brief explicitly says not to invent numerical dose/shielding values.
- Site labels mention possible crater ice, but no ice resource mechanic is implemented. “Grow crew supplies” is a fictional gameplay abstraction and not a representation of validated crop production or in-situ resource utilization rates.
- Communications delay is mentioned only in a science note/reference text; it is not currently a gameplay mechanic.
- The game does not currently distinguish oxygen from food/water in separate meters, despite those being part of the challenge's broad goal.
- `today` conditions are generated when rendering a turn; they remain fixed for that turn until the player resolves it. Re-rendering a turn would re-roll the event.
- `reset` starts a fresh game using the current dropdown selections.
- User-facing result text is inserted via `innerHTML` in `finish`; current result strings are hardcoded, but if future content becomes user-provided, avoid unsafe HTML insertion.

## NASA facts, data, and attribution

The game contains an in-game “What is based on NASA information?” disclosure, several science notes, and links/references. It explicitly says game quantities are simplified and that DONKI and OSDR are not connected. Current referenced sources include:

- NASA, “Living and Working on the Moon.”
- NASA, “Moon Base.”
- NASA, “Lunar Living: NASA’s Artemis Base Camp Concept” (2020).
- NASA, “How NASA Will Protect Astronauts From Space Radiation at the Moon.”
- K. Ryder and M. Campola, “The Lunar Radiation Environment” (NASA GSFC, 2022; NTRS 20220007070).
- NASA DONKI API and NASA Open Science Data Repository (OSDR), linked as potential sources, not implemented feeds.

The user-provided brief includes additional facts that may support future carefully sourced improvements: early systems may need to store power for up to eight days; a planned fission surface power unit is 10 kW; south-pole temperature extremes; regolith shelter shielding; the solar maximum/minimum trade-off; approximately 240,000 miles to the Moon and a calculated ~1.3-second one-way light travel time; possible water ice; and recent crater findings. Verify each claim and its current wording against original sources before incorporating it. Do not use future-dated/current-event details without verifying their existence and publication dates.

**Data status:** No live API call, DONKI event, OSDR data, or downloaded NASA dataset is implemented. Never describe the game as live-data-powered until actual retrieval, display, error handling, date labeling, and attribution are implemented. If adding a static/archived record, label its date and archived status in the UI.

## AI use disclosure and prior AI-related work

[`AI_USAGE.md`](./AI_USAGE.md) is a separate repository file created after the user requested a separate AI-use documentation area. It documents AI-assisted prototype generation, representative prompt examples, project limitations, suggested submission disclosure, and a link to the NASA Space Apps legal/terms page.

The disclosure currently says generative AI (GitHub Copilot / OpenAI assistant) helped draft the prototype's HTML/CSS/JavaScript, game text, and repository documents. It labels the examples as representative prompt summaries, **not verbatim complete chat transcripts**. This distinction matters: do not claim reconstructed prompt examples are exact quotations. If precise prompts are required for an application or audit, use actual chat history where available and clearly distinguish exact excerpts from summaries.

Before submission, check the current official [NASA Space Apps Challenge Legal / Participant Terms and Conditions](https://www.spaceappschallenge.org/legal/) directly. Do not treat generated summaries as authoritative legal interpretation. The project must not claim NASA endorsement, partnership, or official status. The prototype intentionally has no NASA logo/insignia or NASA-generated visual assets. Review third-party code/assets and event-specific disclosure/ownership requirements before public submission.

## Design and development guardrails

1. Update the existing `index.html` in the repo for future game edits; keep `PROJECT_OVERVIEW.md` and `AI_USAGE.md` separate from the HTML.
2. Update this overview when meaningful implementation details, project decisions, files, hosting, data integrations, or AI tooling change.
3. Keep all UI language suitable for ages 7–12 and explain jargon in context.
4. Distinguish NASA-cited factual background from game assumptions. Mark invented game units and probabilities as illustrative.
5. Do not fabricate dose, shielding, food production, power, or health figures; use source-verified figures with scope and units if adding real data.
6. Make costs and consequences visible before decisions, and ensure the interface matches the implemented mechanics.
7. Consider adding stronger accessibility (screen-reader updates, reduced-motion support, contrast review) and testing on mobile/small screens.
8. Avoid implying NASA built, approved, or endorses the prototype.
9. Keep the static HTML usable without account/API key. If implementing NASA API calls, protect credentials (never embed a private API key), handle rate limits/network errors, disclose data dates, and provide a clear fallback.

## Conversation and project history so far

- User provided the challenge prompt and extensive lunar outpost research brief.
- An initial single-file browser game was drafted in chat.
- User asked for a persistent place to save and edit the same script. A private repo was created after user confirmation.
- User requested a separate overview document for cross-chat handoff, and confirmed adding it after `index.html` was saved.
- `index.html` and the initial `PROJECT_OVERVIEW.md` were committed together to the repository.
- User requested a separate documentation area for AI use under NASA terms. Research was done on the official legal page, and a separate `AI_USAGE.md` was added after confirmation.
- User then requested specific prompts/information on the AI-use page. Representative prompt examples and more detailed AI-use disclosure were added to `AI_USAGE.md`.
- User's latest request is to make this overview sufficiently complete that a new chat can continue the HTML game with full context. This version expands the handoff, records current code mechanics and known inconsistencies, and links the companion documents.

## Suggested first message in a new chat

> Please read `PROJECT_OVERVIEW.md`, `AI_USAGE.md`, and the current `index.html` in `hudsonruthling/moonbase-game` before making changes. This is the handoff for the Moonbase: Every Choice Costs STEM game. Continue by editing the existing `index.html` in the repository, preserve the distinction between NASA facts and illustrative mechanics, and update the overview if behavior or project status changes. My requested change is: [describe the change].
