# Mobile Accessibility Plan

This plan defines baseline mobile and accessibility expectations for the future Dara gameplay interface. It is focused on the Ayo board, pit actions, seed counts, turn indicators, and status messaging contributors will need when building the frontend.

## Goals

- Make the game playable on small touch screens first.
- Keep board actions understandable for keyboard and screen-reader users.
- Make the current turn, selected pit, seed counts, and game status clear without relying on color alone.
- Give contributors a simple checklist before opening gameplay UI pull requests.

## Mobile-First Board Layout

The board should be designed for narrow screens before desktop expansion:

- Keep the main board visible without requiring horizontal scrolling.
- Use large touch targets for every playable pit.
- Preserve clear spacing between adjacent pits so taps do not trigger the wrong move.
- Keep the current player, turn state, and latest move summary close to the board.
- Avoid hiding required game actions behind hover-only interactions.
- Prefer stacked controls on mobile and wider side-by-side panels on tablet or desktop.

Recommended touch target guidance:

- Pit buttons should be at least 44 by 44 CSS pixels.
- Primary game actions should remain reachable with one hand on common phone widths.
- Secondary information, such as history or help text, can move below the board on mobile.

## Pit Buttons

Each pit should be implemented as a real interactive control, not only a visual container.

Pit button requirements:

- Use a semantic `button` for playable pits.
- Disable pits that cannot be selected on the current turn.
- Provide a visible selected, focused, disabled, and active state.
- Do not use color as the only indicator for the active player or selected pit.
- Keep the pit label stable as seeds move during gameplay.

Suggested accessible label pattern:

```text
Player 1 pit 3, 4 seeds, selectable
```

For unavailable pits:

```text
Player 2 pit 5, 0 seeds, not selectable this turn
```

## Seed Counts

Seed counts are core game information and should be readable in several ways:

- Display the number as text, not only as seed icons.
- Keep the count close to the pit it describes.
- Announce count changes after a move through status text.
- Avoid animations that make counts difficult to follow.
- Use plural-friendly copy such as `1 seed` and `4 seeds`.

If seed icons are added later, they should be decorative when the numeric text already communicates the count.

## Turn Indicators

The active turn should be visible and announced clearly.

Turn indicator requirements:

- Show the current player in text, for example `Player 1 turn`.
- Pair color with a text label or icon so the state is not color-only.
- Update the status message after each move.
- Keep the turn indicator near the board on mobile.
- Preserve focus after a move so keyboard users do not lose their place.

Suggested status message:

```text
Player 1 moved pit 3. Player 2 turn.
```

## Status Messages

Status messages should explain important game state changes:

- Invalid move
- Move completed
- Turn changed
- Capture or scoring event
- Game paused
- Game over

Use a live region for important updates so screen readers receive changes without forcing focus away from the board.

Suggested implementation direction:

```tsx
<p aria-live="polite">{statusMessage}</p>
```

Use assertive announcements only for urgent states, such as a blocking error.

## Keyboard Navigation

The board should support keyboard play for desktop and assistive technology users.

Recommended keyboard behavior:

- `Tab` moves between playable pits and game controls.
- `Enter` or `Space` selects the focused pit.
- Arrow keys can move focus across adjacent pits once the board grid exists.
- `Escape` closes any open help, settings, or confirmation panel.

Keyboard focus should always be visible. Avoid resetting focus to the top of the page after a move.

## Screen-Reader Label Guidance

Labels should include player side, pit number, seed count, and action state.

Examples:

- `Player 1 pit 1, 3 seeds, selectable`
- `Player 1 store, 12 captured seeds`
- `Player 2 pit 4, 6 seeds, disabled until Player 2 turn`
- `Current turn: Player 1`
- `Move result: Player 1 captured 2 seeds`

If the board uses icons or visual seed groups, hide decorative duplicates with `aria-hidden="true"` and keep the numeric label available.

## Pre-PR Accessibility Checklist

Use this checklist before opening a Dara gameplay UI pull request:

- [ ] Pit controls are reachable by keyboard.
- [ ] Playable pits use semantic buttons.
- [ ] Disabled pits cannot be selected accidentally.
- [ ] Each pit exposes player, pit number, seed count, and selection state.
- [ ] Seed counts are displayed as text.
- [ ] Turn state is shown with text, not color alone.
- [ ] Important move results update visible status text.
- [ ] Important status changes are announced through a live region.
- [ ] Touch targets are comfortable on mobile widths.
- [ ] The board does not require horizontal scrolling on common phone widths.
- [ ] Focus remains visible and predictable after a move.
- [ ] Screenshots or notes are included for mobile and desktop review.

## Future Review Notes

When the first playable board implementation exists, contributors should test this plan against real gameplay flows and update it with any Dara-specific rules for captures, scoring, move validation, and end-game states.

