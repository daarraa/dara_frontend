<p align="center">
  <img src="./assets/dara-logo.png" alt="Dara Logo" width="180" />
</p>

<h1 align="center">Dara Frontend</h1>

<p align="center">
  A digital Ayo strategy game exploring African gaming culture, Stellar wallet identity, and future Soroban-powered gameplay.
</p>

---

## Overview

Dara is the planned user-facing frontend for a digital Ayo strategy game. The project combines a culturally rooted board-game experience with modern web UX, contributor-friendly documentation, and a future path toward Stellar and Soroban experiments.

This repository focuses on the frontend layer: board presentation, player flows, responsive interaction patterns, accessibility, and wallet-ready UI research. The companion contract work is tracked separately in the Dara contract repository.

## What is Ayo?

Ayo is a traditional African strategy board game, widely associated with Yoruba and broader West African play traditions. It is part of the mancala family of games where players distribute seeds or stones across pits, plan captures, and use counting strategy to outmaneuver an opponent.

Dara uses that familiar strategic foundation as inspiration for a digital game interface. The goal is to make the experience approachable for new players while respecting the cultural roots of the game.

## Frontend Purpose

The frontend is expected to become the main player experience for Dara. Planned responsibilities include:

- Presenting a clear Ayo board with pits, seeds, player turns, and game status.
- Supporting local gameplay state before any networked or on-chain features are introduced.
- Explaining rules, turn outcomes, and player actions in a beginner-friendly way.
- Providing mobile-friendly layouts for quick play.
- Preparing wallet connection surfaces for future Stellar identity experiments.
- Keeping contract and backend assumptions out of the UI until those interfaces are specified.

## Planned Features

| Area | Planned work |
|------|--------------|
| Board UI | Responsive pit/seed layout, player sides, turn indicators, and capture feedback. |
| Game state | Local move validation, status messages, restart flow, and winner display. |
| Player onboarding | Lightweight rules summary and first-game guidance. |
| Accessibility | Keyboard-friendly controls, visible focus states, readable contrast, and screen-reader labels. |
| Mobile UX | Touch-friendly board interactions and compact status panels. |
| Stellar research | Wallet identity UX, player profiles, and future proof-of-play concepts. |
| Soroban research | Match records, tournament metadata, and reward architecture exploration. |

## Current Status and Setup

This repository currently contains project documentation, issue templates, contribution guidance, Drips submission notes, and the Dara logo asset. The frontend application scaffold is not implemented yet.

Until an app scaffold is added, contributors can still help by improving documentation, UX plans, accessibility checklists, game-state specifications, wallet research notes, and issue hygiene.

Suggested local review flow:

```bash
git clone https://github.com/daarraa/dara_frontend.git
cd dara_frontend
```

Then review the Markdown files and assets directly. No package install step is required until a frontend framework is introduced.

## Stellar/Soroban Roadmap

Dara is preparing Stellar ecosystem support through scoped research and design tasks before any production on-chain claims are made.

| Phase | Direction | Example outputs |
|-------|-----------|-----------------|
| 0 | Documentation and frontend planning | README, contribution guide, UI requirements, Drips notes. |
| 1 | Playable frontend prototype | Local Ayo board, game-state handling, accessibility baseline. |
| 2 | Stellar identity exploration | Wallet connection UX, player identity notes, profile flows. |
| 3 | Soroban architecture research | Match-record design, rewards constraints, tournament metadata. |
| 4 | Integration planning | Contract/frontend interface notes, test plans, and security review checklist. |

## Contributing

We welcome contributors interested in frontend development, game UX, accessibility, documentation, cultural game research, Stellar wallet UX, and Soroban architecture planning.

Before starting:

1. Check the Issues tab for a scoped task.
2. Comment on the issue before starting work.
3. Fork the repository and create a focused branch.
4. Keep pull requests small and tied to one issue.
5. Include manual review notes or screenshots when the change affects visible UI.
6. Do not commit secrets, private keys, generated build artifacts, or unrelated files.

See [`CONTRIBUTING.md`](./CONTRIBUTING.md) for the repository checklist and complexity guide.

## Related Docs

- [`CONTRIBUTING.md`](./CONTRIBUTING.md) - contribution flow and pull request checklist.
- [`docs/drips-submission-notes.md`](./docs/drips-submission-notes.md) - project scope and Drips submission context.
- [`assets/dara-logo.png`](./assets/dara-logo.png) - logo used at the top of this README.

## License

MIT