# Design System Specification: Sovereign Authority

## 1. Overview & Creative North Star
The "Sovereign Authority" design system is built to project absolute reliability, institutional permanence, and high-security precision. Moving away from the "friendly SaaS" aesthetic, this system adopts a **"Digital Vault"** Creative North Star. 

The vault is characterized by weight, clarity, and intentionality. We break the standard template look by utilizing **Editorial Asymmetry**—where large, high-contrast typography is paired with expansive negative space to guide the eye through complex legal data. Instead of standard grids, we treat the screen as a series of heavy, layered plates. We prioritize a "Security-First" aesthetic where information is not just displayed, but "authenticated" through glassmorphism and light-reactive surfaces.

## 2. Colors & Tonal Architecture
The palette is rooted in deep, authoritative tones. We avoid pure black to maintain a sense of digital depth, utilizing charcoal and navy undertones to create a sophisticated, high-end environment.

### The "No-Line" Rule
**Explicit Instruction:** Designers are prohibited from using 1px solid borders to section content. Boundaries must be defined solely through background color shifts. For example, a `surface-container-low` component sits directly on a `surface` background. The eye should perceive the edge via the shift in luminance, not a physical stroke.

### Surface Hierarchy & Nesting
Treat the UI as a physical stack of materials.
- **Base Level:** `surface` (#131313) – The foundation.
- **Sectioning:** `surface-container-low` (#1C1B1B) – Used for broad content groupings.
- **Actionable Containers:** `surface-container-high` (#2A2A2A) – Used for primary cards.
- **Focus Elements:** `surface-container-highest` (#353534) – Used for active modal states or popovers.

### The "Glass & Gold" Accents
- **Primary Actions:** Use `primary` (#B6C4FF) for standard utilities, but reserve `secondary` (#F7BD48) for high-level "Official" actions.
- **Signature Textures:** For Hero sections or primary CTAs, use a linear gradient from `primary-container` (#1E3A8A) to `on-primary-fixed-variant` (#264191) at a 135-degree angle to provide a metallic, light-catching finish.

## 3. Typography
We utilize **Inter** to bridge the gap between technical precision and modern readability.

*   **Display (lg/md/sm):** Heavy, authoritative, and tight-tracked (-0.02em). Use for high-level statistics or page titles to establish dominance.
*   **Headline & Title:** Used for card headers. These should always be high-contrast (`on-surface`).
*   **Body (lg/md/sm):** Reserved for instructional text and form labels. Use `on-surface-variant` (#C5C5D3) for secondary information to ensure the primary data (the user's input) stands out.
*   **Label (md/sm):** All-caps with +0.05em letter spacing for metadata and tags. This mimics official government stamps and serial numbers.

## 4. Elevation & Depth
Depth in this system is achieved through **Tonal Layering**, not structural shadows.

*   **The Layering Principle:** To lift a card, do not add a shadow. Instead, move it from `surface-container-low` to `surface-container-high`.
*   **Ambient Shadows:** If an element must float (e.g., a critical notification), use a shadow with a 40px blur at 6% opacity, tinted with `primary` (#B6C4FF). This creates a "glow" rather than a "drop," suggesting the element is backlit by the system's power.
*   **The "Ghost Border" Fallback:** In high-density tables where separation is critical, use `outline-variant` (#444651) at **15% opacity**. It should be felt, not seen.
*   **Glassmorphism:** For overlays, use `surface-container` with a 12px backdrop-blur and 80% opacity. This maintains the context of the data beneath while creating a "secure frosted pane" effect.

## 5. Components

### Buttons
- **Primary:** High-gloss gradient (Police Blue) with `DEFAULT` (4px) rounding.
- **Secondary (The Brass Standard):** Solid `secondary-container` (#BA880F) with `on-secondary-container` text. This is for "Submit Application" or "Verify Identity."
- **Tertiary:** No background; `label-md` typography with a subtle underline on hover.

### Official Badges (Tags)
- **Approved:** `on-tertiary-container` text on a `tertiary-container` background.
- **Under Review:** `on-secondary-container` text on a `secondary-container` background.
- **Denied:** `on-error-container` text on `error-container` (#93000A).
- *Style Note:* Use `sm` (2px) rounding for badges to maintain a "stamped" official appearance.

### Input Fields
- **States:** Default inputs should be `surface-container-lowest` (#0E0E0E). On focus, the background remains dark, but a 1px "Ghost Border" of `primary` appears.
- **Labels:** Always use `label-md` positioned above the field, never inside as placeholder text.

### Cards & Lists
- **The "No Divider" Mandate:** Forbid the use of horizontal lines between list items. Use a `1.5` (0.375rem) vertical gap and a subtle background shift on hover (`surface-bright`) to denote individual rows.

### Security Visualizer (Context Specific)
A custom component for this system: A "Verification Progress" bar that uses a micro-shimmer gradient moving through the `primary` blue tones to indicate active data processing or background checks.

## 6. Do's and Don'ts

### Do
- Use **Asymmetric Layouts**: Place large headings on the left with supporting data blocks shifted to the right to create an editorial feel.
- Use **High Contrast**: Ensure `on-surface` text is always used for critical legal data.
- Use **Intentional Empty Space**: Allow the "Vault" to breathe; security is reflected in the lack of clutter.

### Don't
- **No Large Border Radii:** Never exceed `lg` (8px). Rounded "bubbly" corners undermine authority.
- **No Generic Grey Shadows:** Shadows must be tinted or avoided entirely in favor of tonal shifts.
- **No Pure White:** Never use #FFFFFF. Use `on-surface` (#E5E2E1) to maintain the dark-mode eye comfort and professional "paper" feel.
- **No Divider Lines:** Avoid the "Excel" look. Let the geometry of the blocks define the structure.