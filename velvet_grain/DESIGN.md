# Design System Strategy: The Editorial Epicurean

## 1. Overview & Creative North Star
The Creative North Star for this design system is **"The Digital Atelier."** We are moving away from the "template-clutter" of typical café sites and toward a high-end, editorial experience that feels as curated as a specialty pour-over. 

The goal is to evoke the tactile sensation of a heavy-stock paper menu and the warmth of a sun-drenched marble counter. We achieve this through **Intentional Asymmetry**: hero images should not always be centered; typography should overlap image containers (using `surface-container` tiers) to create depth; and whitespace (using our `spacing-24` tokens) must be treated as a functional element, not a void to be filled.

## 2. Colors & Tonal Architecture
The palette is grounded in organic warmth, utilizing a sophisticated Material Design 3 logic to manage depth.

*   **Primary (#442a22):** Our "Espresso Roast." Reserved for high-impact brand moments and primary CTAs. 
*   **Secondary (#924a28):** Our "Terracotta Accent." Used to draw the eye to interactive elements like "Book a Table" or "Today’s Special."
*   **Tertiary (#243522):** "Sage Leaf." A grounding, organic tone for success states or subtle environmental callouts.

### The "No-Line" Rule
**Borders are prohibited for structural sectioning.** To separate a "Menu" section from a "Gallery," do not use a `1px` line. Instead, transition from `surface` (#fbf9f4) to `surface-container-low` (#f5f3ee). Boundaries are defined by the physical shift in the "paper" color, not a drawn stroke.

### Surface Hierarchy & Nesting
Treat the UI as a series of stacked artisanal papers. 
*   **Base:** `surface` (#fbf9f4).
*   **Sectional Shifts:** Use `surface-container` or `surface-variant` to group related content.
*   **Cards:** Place a `surface-container-lowest` (#ffffff) card on a `surface-container` background to create a "lift" that feels natural and light.

### The "Glass & Gradient" Rule
For floating navigation bars or over-image labels, use **Glassmorphism**. Apply `surface-bright` at 80% opacity with a `16px` backdrop-blur. For Hero backgrounds, use a subtle radial gradient transitioning from `primary` to `primary-container` to add "soul" and dimension to the coffee-brown depths.

## 3. Typography: The Editorial Contrast
We pair the high-contrast elegance of **Newsreader** with the functional precision of **Manrope**.

*   **Display & Headlines (Newsreader):** These are your "flavor notes." Use `display-lg` for hero statements. The high-contrast serifs provide an upscale, boutique feel. Use `italic` variants sparingly for emphasis to mimic high-end food magazines.
*   **Body & Titles (Manrope):** These are your "service facts." Manrope provides a clean, modern counterpoint that ensures menu items and descriptions remain legible at any size.
*   **Hierarchy Tip:** Never center-align long blocks of body text. Keep `body-lg` left-aligned or use asymmetric "staggered" columns to maintain the editorial feel.

## 4. Elevation & Depth
Elevation is communicated through **Tonal Layering** and environmental light, never heavy dropshadows.

*   **The Layering Principle:** Depth is achieved by stacking. A `surface-container-highest` element sitting on a `surface` background provides all the "elevation" needed for a standard button or chip.
*   **Ambient Shadows:** For "floating" elements like Modals or floating Action Buttons, use a shadow with a 24px-32px blur, set to 6% opacity. The shadow color must be a tint of `on-surface` (#1b1c19), creating a soft, warm glow rather than a harsh grey stain.
*   **The "Ghost Border" Fallback:** If a container requires more definition (e.g., an input field), use the `outline-variant` token (#d4c3be) at **15% opacity**. It should be felt, not seen.

## 5. Component Logic

### Buttons
*   **Primary:** Background: `primary`. Text: `on-primary`. Shape: `md` (0.75rem). No shadow.
*   **Secondary:** Background: `secondary-container`. Text: `on-secondary-container`. 
*   **Tertiary (Editorial):** No background. Text: `primary`. Use an underline of `outline-variant` at 40% opacity that expands on hover.

### Cards & Lists
*   **Forbid Divider Lines:** Use `spacing-6` or `spacing-8` to separate menu items. 
*   **Layout:** Use `surface-container-low` for card backgrounds. Images should have `rounded-lg` corners to soften the "tech" feel.

### Input Fields
*   **Style:** Minimalist. Only a bottom border using `outline` at 20% opacity. Upon focus, the border transitions to `primary` at 100% opacity.

### Featured Components (Café Specific)
*   **The "Flavor Chip":** Use `tertiary-fixed-dim` for dietary tags (e.g., Vegan, Gluten-Free). The sage green provides a subtle, organic cue.
*   **The "Photography Portal":** Use `rounded-xl` for large imagery. Images should never be full-bleed squares; always use the rounding scale to maintain the "Soft Minimalism" aesthetic.

## 6. Do's and Don'ts

### Do:
*   **Do** use `spacing-20` and `spacing-24` to allow the design to breathe. High-end brands aren't afraid of "empty" space.
*   **Do** overlap elements. Place a `title-lg` description partially over an image container to break the grid.
*   **Do** use high-quality, warm-toned photography. The design system is a frame; the coffee and food are the art.

### Don't:
*   **Don't** use 100% black (#000000). Always use `on-surface` or `primary` for text to keep the "warmth."
*   **Don't** use `none` or `sm` rounding for main containers. It feels too clinical/corporate. Stick to `md` and `lg`.
*   **Don't** use standard "Load More" buttons. Use "Discover More" or "Explore the Menu" to maintain the editorial voice.
*   **Don't** use grid-lines or dividers. If you feel the need for a line, try a background color shift instead.