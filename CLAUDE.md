# Mossjar Terrarium

A single-file pixel pet game: everything lives in `index.html`. The player uses a phone in portrait.

## General rules
- Don't change existing music or visuals without asking first.
- Menus must not change size.
- The Fun interface is the only interface (the Basic option was removed).
- A critter may have more than one Mythic skin when the user asks for it (the snake has two).
- Every sprite and accessory is procedural: built from `fb.cap` / `fb.box` shapes and lit by `composite`. No hand-placed pixel sprites.
- Glows should look like real light, not a flat tint.

## Critter skins (swatches)
Skins are bought from the swatch row in the Critters menu. Each critter gets one at a time, in this order:
1. Text concepts first.
2. Then a concept image sheet.
3. Then implementation.

| Tier | Price | What it may change |
|---|---|---|
| **Natural** | 40–60 | Real-world colour morphs of the actual species. Palette only. |
| **Vivid** (×4) | 120 | A **skin change only**: a themed pattern on the same shape, face and behaviour. |
| **Special** (×1) | 350 | An effect on the same body shape. |
| **Mythic** (×1) | 800 | The **only** tier allowed to change the body's shape. Still just a skin. |

### Vivid
- Themed and imaginative (Ballerina, Kimono, Tuxedo, Toy bricks…). Not natural-looking materials (wood, stone, marble), not real-world breads, not plain recolours.
- Don't reuse a theme another critter already has.
- **No shape changes.**
- **No unique effects or new glows.** Small accessories are fine; an accessory may have a tiny effect when it makes sense (the Party bun's candle flame glows).
- **Never remove anything the critter already has.** Restyle its existing features instead:
  - If it has babies, flowers, runes or gills, the skin gives them a themed replacement.
  - If it already glows, the skin glows in its own colours.

### Special
- One effect that suits the critter, for example the Amethyst golem's crystals or the Mochi bun's starch puff.
- Not a generic glow.
- **No shape change.**

### Mythic
- May change the body's shape and look all the way.
- Should still feel like a **skin**, not a new game mechanic. Keep its behaviour close to the critter's own.
- Gets its own sound effects (add each to the SFX table and give it a `GAP` entry).

## Testing
Smoke tests live outside the repo in the session scratchpad. Run them with `NPM_G=$(npm root -g) node X.js`:
- `roster.js`, `live.js`, `mythlive.js` for the critters and skins;
- `sndtest.js` for the sounds.
