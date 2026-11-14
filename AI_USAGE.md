# AI use disclosure

**Project:** Moonbase: Every Choice Costs  
**Repository:** [`hudsonruthling/moonbase-game`](https://github.com/hudsonruthling/moonbase-game)  
**Purpose:** Document AI assistance used in this project and provide a checklist for reviewing applicable NASA Space Apps Challenge terms.  
**Status:** Prepared November 14, 2026. This is a project disclosure, not legal advice or a substitute for the event's official rules.

## AI tools and assistance used

Generative AI was used to help build and organize the project. In this repository, the work was assisted using GitHub Copilot and an OpenAI-style assistant in the project chat workflow.

### What the AI helped with

- turning the challenge prompt and the supplied lunar outpost research brief into a playable prototype;
- drafting the initial HTML, CSS, and JavaScript for [`index.html`](./index.html), including layout, mechanics, game logic, and explanatory science notes;
- formatting the repository documents and preparing separate project notes for continuity across chats;
- writing a plain-language project overview and AI usage disclosure.

### Representative prompts used

The following are representative examples of the kinds of prompts used during development (not a verbatim record of every single prompt, but a faithful summary of the task types):

- "Build a browser-based lunar outpost game for kids ages 7–12. Make it educational, fun, and grounded in real NASA concepts. Use resource management and trade-offs like power, oxygen, radiation shielding, science, and communication delay."
- "Create a single-file HTML/CSS/JS game in a browser-friendly format. Keep it simple enough for kids but accurate enough to teach mission trade-offs."
- "Design a lunar outpost survival game with a six-day mission. Each day the player chooses an action. Balance power, crew supplies, shelter shielding, and science. Add a clear restart and win/lose state."
- "Add plain-language explanations for regolith, solar maximum, solar minimum, and communication delay within the game. Explain that the game numbers are simplified and not real NASA data."
- "Write a project overview file separate from the HTML that explains the project, repository, NASA research context, and how future edits should be handled."
- "Create an AI usage disclosure document that explains the project, the AI tools involved, the project's limitations, and how it complies with transparency expectations for a NASA challenge."
- "Add an attribution section in the game with NASA references, and label live vs. archived data clearly."

These prompts were used to generate and refine implementation details, not to replace human decision-making or science validation.

## What the prototype does and does not do

- It is a simplified educational game, not a NASA tool, mission-planning system, or validated scientific model.
- Gameplay quantities, event probabilities, resource effects, and thresholds are illustrative choices for play. They are not NASA measurements, dose estimates, or engineering specifications.
- NASA-related statements and source references in the game are based on the user-provided research brief and cited NASA material. They should be checked against the original sources before publication or judging.
- The current prototype does **not** make live requests to NASA DONKI or OSDR, and does not contain a NASA dataset represented as live. The source links are attribution and possible future research directions only.
- No NASA logo, insignia, or NASA-generated image asset was intentionally added to the prototype.
- No external generative-AI image, audio, or video assets were used in the submitted HTML prototype.

## Human review and validation

The AI-generated content was reviewed by the project owner and adjusted to match the user's challenge brief and research summary. All game logic and educational statements were checked for clarity and to keep NASA facts separate from simplified gameplay units.

## Terms and attribution review

The project should be checked against the exact terms and challenge-specific rules for the relevant Space Apps year before submission. The official participant terms are published at [NASA Space Apps Challenge Legal / Participant Terms and Conditions](https://www.spaceappschallenge.org/legal/). Read the current terms directly; this disclosure does not quote or interpret them as a definitive legal ruling.

In particular, the team should verify the event's current requirements regarding:

1. disclosure of AI tools or AI-generated work;
2. submission ownership, permissions, and licenses granted to the organizers;
3. third-party code, text, data, and asset licenses;
4. NASA name, insignia, imagery, endorsement, and affiliation claims; and
5. required source citations and project-submission disclosures.

This repository's disclosure is intended to make AI assistance transparent. It does not imply NASA sponsorship, endorsement, partnership, or approval. NASA names and source links are used to identify references, not to represent the game as an official NASA product.

## Suggested submission disclosure

> Generative AI assistance (GitHub Copilot / OpenAI assistant) was used to draft and implement the prototype's HTML, CSS, JavaScript, game text, and project documentation. The project team supplied the challenge brief and research notes and reviewed the resulting code and factual claims. Game values are illustrative and not NASA data. The prototype does not connect to live NASA APIs. NASA sources are credited in the game; NASA does not endorse this project.

Edit this statement if the project later adds or removes AI tools, data feeds, assets, or substantial human-authored contributions. Review it against the current event rules before submission.

## References

- [NASA Space Apps Challenge — Legal / Participant Terms and Conditions](https://www.spaceappschallenge.org/legal/)
- [NASA Space Apps Challenge website](https://www.spaceappschallenge.org/)
- See the in-game attribution section in [`index.html`](./index.html) and research context in [`PROJECT_OVERVIEW.md`](./PROJECT_OVERVIEW.md).
