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
| **Vivid** (×4) | 120 | Unique, cool skins: above Natural, below Special. **Only restyles what the critter already has. Adds nothing.** |
| **Special** (×1) | 350 | The **only** tier that adds an epic new effect. Same body shape. |
| **Mythic** (×1) | 800 | Completely changes how the critter looks: shape changes, cool extras, all of it. |

### Vivid
- Themed and imaginative (Ballerina, Kimono, Tuxedo, Toy bricks…). Not natural-looking materials (wood, stone, marble), not real-world breads, not plain recolours.
- Don't reuse a theme another critter already has.
- **No shape changes.**
- **Adds no effects of any kind**: no new glows, particles, puffs, animations, sounds or behaviours. Before proposing a vivid, check each idea: "does the base critter already do this?" If not, it doesn't belong in a vivid.
- **Only restyles what the critter already has.** If the base critter has an effect (glow, spore puffs, babies, flowers, runes, gills, tongue, swallow lump), the skin gives that existing thing a themed look. It never adds one the base doesn't have.
- Small costume pieces are fine (a bow, a plume, a cape), and they may have a minor effect of their own: a cape flapping, a plume swaying, a candle flame glowing. Anything bigger, like smoke or steam puffs, belongs to Special.
- **Never remove anything the critter already has.**

### Special
- The only tier that adds new effects. One epic effect that suits the critter, for example the Amethyst golem's crystals or the Mochi bun's starch puff.
- Not a generic glow.
- **No shape change.**

### Mythic
- Completely changes how the critter looks: new shape, new parts, cool extras.
- Should still feel like a **skin**, not a new game mechanic. Keep its behaviour close to the critter's own.
- Gets its own sound effects (add each to the SFX table and give it a `GAP` entry).

## Testing
Smoke tests live outside the repo in the session scratchpad. Run them with `NPM_G=$(npm root -g) node X.js`:
- `roster.js`, `live.js`, `mythlive.js` for the critters and skins;
- `sndtest.js` for the sounds.
