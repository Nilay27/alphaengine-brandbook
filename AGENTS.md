# AGENTS.md - AlphaEngine Brandbook

## Engineering goals
- Keep the brandbook as a deterministic, standalone HTML/CSS deck.
- Preserve the AlphaEngine mark and existing visual system unless explicitly requested.
- Treat pitch-deck positioning as the strategic source of truth and PMF docs as product-accuracy source of truth.

## Runtime safety and non-negotiables
- Do not edit `deck-stage.js` unless a deck runtime bug requires it.
- Do not redraw or replace `img/logo.png`.
- Do not delete image assets; unused assets may remain.
- Keep visible brand copy free of unsupported performance, allocation, or privacy claims.

## Architecture boundaries
- `AlphaEngine Brand Book.html` is the primary interactive deck.
- `AlphaEngine Brand Book-print.html` is the print/export variant and should be synchronized intentionally, not accidentally.
- `brandbook.css` owns deck styling and should receive only scoped additions for new slide patterns.

## Testing requirements
- Count slides after structural edits.
- Search for prohibited legacy positioning terms after copy changes.
- Preview representative slides in a browser after layout changes.
- Verify no broken images and no obvious text overflow before delivery.

## Contract and change hygiene
- Keep the brandbook broad enough for AlphaEngine's long-term on-chain finance vision.
- Use "Simulate -> Verify -> Select" only in code-like contexts; visible brand copy should use the polished arrow.
- Document if the print HTML is not updated in the same pass as the interactive deck.
