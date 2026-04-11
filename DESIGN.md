# Design System Documentation: Kinetic Vanguard

## 1. Overview & Creative North Star

### Creative North Star: "The Kinetic Vanguard"
This design system is a departure from the quiet luxury of 'Noir & Gilt' toward a high-frequency, aggressive editorial aesthetic. It is built on the tension between the industrial weight of heavy sans-serif typography and the intellectual elegance of classical serifs. 

The system moves away from "templates" by embracing **intentional asymmetry** and **kinetic energy**. We do not guide the user through a quiet gallery; we propel them through a high-impact narrative. By stripping away all rounded corners and traditional borders, we create a visual language of sharp precision and raw power.

## 2. Colors

The palette is dominated by a high-contrast relationship between a surgical white background and a visceral, blood-red primary.

### Color Tokens (Material Design Mapping)
*   **Primary (`#bb0100`):** The engine of the system. Used for high-impact typography, primary actions, and kinetic accents.
*   **Background (`#f6f6f6`):** A slightly off-white "paper" gray that prevents retinal fatigue while maintaining high contrast.
*   **Surface Hierarchy:**
    *   `surface-container-lowest`: `#ffffff` (For the highest lift/floated elements).
    *   `surface-container`: `#e7e8e8` (For standard section nesting).
    *   `surface-container-highest`: `#dbdddd` (For the deepest recessed areas).

### The "No-Line" Rule
**Explicit Instruction:** Designers are prohibited from using 1px solid borders to define sections or containers. Boundary definition must be achieved through:
1.  **Hard Tonal Shifts:** Placing a `primary` section directly against a `surface` section.
2.  **Surface Nesting:** Using a `surface-container-low` block to hold content on a `surface` background.
3.  **Negative Space:** Using aggressive white space to dictate grouping.

### Signature Textures & Blending
To achieve a "high-end editorial" feel, utilize **Color Blending Effects**. Headlines should occasionally use `mix-blend-mode: difference` when overlapping imagery or secondary containers. Incorporate a subtle "film grain" overlay on `primary` backgrounds to add organic depth to the digital red.

## 3. Typography

Typography is not a support element in this system; it is the **architecture itself**.

### The Typeface Pairing
*   **Inter (Sans-Serif):** The "Heavy" voice. Used for `display`, `headline`, and `label` scales. It should be tracked tightly (-0.02em to -0.04em) in display sizes to feel architectural and urgent.
*   **Newsreader (Serif):** The "Elegant" voice. Used for `body` and `title` scales. This provides a sophisticated, human counterpoint to the aggressive sans-serif.

### Kinetic Scale
*   **Display-LG (3.5rem / Inter):** Used for "Statement Typography." Can be broken across lines or rotated 90 degrees for kinetic effect.
*   **Body-LG (1rem / Newsreader):** Used for editorial storytelling. Ensure generous line-height (1.6) to contrast with the tight tracking of the displays.
*   **Label-MD (0.75rem / Inter Bold):** All-caps. Used for metadata and navigation to maintain a technical, "blueprint" feel.

## 4. Elevation & Depth

### The Layering Principle
Depth is achieved through **Tonal Layering** rather than traditional drop shadows. We treat the UI as stacked sheets of heavy cardstock.
*   **The Sharp Edge:** All components must have a `0px` border-radius. No exceptions.
*   **Shadows as Glows:** If a floating effect is required (e.g., for a high-priority modal), use an **Ambient Shadow**. The shadow must be large, diffused (40px+ blur), and tinted with the `primary` red at 5% opacity to simulate a light-bleed rather than a "shadow."

### The "Ghost Border" Fallback
If a visual separator is functionally required for accessibility, use a **Ghost Border**: `outline-variant` (`#acadad`) at 15% opacity. This provides a "suggestion" of a line without breaking the minimalist aesthetic.

## 5. Components

### Buttons: The Kinetic Trigger
*   **Primary:** Solid `primary` (`#bb0100`) background with `on-primary` (`#ffefed`) text. 0px radius. Hover state: `primary-dim` with a 4px horizontal shift of the text to imply motion.
*   **Secondary:** Ghost style. No background, `primary` text, and a `Ghost Border`. 
*   **Tertiary:** All-caps `label-md` with a `primary` underline that expands from center on hover.

### Cards & Editorial Modules
*   **Rule:** Forbid the use of divider lines within cards.
*   **Implementation:** Use a `surface-container-low` background. Content hierarchy is defined by the switch between Inter Bold and Newsreader Italic.
*   **Image Handling:** Images should be treated with a high-contrast black-and-white filter or a red duotone to sit within the brand's energetic aesthetic.

### Input Fields
*   **Style:** Minimalist underline only. The line color is `outline-variant`. On focus, the line transforms into `primary` and thickens to 2px.
*   **Error State:** Use `error` (`#b41340`) for the underline and helper text.

### Progress & Loading
*   Use a "Strobe" effect or a fast-moving horizontal bar using the `primary` color. Movement should feel "mechanical" (linear easing) rather than "organic" (ease-in-out).

## 6. Do’s and Don’ts

### Do:
*   **Do** lean into extreme scale. Make headlines "uncomfortably" large.
*   **Do** use Newsreader Italic for emphasis within Inter headlines to create a signature editorial "flicker."
*   **Do** allow elements to overlap. A red headline can partially obscure an image to create depth.
*   **Do** maintain 100% sharp corners on everything from buttons to image masks.

### Don’t:
*   **Don't** use 1px black borders. It cheapens the high-end editorial feel.
*   **Don't** use rounded corners (`border-radius: 4px`, etc.). It breaks the "Kinetic Vanguard" spirit.
*   **Don't** use standard "Material" easing for animations. Use "Power4.out" or "Linear" to maintain an aggressive, modern energy.
*   **Don't** use soft grays for text. Use `on-background` (`#2d2f2f`) for maximum legibility and "punch."