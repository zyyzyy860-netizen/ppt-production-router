# Native PPTX delivery

Use this route when the recipient must edit the file in PowerPoint, especially when charts, tables, or a company template matter.

1. If an approved template or sample deck exists, preserve its non-negotiable elements. For a style family rather than a fixed master, use `deck-dna` with 2–3 representative decks before production.
2. Use `ppt-master` for native shapes, charts, tables, speaker notes, and template-aware work. Use `slide-skill` for deterministic SVG-to-PPTX output, fixed-template filling, or its validation workflow.
3. Prototype three representative pages before scaling: cover, normal content, and the densest page.
4. Open the exported `.pptx` in PowerPoint or the target Office viewer. Verify editable text, image replacement, chart behavior, fonts, overflow, and speaker notes.

Do not promise that image-derived graphics or arbitrary SVG effects will become data-backed native charts. If the user needs a data-editable chart, create and test one as a native chart before generating the full deck.
