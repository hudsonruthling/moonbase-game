# Moon Base Trade-Offs — project handoff

Read this handoff and inspect the current [`index.html`](./index.html) before continuing in another chat. It summarizes project history and current behavior; the checked-in HTML is authoritative if details differ.

## Quick handoff instructions

- **Repository:** [`hudsonruthling/moonbase-game`](https://github.com/hudsonruthling/moonbase-game), private, default branch `main`.
- **Current game:** [`index.html`](./index.html), titled **Moon Base Trade-Offs**.
- **AI disclosure:** [`AI_USAGE.md`](./AI_USAGE.md).
- Edit the existing `index.html` for future changes. Keep this overview and AI disclosure separate from the playable HTML, and update them when project details change.
- No local server or GitHub Pages deployment has been configured. Repository storage is not the same as locally hosting on the user's device or publishing a playable website.
- The user wants this repository to be the persistent home of the game so later chats can update the same source.

## Goal and supplied research

The user is developing a browser-playable STEM game for ages 7–12 for the NASA Space Apps Challenge. The challenge is to teach authentic lunar (or possibly Martian) outpost trade-offs in a kid-friendly way. The user supplied a detailed “Lunar Outpost Trade-Off Game: Research Brief” (prepared Nov. 14, 2026) and challenge description. Those discuss power and lunar night, radiation and shielding, solar activity, habitats, food/oxygen and possible local resources, communication delay, NASA attribution, and optional DONKI/OSDR data. They caution against inventing dose/shielding figures and say static information must not be represented as live.

## Project history

1. The user supplied the challenge and research briefs. An initial six-day, card-based game was drafted in the project conversation and committed as `index.html`.
2. The private GitHub repository was created at the user's request. The user asked for separate project-handoff and AI-use documents so work can continue across chats.
3. The user reports switching to Claude (Anthropic) to generate a new starting game: a top-down, Terraria-style pixel-art lunar base. The owner reports using Claude Haiku 5.5 in one web-chat conversation, supplying the challenge and NASA research brief, and asking for resource/shielding/power/storm gameplay, keyboard and touch controls, an expanded outdoor map with collisions, and an interior habitat with bunks, comms, rooms, and a sleep function. These are owner-reported tool/model details; exact Claude prompt transcripts were not supplied here.
4. The user pasted the full new HTML source and asked to replace the old game. The repository assistant committed the supplied source as the current `index.html`; the earlier card-based prototype was overwritten. The repository assistant has not independently browser-tested the new game.
5. The user then asked to update this handoff and the AI-use page to reflect the Claude-generated game. Both documents have now been updated accordingly.

## Current game summary

`index.html` is a single HTML document with inline CSS and JavaScript. It uses a 320×192 canvas, pixel-art rendering, a retro interface, and the Google-hosted “Press Start 2P” font. It has no build tools or packages; that external font does require network access. The game can be opened as an HTML file in a browser, though browser testing has not been independently recorded.

### Mission setup

- Mission is described as four astronauts at the lunar south pole for 12 days.
- Select **solar maximum** or **solar minimum**. These change the game's random storm probability (32% versus 8% per later day); this is an invented game setting, not a live forecast or a NASA probability.
- Select **sunny ridge** or **crater rim**. Ridge has more simulated solar power; crater has less solar power but its air-making action produces more air, standing in for nearby ice. This is a simplified gameplay assumption, not a site-specific engineering estimate.
- Allocate up to six extras between solar panels, a bigger battery, and a shielding kit. Each allocation is limited to 0–3. Initial power capacity is 8 + 6 per battery extra, starting power is full, solar panels are 1 + extra panels, and shield starts at the selected kit count.
- Setup currently says the player must keep dose under 100 and perform at least five science walks.

### Controls, map, and interface

- Pixel-art top-down exterior base and separate interior habitat are rendered on canvas.
- Move with arrow keys or WASD; use E/space or the on-screen direction pad and Use button. Action buttons also route the crew to a facility and execute the chosen action.
- Player can use the airlock to change between outside and inside. The interface displays power, air, food, dose, day, crew action points, science, weather banner, and a text/fact log.
- The layout includes touch controls and a responsive HUD. The canvas has an accessible label; comprehensive accessibility testing has not been done.

### Daily actions and costs (as implemented)

There are three crew action points per day. Each listed action consumes one action point and its displayed power amount:

- **Make air:** 2 power; produces +24 air at crater site or +14 at ridge, capped at 100.
- **Grow food:** 2 power; produces +12 food, capped at 100.
- **Moon walk: science:** 1 power; science +1. Adds +4 dose on a quiet day or +28 if a storm is occurring.
- **Pile moon dirt:** 1 power; shielding +1 up to level 4. A storm later in the day adds dose based on the shield level; dose calculation is simplified.
- **Call Earth:** 1 power and one action point; moves the player to the habitat comms station, displays a signal-travel delay, then waits 2.6 seconds in real time before revealing the pre-generated next-day storm state (when a next day exists). This is a gameplay timing effect, not an exact real-time communication simulation.
- **End the day / sleep:** after actions are finished or voluntarily, daily resource costs and events resolve. Each day adds background dose (+2 at solar max, +4 at solar min). A storm adds shield-adjusted dose and drains 2 power. The outpost then uses 3 power, 10 air, and 8 food. If power falls below zero, it is set to zero and air loses another 12. A lunar night is scripted every fourth day; it has no solar generation.
- Solar generation on non-night days is `floor(panels * 5 * siteMultiplier)`, with multiplier 1 at ridge and 0.6 at crater, capped by battery capacity.
- Storm states for days 2–13 are randomly pre-generated at mission start using the selected solar setting.
- Ending conditions include air exhaustion, food exhaustion, dose reaching 100, or finishing 12 days. Completion is labeled mission success only if at least five science walks are completed.

All these values, probabilities, rates, thresholds, resource conversions, and outcomes are simplified and invented for play. They are not validated NASA measurements, dose estimates, clinical advice, engineering specifications, or mission-planning limits.

## Science content and data status

The game provides short “Did you know?” facts concerning lunar darkness and power storage, regolith shielding, solar storms, space-weather officers, the August 1972 solar storms, Shackleton crater/ice, Moon signal delay, cosmic rays, temperatures, potential local resources, solar cycle, dose, and impacts. A source list appears in a details section in the game.

- **No live NASA API or dataset is connected.** DONKI and OSDR are not queried. Storm days are random. The historical 1972 event is an archived fact, not current data.
- The source list currently contains plain-text citations rather than direct links for all listed works. Verify titles, dates, claims, and citations against primary sources before submission; research-brief citations should not be assumed independently verified.
- Communication delay is described in the game as an approximately 1.3-second one-way light-speed calculation from an approximate 240,000-mile distance, not a quoted NASA figure.
- NASA facts should be distinguished from made-up game values. Avoid introducing dose/shielding numbers not supported by a checked source; the supplied brief says exact values were not extracted from the cited charts.
- Do not claim NASA endorsement, partnership, or official status. The submitted HTML has no NASA logo/insignia or NASA imagery.

## AI-use record

See [`AI_USAGE.md`](./AI_USAGE.md) for the disclosure. Summary:

- The owner reports using Claude (Anthropic) in one web conversation, model/version reported as Claude Haiku 5.5, to synthesize the supplied challenge/research material, design the pixel-art game, and generate the starting HTML/CSS/JavaScript, game text, and attribution. They report requesting keyboard/touch controls, more detailed exterior/collisions, and an interior with bunks/comms/rooms/sleep.
- Exact Claude prompts are not in the current conversation and must not be fabricated or presented as verbatim. The AI-use file includes honest task summaries only.
- GitHub Copilot / an OpenAI assistant was used for the superseded earlier prototype and repository documentation; the project assistant also committed the user-provided Claude HTML source to replace the earlier game.
- The owner reports selecting the concept and requirements, supplying the challenge/research brief, reviewing/testing the output, and selecting retained features. The repository assistant has not independently run or tested the current game.

## Known validation and follow-up items

- The new game has not been independently tested in a browser by the repository assistant. Before public use, test launch/setup, each action and resource cost, storm/night transitions, scene movement/collisions, Earth forecast delay, end conditions, restart, keyboard, touch, and small-screen behavior.
- Verify game logic and UI labels against code after any change. Treat all gameplay numbers and dose values as fictional game units; the current UI needs to make that limitation conspicuous enough for young players.
- The current science notes say lunar dirt can grow crops and make oxygen, and crater ice can be melted into air. Keep these framed as potential technologies or simplified game mechanics, not established yields or operational capabilities.
- Consider adding direct links and publication dates to each source; verify 2026-dated references against original NASA pages before relying on them.
- Review the official [NASA Space Apps Challenge Legal / Participant Terms and Conditions](https://www.spaceappschallenge.org/legal/) and event-specific rules directly before submission. `AI_USAGE.md` is a transparency record, not legal advice or a guarantee of compliance.
- If enabling GitHub Pages, consider that the repo is private and confirm the desired access and availability first. No hosted URL is currently configured.

## Suggested new-chat handoff prompt

> Read `PROJECT_OVERVIEW.md`, `AI_USAGE.md`, and the current `index.html` in `hudsonruthling/moonbase-game`. The current game is the Claude-generated pixel-art “Moon Base Trade-Offs” game, replacing the earlier six-day card prototype. Continue by editing the existing `index.html` and keep the overview and AI disclosure accurate. Treat all gameplay quantities and randomized storm events as illustrative, not NASA data; no live NASA API is implemented. Do not invent verbatim Claude prompts. My requested change is: [describe the change].
