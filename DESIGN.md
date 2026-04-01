# Design System Documentation: The Executive Concierge

## 1. Overview & Creative North Star
The Creative North Star for this design system is **"The Precision Concierge."** 

In the world of corporate mobility, trust isn't built through loud colors or trendy patterns—it’s built through unwavering precision, editorial clarity, and an atmosphere of quiet competence. This design system rejects the "generic SaaS" aesthetic of heavy borders and flat cards. Instead, it adopts a high-end editorial approach, utilizing intentional asymmetry, expansive breathing room, and sophisticated tonal layering. 

We are not just building a booking tool; we are designing a premium service experience that feels as reliable and high-end as a chauffeured executive sedan.

---

## 2. Colors: Tonal Architecture
The palette is rooted in deep, authoritative blues (`primary`) and sophisticated, neutral grays (`surface` tiers). 

### The "No-Line" Rule
To achieve a bespoke, premium feel, **1px solid borders are strictly prohibited for sectioning content.** Boundaries must be defined solely through background color shifts. For example, a `surface_container_low` section sitting on a `surface` background creates a clear but soft structural division that feels modern and integrated.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers—like stacked sheets of frosted glass or fine stationery.
*   **Base:** `surface` (#f7f9fc)
*   **Low Priority/Main Content Areas:** `surface_container_low` (#f2f4f7)
*   **Interactive Cards/Modules:** `surface_container_lowest` (#ffffff) to create a subtle "lift."
*   **Elevated Overlays:** `surface_container_high` (#e6e8eb)

### The Glass & Gradient Rule
To move beyond "out-of-the-box" UI, use Glassmorphism for floating elements (e.g., car selection overlays). Apply a semi-transparent `surface_container_lowest` with a 20px backdrop blur. 
**Signature Textures:** Use a subtle linear gradient transitioning from `primary` (#00346f) to `primary_container` (#004a99) for primary CTAs and hero sections. This adds a "soul" to the interface that flat colors cannot replicate.

---

## 3. Typography: Editorial Authority
We utilize a dual-typeface system to balance character with functionality.

*   **Display & Headlines (Manrope):** This is our "Editorial" voice. Use `display-lg` and `headline-lg` with tight tracking (-2%) to create a sense of command and luxury.
*   **Body & Labels (Inter):** This is our "Functional" voice. Inter’s high x-height ensures legibility for complex data like car specs and booking times.

**Hierarchy Strategy:** 
Large, asymmetrical headlines (using `display-md`) should be used to anchor the page, while `label-md` in `on_surface_variant` is used for metadata to keep the interface from feeling cluttered.

---

## 4. Elevation & Depth: Tonal Layering
Depth is achieved through **Tonal Layering** rather than traditional structural shadows.

*   **The Layering Principle:** Place a `surface_container_lowest` card on a `surface_container_low` section. This creates a soft, natural lift.
*   **Ambient Shadows:** If a "floating" effect is required (e.g., a car preview modal), use an extra-diffused shadow: `blur: 40px`, `y: 12px`, `opacity: 6%`. The shadow color must be a tinted version of `on_surface` to mimic natural light.
*   **The Ghost Border:** For high-density data where separation is vital, use a "Ghost Border"—the `outline_variant` token at **15% opacity**. Never use 100% opaque borders.

---

## 5. Components

### Buttons & Interaction
*   **Primary:** A gradient fill (`primary` to `primary_container`) with `on_primary` text. Use `lg` (0.5rem) rounding for a modern, architectural feel.
*   **Secondary:** Use `secondary_container` with `on_secondary_container` text. No border.
*   **The "Micro-Shift":** On hover, primary buttons should shift 2px upwards with an ambient shadow, rather than changing color significantly.

### Status Badges (The "Signal" System)
*   **Available:** `secondary_container` fill with `on_secondary_fixed_variant` text.
*   **Occupied:** `tertiary_container` fill with `on_tertiary_container` text.
*   **Shape:** Use `full` (9999px) rounding for badges to contrast against the `lg` rounded corners of the containers.

### Intuitive Form Fields
*   **The Layout:** Abandon the 2-column grid. Use wide, single-column fields with `title-sm` labels positioned above the input.
*   **States:** Default state uses `surface_container_highest`. Focus state transitions to a `surface_container_lowest` background with a 2px `primary` bottom-border only (no full box border).

### Calendar & Date Selection
*   **The Grid:** Use `surface_container_low` for the calendar background. Selected dates use a `primary` circle. 
*   **Range Selection:** Use a soft `primary_fixed` rectangular background with `lg` rounding for the start and end of the range, creating a "pill" across the dates.

### Cards & Lists
*   **Forbid Dividers:** Use the `spacing-6` (1.5rem) or `spacing-8` (2rem) scale to create separation through white space. 
*   **Interaction:** List items should highlight using a subtle shift to `surface_container_high` on hover, rather than a border or heavy shadow.

---

## 6. Do's and Don'ts

### Do:
*   **Embrace Asymmetry:** Align headlines to the left while keeping car imagery or booking forms slightly offset to the right to create an editorial layout.
*   **Use the Spacing Scale:** Stick strictly to the defined scale. Use `spacing-12` (3rem) for section breathing room to maintain the premium feel.
*   **Prioritize Typography:** Let the `display` and `headline` scales do the heavy lifting for hierarchy, not bold colors.

### Don't:
*   **Don't use 1px Borders:** As stated, use background color shifts (`surface` vs `surface_container`) to define areas.
*   **Don't use Pure Black:** Always use `on_surface` (#191c1e) for text to maintain a soft, expensive look.
*   **Don't Over-shadow:** Shadows are a last resort for focus. Tonal layering is the primary method of depth.