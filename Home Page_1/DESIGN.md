# Design System Strategy: The Academic Modernist

## 1. Overview & Creative North Star
The design system for MISBA is guided by the **"The Digital Archivist"** North Star. This vision moves away from the "generic corporate portal" and toward a high-end, editorial experience that feels both historically grounded and technologically advanced. 

We achieve this through **Intentional Asymmetry** and **Tonal Depth**. Instead of a standard 12-column grid, we utilize generous "breathing room" (negative space) and overlapping elements where serif typography bleeds into image containers. This creates a bespoke, curated feel that mirrors the intersection of traditional business wisdom and modern data analytics.

---

## 2. Colors & The "No-Line" Rule
The palette is anchored in a deep, authoritative `primary` (#570000) and a prestigious `secondary` (#FFD700) gold. 

### The "No-Line" Rule
To achieve a premium feel, **1px solid borders are prohibited for sectioning.** We define boundaries through background shifts and tonal transitions.
- **Sectioning:** Use `surface_container_low` sections sitting on a `surface` background to denote a change in content.
- **Transitions:** Use `primary_container` (#800000) for full-width "interstitial" sections to break up long scrolls of white content.

### Surface Hierarchy & Nesting
Treat the UI as physical layers of fine paper.
- **Base:** `surface` (#f8f9fa).
- **In-Page Containers:** `surface_container_lowest` (#ffffff) for primary reading cards.
- **Secondary Modules:** `surface_container` (#edeeef) for sidebars or "Metadata" modules.

### The "Glass & Gold" Rule
To elevate the "Collegiate" aesthetic, use the `secondary_container` (Gold) sparingly. Rather than thick gold borders, use Gold as a **shimmering accent**:
- **Glassmorphism:** Use `surface_container_lowest` at 80% opacity with a `20px backdrop-blur` for navigation bars. This allows the `primary` maroon headers to bleed through softly.
- **Signature Textures:** Apply a subtle linear gradient from `primary` (#570000) to `primary_container` (#800000) on large hero sections to add "soul" and depth.

---

## 3. Typography
The system uses a high-contrast pairing: **Newsreader** (Serif) for authority and **Work Sans** (Sans-Serif) for clarity.

*   **Display & Headlines (`newsreader`):** Used for storytelling and brand-level statements. These should be set with tighter letter-spacing (-0.02em) to feel like a premium journal.
*   **Body & Labels (`workSans`):** Used for data-heavy MIS and Analytics content. The clean, geometric nature of Work Sans balances the traditional feel of the serif headings.
*   **Hierarchy Note:** Always lead with a `display-md` serif heading followed by a `label-md` uppercase sans-serif subhead in `secondary` gold for a "Masterclass" aesthetic.

---

## 4. Elevation & Depth
We eschew traditional shadows in favor of **Tonal Layering**.

*   **The Layering Principle:** Depth is achieved by "stacking." Place a `surface_container_lowest` card on a `surface_container_low` section. The subtle shift from #ffffff to #f3f4f5 creates a natural lift.
*   **Ambient Shadows:** When an element must "float" (e.g., a modal or floating action button), use a shadow with a 32px blur at 6% opacity. The shadow color must be a tint of `on_surface` (#191c1d), never pure black.
*   **The Ghost Border Fallback:** If a container needs more definition (e.g., a card on a white background), use a **Ghost Border**: `outline_variant` at 15% opacity. High-contrast, opaque borders are strictly forbidden.

---

## 5. Components

### Buttons
*   **Primary:** Solid `primary_container` (#800000) with `on_primary` text. No border. `rounded-md` (0.375rem).
*   **Secondary:** Ghost style. Transparent background with a `secondary` gold "Ghost Border" (20% opacity) and `on_surface` text.
*   **Tertiary:** Text-only in `primary` with a 2px underline in `secondary_fixed` that appears on hover.

### Cards & Lists
*   **Anti-Divider Rule:** Forbid the use of line dividers. Use `2rem` of vertical whitespace or a shift to `surface_container_low` to separate items.
*   **Analytics Cards:** Use `surface_container_lowest` with a 4px left-hand accent border in `secondary` gold to highlight key data points.

### Input Fields
*   **State:** Soft `surface_variant` backgrounds. On focus, the background shifts to `surface` and a 1px "Ghost Border" of `primary` appears. Labels are always `label-md` in `on_surface_variant`.

### Academic Accents (Custom Component)
*   **The "Citation" Block:** A specialized component for MISBA quotes or data insights. Uses a `primary_fixed` background with `newsreader` italic text and a `secondary` gold vertical bar on the left.

---

## 6. Do’s and Don’ts

### Do
*   **Do** use asymmetrical layouts where text blocks are offset from images.
*   **Do** leverage `tertiary` (#07274d) for small UI elements like "Analytics" tags to provide a nod to data/technology.
*   **Do** use large `display-lg` typography that intentionally breaks into the margin.

### Don’t
*   **Don’t** use "Alert Red" for errors if you can avoid it; use the `error` (#ba1a1a) token which is tuned to sit harmoniously with the Maroon palette.
*   **Don’t** use 100% opaque Gold for large surfaces; it should be an accent, a highlight, or a refined "Ghost Border."
*   **Don’t** use standard shadows. If it looks like a default Material Design shadow, it is too heavy for this system.