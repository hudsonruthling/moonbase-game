# Moonbase: Every Choice Costs — project overview

Use this document to bring a new chat up to speed on the project. It is intentionally separate from the playable HTML file. If you start a fresh chat, share this file or paste its contents and say that it is the project overview.

## Project and repository

- **Repository:** [`hudsonruthling/moonbase-game`](https://github.com/hudsonruthling/moonbase-game)
- **Visibility:** Private
- **Default branch:** `main`
- **Game file:** [`index.html`](./index.html)
- **Overview:** `PROJECT_OVERVIEW.md` (this document)
- The user wants this repository to be the persistent home for the game, so future edits should update the existing `index.html`, not create a replacement download each time.
- GitHub repository storage is not the same as hosting the game on the user's computer. The file is in the repo; no local server or GitHub Pages deployment has been configured.

## User goal and challenge

Create a working, browser-friendly STEM game for children ages 7–12 in which players run a lunar or Martian outpost and experience authentic engineering trade-offs. Every decision should have a cost, be understandable in plain language, and connect to a real mission constraint. Keep the experience accessible without downloads or accounts where feasible, and clearly distinguish NASA facts from simplified game mechanics.

The supplied challenge brief emphasizes balancing life support, radiation shielding, power, food production, and communication delay. It encourages use of authentic NASA sources such as DONKI, OSDR, Artemis, and surface-mission information, with attribution. Static information must not be presented as live data.

## Current prototype

`index.html` is a self-contained HTML/CSS/JavaScript game that can be opened in a modern browser. It has a dark, responsive mission-control interface and a six-day lunar outpost scenario.

### Setup choices

- Site: sunlit ridge or shadowed crater.
- Solar activity: solar maximum or solar minimum.
- Ridge produces more simulated solar power; crater produces less. This is a simplified gameplay contrast, not a site-specific power model.
- Solar maximum makes simulated storm warnings more likely than solar minimum. The game does not fetch current space-weather events.

### Game systems and actions

- Meters: stored power, crew supplies, shelter shielding, a radiation-risk game meter, and collected science.
- Each day the crew chooses one plan: pile regolith onto shelter, grow supplies, explore for science, tune the solar array, or stay inside and monitor.
- Basic life support consumes power and crew supplies each day. Actions use additional power/supplies or trade safety for science.
- Day 4 is a scripted lunar night with no solar input.
- Weather-event draws and science notes vary between playthroughs.
- Mission outcomes include resource failure, excessive game risk, or completing the six-day mission; survival and science output are described in the ending.
- All resource values, storm probabilities, risk changes, and success limits are illustrative teaching units. They are not NASA measurements, dose predictions, engineering specifications, or validated mission-planning calculations.

### Current science framing and attribution

The game presents explanatory notes and in-game source links for NASA material on lunar power, regolith shielding, solar energetic particles, galactic cosmic rays, lunar conditions, and Moon-to-Earth signal delay. It says that a one-way communication delay of about 1.3 seconds is a light-speed calculation based on the approximate Moon–Earth distance, not a quoted NASA figure. It includes these source references:

- NASA, “Living and Working on the Moon.”
- NASA, “Moon Base.”
- NASA, “Lunar Living: NASA’s Artemis Base Camp Concept” (2020).
- NASA, “How NASA Will Protect Astronauts From Space Radiation at the Moon.”
- K. Ryder and M. Campola, “The Lunar Radiation Environment” (NASA GSFC, 2022; NTRS 20220007070).
- NASA DONKI and NASA Open Science Data Repository are linked as possible future sources, with an explicit note that neither is connected in this prototype.

The user's research brief also mentions NASA’s 2026 Moon Base developments and crater findings, long lunar darkness periods (up to eight days of energy storage planning), solar-vs-cosmic radiation trade-offs across the solar cycle, and the limitations of shielding cosmic rays. Verify current source details and dates before adding them to the game.

## Important constraints for future edits

1. Preserve the distinction between **NASA-sourced facts** and **invented/simplified gameplay values**.
2. Do not label data as live unless the app actually retrieves and displays it. If data is embedded, call it archived/static and cite the source.
3. Do not invent radiation-dose or shielding-thickness numbers. The supplied research brief says exact values were not extracted from the cited shielding charts.
4. Keep language age-appropriate; explain terms like regolith, radiation dose, solar maximum/minimum, and communication delay in context.
5. Keep choices meaningful: beneficial actions should consume another resource, time, or opportunity.
6. Maintain keyboard accessibility, readable contrast, responsive layout, and clear end/restart behavior.
7. When the user asks for an edit, change the existing `index.html` in this repository and retain this overview as a separate document. Update this overview if project decisions, features, data sources, or hosting status change.

## Hosting and next steps

The repository exists and now contains `index.html` and this overview. No live hosting has been set up. To make the game available from a stable browser URL, a future step could enable GitHub Pages for this repository; that would be web hosting, distinct from “hosting locally” on the user's device. Before doing so, consider that this repository is private and confirm the desired access/visibility behavior and available GitHub Pages configuration. A local copy can also be run by opening `index.html` directly in a browser.

## Original reference material

The user supplied a detailed “Lunar Outpost Trade-Off Game: Research Brief” (prepared Nov 14, 2026) and the Space Apps challenge statement. The brief recommends a concise survival game with a few core resources, meaningful costs, plain-language fact cards, NASA attribution, and honest labeling of archived versus live data. It proposes DONKI for solar activity, OSDR for astronaut biology/health research, and a clearly labeled archive such as the 1972 solar storms as possible future data additions. Neither DONKI nor OSDR is implemented in the current prototype.
