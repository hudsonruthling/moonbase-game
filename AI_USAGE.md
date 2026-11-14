# AI use disclosure

**Project:** Moonbase: Every Choice Costs  
**Repository:** [`hudsonruthling/moonbase-game`](https://github.com/hudsonruthling/moonbase-game)  
**Purpose:** Document AI assistance used in this project and provide a checklist for reviewing applicable NASA Space Apps Challenge terms.  
**Status:** Prepared November 14, 2026. This is a project disclosure, not legal advice or a substitute for the event's official rules.

## AI tools and assistance used

Generative AI (GitHub Copilot / OpenAI assistant in the project conversation) was used to help:

- turn the user's challenge prompt and supplied lunar-outpost research brief into a playable prototype;
- draft the HTML, CSS, and JavaScript in [`index.html`](./index.html), including the interface, sample game mechanics, explanatory text, and game outcomes;
- organize the repository and prepare project documentation.

The user supplied the challenge description and research brief that informed the prototype. AI assistance generated and assembled the implementation and draft text; this file records that contribution rather than presenting the work as wholly human-authored.

## What the prototype does and does not do

- It is a simplified educational game, not a NASA tool, mission-planning system, or validated scientific model.
- Gameplay quantities, event probabilities, resource effects, and thresholds are illustrative choices for play. They are not NASA measurements, dose estimates, or engineering specifications.
- NASA-related statements and source references in the game are based on the user-provided research brief and cited NASA material. They should be checked against the original sources before publication or judging.
- The current prototype does **not** make live requests to NASA DONKI or OSDR, and does not contain a NASA dataset represented as live. The source links are attribution and possible future research directions only.
- No NASA logo, insignia, or NASA-generated image asset was intentionally added to the prototype.
- No external generative-AI image, audio, or video assets were used in the submitted HTML prototype.

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

> Generative AI assistance (GitHub Copilot / OpenAI assistant) was used to draft and implement the prototype's HTML, CSS, JavaScript, game text, and project documentation. The project team supplied the challenge brief and research notes and should review, test, and verify the resulting code and factual claims. Game values are illustrative, not NASA data. The prototype does not connect to live NASA APIs. NASA sources are credited in the game; NASA does not endorse this project.

Edit this statement if the project later adds or removes AI tools, data feeds, assets, or substantial human-authored contributions. Review it against the current event rules before submission.

## References

- [NASA Space Apps Challenge — Legal / Participant Terms and Conditions](https://www.spaceappschallenge.org/legal/)
- [NASA Space Apps Challenge website](https://www.spaceappschallenge.org/)
- See the in-game attribution section in [`index.html`](./index.html) and research context in [`PROJECT_OVERVIEW.md`](./PROJECT_OVERVIEW.md).
