```markdown
# Design System Strategy: The Cinematic Editorial

## 1. Overview & Creative North Star
The Creative North Star for this system is **"The Kinetic Poster."** 

We are moving away from traditional app-like interfaces that rely on cards and borders. Instead, we are treating the digital canvas as a high-impact, international event poster. The design breaks the "template" look through massive scale shifts, aggressive typography, and a total rejection of the "soft" web. By utilizing 0px corner radii across every element, we establish a prestigious, uncompromising, and architectural tone. The layout relies on intentional asymmetry and a dramatic vertical color shift to guide the eye from the cinematic void of the top region into the electric energy of the content below.

## 2. Colors & Tonal Depth
This system utilizes a high-contrast palette designed to evoke the atmosphere of a stadium-sized tech summit.

### The Palette Logic
- **Atmospheric Backgrounds:** Use `surface` (`#0e0e10`) for primary canvases. This creates a "black box" effect that allows photography and `primary` (`#94aaff`) accents to pop.
- **The Electric Shift:** The signature of this system is the transition from `surface` to `primary_dim` (`#3367ff`). Use this gradient behavior to anchor the bottom half of hero components.
- **The "No-Line" Rule:** 1px solid borders are strictly prohibited for sectioning. Boundaries must be defined solely through background color shifts. For example, a `surface_container_low` section sitting against a `surface` background is the only acceptable way to define a new content block.

### Surface Hierarchy & Nesting
Treat the UI as stacked sheets of rigid material. 
1. **Base Layer:** `surface` (The void).
2. **Nesting:** Place `surface_container_lowest` (`#000000`) elements inside `surface_container` to create "inset" depth without using shadows.
3. **The Signature Texture:** Use linear gradients transitioning from `primary` to `primary_container` for high-impact CTAs. This adds a "soul" to the UI that flat colors lack.

## 3. Typography
Typography is the primary architecture of this system. It is not just for reading; it is a visual element in itself.

- **Display & Headline (Space Grotesk):** These must be set with tight letter-spacing and heavy weights. They are designed to "shout." Use `display-lg` (3.5rem) to dominate the viewport.
- **Navigation & Metadata (Public Sans):** Use `label-md` or `label-sm`. These must be set in **ALL CAPS** with a wide tracking (0.1em to 0.15em). This creates a "technical" look that balances the aggressive headlines.
- **Body (Inter):** Use `body-md` for legibility. Keep line lengths short to maintain the editorial feel.

The contrast between the compressed, massive headlines and the tiny, wide-tracked labels creates the "Prestigious International Event" aesthetic.

## 4. Elevation & Depth
In a system with 0px roundedness and no borders, depth is achieved through **Tonal Layering**.

- **The Layering Principle:** Stacking `surface-container` tiers creates natural lift. Place a `surface_container_highest` element on top of a `surface_dim` background to signal importance.
- **Ambient Shadows:** Shadows are rarely used, but when a "floating" effect is required (e.g., a modal), use an extremely diffused shadow: `Box-shadow: 0 20px 50px rgba(0, 0, 0, 0.5)`. The shadow must feel like ambient occlusion, not a drop-shadow.
- **The "Ghost Border" Fallback:** If a container absolutely requires a boundary for accessibility, use the `outline_variant` token at **15% opacity**. Never use 100% opaque borders.
- **The Glass Exception:** While the header is strictly opaque and minimal, lower-level floating elements (like tooltips or status chips) may use a `backdrop-blur` with a semi-transparent `surface_bright` to maintain a sense of layered complexity.

## 5. Components

### Buttons
- **Primary:** `primary_fixed` background, `on_primary_fixed` text. 0px radius. Heavy weight.
- **Secondary:** `outline` ghost button with `on_surface` text.
- **Interaction:** On hover, the background should shift from `primary_fixed` to `primary_dim` with a 150ms linear transition.

### Navigation Bar
- **Style:** Extremely thin (max 64px height). 
- **Background:** Transparent or 5% opacity `surface`. 
- **Links:** `label-md` Public Sans, uppercase, wide-tracked. No icons; only text.

### Inputs & Fields
- **Container:** `surface_container_highest` with a bottom-only `outline` border (Ghost Border style).
- **Focus:** The bottom border transitions to `primary`. No "glow" or outer rings.

### Cards & Lists
- **Rule:** Forbid divider lines. Use `spacing-6` or `spacing-8` to separate list items. 
- **Structure:** Use background color blocks (`surface_container_low`) to group related items.

### Event Chips
- **Style:** Small, rectangular blocks. Background: `secondary_container`. Text: `on_secondary_container`. No rounded corners.

## 6. Do's and Don'ts

### Do
- **Do** use massive typography that intentionally bleeds or sits very close to the edge of the frame.
- **Do** use photography with a "dark/moody" treatment to blend into the `surface` background.
- **Do** utilize the "bottom-to-mid" gradient overlay on all hero images to ensure white text remains readable.
- **Do** maintain strict 0px edges on everything, including buttons and input fields.

### Don't
- **Don't** use soft shadows or "outer glows."
- **Don't** use standard 1px borders to separate content; it breaks the cinematic flow.
- **Don't** use standard sans-serif weights for headlines; if it doesn't look aggressive, it’s not bold enough.
- **Don't** use glassmorphism in the top navigation or primary hero blocks; keep those regions sharp and "flat-cinematic."
- **Don't** use icons as primary navigation elements. Use the "technical" wide-tracked text labels.```