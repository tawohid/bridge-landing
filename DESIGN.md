# Design System Specification: The Digital Sanctuary

## 1. Overview & Creative North Star
**Creative North Star: "The Editorial Sanctuary"**

This design system is not a utility; it is a facilitator. In the context of interpersonal work and difficult conversations, the interface must recede to allow the human emotion to breathe. We move away from the "app-like" world of buttons and borders and toward the world of high-end editorial matter. 

The aesthetic is governed by **Negative Space as Structure**. We break the traditional rigid grid by using intentional asymmetry—allowing text to hang in wide margins and using large-scale typography to create a sense of honesty and gravitas. The goal is a "designed to be deleted" experience: an interface so intuitive and calm that it disappears the moment the conversation begins.

---

## 2. Colors & Tonal Logic

### The Palette
We use a muted, sophisticated palette that avoids pure black and harsh whites to reduce eye strain and emotional friction.

*   **Surface (`#fbf9f6`):** Our "Heavy Matte Paper." Use this for the primary background.
*   **On-Surface/Ink (`#1b1c1a`):** A deep, warm charcoal for all primary text. Never use #000000.
*   **Terracotta Rose (`#854c45`):** Our signature accent. This is reserved for "Human Connection Points"—AI-facilitated insights, active listening prompts, or primary calls to action.

### The "No-Line" Rule
**Explicit Instruction:** Do not use 1px solid borders to section content. Boundaries must be defined solely through background color shifts or the spacing scale.
*   To separate a header from a body, use a transition from `surface` to `surface-container-low`.
*   To highlight a specific reflection or quote, use `surface-container`.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers of paper.
1.  **Base Layer:** `surface` (#fbf9f6)
2.  **Sectioning:** `surface-container-low` (#f5f3f0)
3.  **Emphasis/Cards:** `surface-container` (#efeeeb)
4.  **Interactive Elements:** `surface-container-highest` (#e4e2df)

---

## 3. Typography
Our typography is the primary carrier of emotion. We pair the intellectual depth of a humanist serif with the modern clarity of a warm sans-serif.

*   **Display & Headlines (Newsreader):** High-contrast and elegant. Use `display-lg` (3.5rem) for moments of deep reflection and `headline-md` (1.75rem) for section headers. The serif conveys honesty and the weight of the spoken word.
*   **Body & UI (Plus Jakarta Sans):** Minimal and warm. Use `body-lg` (1rem) for most text to ensure legibility. The sans-serif acts as the "modern facilitator"—it is clean, unobtrusive, and supportive.
*   **Labels:** Use `label-md` (0.75rem) in `secondary` (#5f5e5b) for metadata or helper text to keep the hierarchy quiet.

---

## 4. Elevation & Depth

### The Layering Principle
Standard shadows are prohibited. Depth is achieved via **Tonal Layering**. 
*   **Example:** A user’s reflection card (`surface-container-lowest`) sitting on a session background (`surface-container-low`) creates a soft, natural lift through value contrast rather than artificial drop shadows.

### The "Ghost Border" Fallback
If accessibility requirements (WCAG) demand a container definition that color shifts cannot solve, use a **Ghost Border**:
*   **Token:** `outline-variant` (#d7c2bf) at **15% opacity**. 
*   It should be felt, not seen.

### Glassmorphism & Softness
For floating navigation or ephemeral prompts, use semi-transparent surfaces with backdrop blurs.
*   **Floating Prompt:** `surface` at 80% opacity with a `blur(12px)`. This allows the "emotional warmth" of the background content to bleed through, making the tool feel integrated into the conversation.

---

## 5. Components

### Buttons (The "Soft Interaction")
*   **Primary:** Background `primary` (#854c45), Text `on-primary` (#ffffff). Shape: `md` (0.375rem). No shadow.
*   **Secondary:** Background `secondary-container` (#e2dfdb), Text `on-secondary-container` (#64625f).
*   **Tertiary (Editorial Link):** No background. Text `primary`. Underline only on hover using a 1px offset.

### Input Fields (The "Letter")
*   Inputs should not look like boxes. Use a background of `surface-container-low` with a generous `16` (5.5rem) internal padding. 
*   **Focus State:** Do not use a blue ring. Transition the background to `surface-container-high` and change the label color to `primary`.

### Cards & Lists
*   **Constraint:** Zero dividers. 
*   Use the **Spacing Scale** `8` (2.75rem) to separate list items. 
*   For grouped content, use a subtle background shift to `surface-container-lowest` (#ffffff) with a `xl` (0.75rem) corner radius.

### The "Reflection" Component (Unique to this System)
A specialized container for AI-generated insights or partner quotes. 
*   **Style:** `surface-variant` background, asymmetric padding (Top/Bottom: `10`, Left: `12`, Right: `6`).
*   **Typography:** Newsreader italic. This creates a visual "hush" in the interface.

---

## 6. Do’s and Don’ts

### Do
*   **Do** use extreme vertical whitespace. If it feels like too much space, add a little more.
*   **Do** use `primary` (#854c45) sparingly. It is a beacon of connection, not a branding tool.
*   **Do** align text to the left for long-form reading, but use centered `display-md` serif type for transitional moments.

### Don't
*   **Don't** use 100% black text. It is too aggressive for a sanctuary.
*   **Don't** use standard Material Design "elevated" cards with shadows. It breaks the matte paper metaphor.
*   **Don't** use motion that is "snappy" or "elastic." Use slow, ease-in-out transitions (300ms+) to mimic a deep breath.

### Accessibility Note
While we prioritize a "No-Line" aesthetic, ensure that color contrast between `surface` and `surface-container` tiers remains distinguishable for low-vision users. Use the `outline-variant` Ghost Border at 20% opacity if necessary for interactive field boundaries.