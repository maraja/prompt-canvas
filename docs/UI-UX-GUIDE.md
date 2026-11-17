# UI and UX guide: style, motion and craft

*Study notes from nine short design videos by Charles Liu ([@charles.unemployed](https://www.tiktok.com/@charles.unemployed)), compiled 17 Nov 2026 for Amit's projects. The full guide with source frames and clips lives on Amit's Mac at `Content/Design Research/tiktok-ui-ux-2026-11-17/UI-UX-reference-guide.html`.*

**This guide is about craft, not brand.** It covers hierarchy, interaction, motion and review habits. It never overrides a project's own brand system (colours, typefaces, logo, voice). Where the two disagree, the brand wins.

The lessons are the creator's design judgments, paraphrased. They are not measured results. Treat them as starting points and test them with real users and real content.

---

## 1. The working order: fix structure before polish
1. **Name the task.** What is the person trying to do, and what should happen next?
2. **Choose references.** Say exactly what you're carrying forward from each: type, spacing, density, colour or behaviour.
3. **Set a visual system.** Pick repeatable rules for type, surfaces, spacing, icons and corners.
4. **Clarify the composition.** Make the main content and the main action easy to find. Remove copy and containers that repeat what the layout already says.
5. **Complete the states.** Design the empty, loading, success, error and recovery states.
6. **Add purposeful motion.** Motion should show what changed, where it came from and what the action did.
7. **Review the real flow.** Check small screens, keyboard use, reduced motion, slow responses and failures.

## 2. Spot the generic "AI default" look
Each of these is a warning sign when it's used by habit, not a ban:
- unnecessary pill tags; decorative italics, or one italic word in a heading; Instrument Serif by default;
- letter spacing that's too tight; too much monospace; uppercase labels above every heading; section numbers that mean nothing;
- borders around every container; too many dividers; too many shades and opacities;
- needlessly elaborate mockups or diagrams; decorative code-path labels; dithering and ASCII art used as decoration;
- squircles everywhere; default gradient backdrops; a full stop on every title;
- long, repetitive copy.

**Judgment:** the problem is repetition without purpose. Keep tags, borders, diagrams and monospace when they carry real structure.

Trend motifs are ingredients, not a checklist: glass, cream surfaces, a dark gradient hero, three icon cards, moving logo strips, pulsing "available" dots, sparkles, pixel loaders, painted or classical imagery, endless canvases. Pick only what fits the product and its brand, and never stack them all on one screen.

## 3. Clean up the page before adding effects
- Show the **real product** and make the main feature the most prominent thing.
- Write a **concrete headline** and make **one main action** obvious.
- Group related content **with space**, not with boxes.
- Use one coherent design system, one icon family and one deliberate accent colour.
- Remove badges, duplicate labels and decoration that carry no information. Use ordinary styling for words that were italicised for no reason.
- **Concentric corners:** inner radius = outer radius − inset padding. Clamp it at zero, then check by eye.
- Raise text contrast. Prevent awkward heading breaks (widows and orphans). Align by visual weight (optical centre).
- Use **tabular numerals** for any value that changes.
- Show loading explicitly, and animate meaningful feedback.

## 4. Motion that explains
Starting values from the source. Tune them for the actual distance, device and task.

| Situation | Starting point |
|---|---|
| Entrances | ease-out (fast start, then slow down) |
| Movement within a view | ease-in-out |
| Dropdowns | 150–250 ms |
| List rows | stagger each by ~30 ms |
| Button press | scale to 0.97 |
| Popover entry | start near 0.95 scale, grow out of the control that opened it, and collapse back into it |
| Exit vs entry | exit about 20% faster than entry; overlap the outgoing and incoming states |
| Success | a single pulse |
| Moving knob | stretch ~12% in its direction of travel |
| Dragging | follow the pointer exactly; add growing resistance past the limits |
| Icon swaps | blend opacity, scale and blur |
| Secondary details | settle slightly after the main element |
| View changes | keep the same object recognisable (shared element transition); reveal with masks where it helps |
| Routine transitions | no overshoot |

Rules that always apply:
- Animations must be **interruptible**: when new input arrives mid-animation, retarget instead of finishing first.
- `prefers-reduced-motion` beats decorative motion. Give every flourish a simple alternative.
- Motion comes after the flow works, never instead of it.

## 5. Interaction patterns from the examples
- **Physical controls (age picker):**
  - make the selected value the focal point;
  - give it a wide drag hit area (Fitts's law) and keep one accent for the pointer only;
  - move numbers instead of swapping them; snap to valid values;
  - keep momentum after a flick, with an optional tick sound;
  - always keep keyboard and direct-entry alternatives.
- **Verification codes:**
  - quieter hierarchy, short instructions and high-contrast digit tiles;
  - submit automatically when the code is complete;
  - show distinct entry, checking, error and verified states;
  - use `autocomplete="one-time-code"`;
  - keep paste, correction, resend, expiry and recovery working.
- **Login that belongs to its product:**
  - one title and one main action;
  - imagery and a mark that relate to the product's task;
  - concentric corners and tinted shadows;
  - carry the same visual object into the signed-in view;
  - end on a satisfying moment (peak-end rule) without delaying access;
  - provide a reduced-motion version.
- **AI chat you can trust:**
  - task-specific starter prompts (recognition over recall);
  - real progress, never invented work or fake delays;
  - numbered citations that open their source;
  - reserve space before streamed text so the page doesn't jump;
  - link related text and chart marks with shared highlighting;
  - **ask before changing the user's data**;
  - optimistic updates need rollback or retry.

## 6. Review checks
| Area | Passes when |
|---|---|
| Hierarchy | A new visitor can say what the screen does and what to do next. |
| Composition | Every element adds meaning, and the real product has room to be understood. |
| Typography | No awkward breaks, no number jitter, readable secondary copy, a sensible line length. |
| Geometry | Curves, spacing and icon weight feel consistent, optically adjusted where needed. |
| Forms | The task works without a pointer, and errors say how to fix them, not only in colour. |
| Motion | Motion clarifies a relationship, responds to new input and never blocks the task. |
| Loading | Progress is truthful, the layout stays usable, and retry is available. |
| AI actions | Sources can be inspected, and changes are reviewed before they apply. Failures can be recovered. |
| Accessibility | WCAG 2.2: contrast of 4.5:1 for body text and 3:1 for large text; targets at least 24×24 CSS px (with the spacing exceptions); visible focus; full keyboard use; zoom and small screens work. |

## 7. Vocabulary for design notes
- **Kerning:** the space between one specific pair of letters. **Tracking:** spacing across a whole run of letters. **Leading:** the space between lines.
- **X-height:** the height of the lowercase letter bodies. **Line length:** the width of a text column.
- **Widow / orphan:** a stranded last word, or a lone line cut off across a break.
- **Tabular numbers:** digits that all take the same width.
- **Optical centre:** balance judged by how heavy things look, not by their measurements.
- **Tinted neutral:** a grey with a slight hue. **OKLCH:** colour given as lightness, chroma and hue.
- **Layout shift:** content jumping while the page loads. **Skeleton:** placeholders that hold the final layout's space.
- **Empty state:** the view before any content exists.
- **Optimistic update:** showing the change before the server confirms it.
- **Affordance:** a cue that something can be interacted with. **Touch target:** the whole tappable area. **Safe area:** the space clear of device notches and bars.
- **Combobox:** a text field combined with a list of options.
- **Progressive disclosure:** revealing detail only when it's needed.
- **Stagger:** offset start times for a group of animations. **Ease-out:** fast at first, then slowing down. **Origin-aware animation:** motion anchored to whatever triggered it.
- **Interruptible animation:** motion that can change target before it finishes.
- **Shared element transition:** the same object carried across two views.

Naming a technique doesn't prove it helps. Describe the change you can actually see.

## 8. Brief to hand a design agent
> Before designing, read this guide. Start with the person's task, the main action and the project's existing brand. The brand always wins. Pick a few references and say which qualities you're carrying forward: hierarchy, density, type, palette, material or motion. Build the core flow first: specific copy, the real product, related things grouped with space, and one main action per decision. Use a coherent type scale, palette, icon family, spacing scale and corner system. Remove decoration that doesn't explain the product, a state or the next action. Use tabular numerals for changing values. Design the empty, loading, success, failure and recovery states, and reserve layout space. Forms work with keyboard, paste and autofill, with clear inline feedback, and errors don't rely on colour alone. Check contrast, focus, touch targets, small screens and zoom. Add motion only after the flow works: anchor overlays to their controls, keep objects recognisable across transitions, start from the timing table and then tune it, follow the pointer while dragging, retarget on new input and honour reduced motion. For AI features: task-specific starting points, real progress, citations you can inspect, a review step before changing user data, and rollback when sync fails. Never fake work or add delays to build trust. Review at real sizes on desktop and mobile, including keyboard use, reduced motion, loading and failure.

## Sources
1. [Make an age picker feel physical](https://www.tiktok.com/@charles.unemployed/video/7703604691388697863)
2. [Recognise the repeated AI design defaults](https://www.tiktok.com/@charles.unemployed/video/7703999846109318408)
3. [Reduce the work of entering a verification code](https://www.tiktok.com/@charles.unemployed/video/7704297380790799634)
4. [Make motion explain the interaction](https://www.tiktok.com/@charles.unemployed/video/7704685504305876242)
5. [Treat visual trends as ingredients](https://www.tiktok.com/@charles.unemployed/video/7705095150845824257)
6. [Clean up the page before adding effects](https://www.tiktok.com/@charles.unemployed/video/7705468598260665618)
7. [Make a login screen belong to its product](https://www.tiktok.com/@charles.unemployed/video/7705480372376980754)
8. [Help people start and trust an AI chat](https://www.tiktok.com/@charles.unemployed/video/7705820001038601480)
9. [Use precise words when reviewing a design](https://www.tiktok.com/@charles.unemployed/video/7706223781462674740)

The accessibility figures are from WCAG 2.2. All of these sources are references, not universal rules.
