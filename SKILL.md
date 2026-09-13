---
name: ppt-production-router
description: "Create distinctive blackboard, ink, or watercolor presentations with an explicit choice between editable live-demo decks and image-first final visuals. Use for client-ready decks; not for simple slide text edits."
---

# PPT Production Router

Use this skill to choose one primary production path before making a deck. The goal is a convincing, audience-ready result with the right kind of editability—not the most tools or the most familiar AI-slide look.

## House visual identity

Default to a hand-rendered visual system: **blackboard chalk**, **black-and-white ink**, or **watercolor**. Use the subject to choose among them; an explicit user style or an approved brand overrides this preference. Do not fall back to corporate cards, neon gradients, floating pills, or generic photo-and-sidebar layouts.

Read [hand-rendered-modes.md](references/hand-rendered-modes.md) before choosing an engine for a blackboard, ink, or watercolor brief.

## Start with the delivery constraint

Ask only if the answer is not evident from the request:

- Must the recipient edit text, tables, charts, or a mandated template in PowerPoint? Read [native-pptx.md](references/native-pptx.md).
- Is this an on-screen talk, demo video, or shareable web presentation where visual impact matters more than native editing? Read [visual-deck.md](references/visual-deck.md).
- Is the source a screenshot, PDF page, or image deck that needs editable reconstruction? Read [reconstruction.md](references/reconstruction.md).
- Does the user want an installed workbench or self-hosted service rather than a one-off deck? Read [workbenches.md](references/workbenches.md).

Also establish whether the user needs an **editable live-demo deck** or an **image-first final visual**. Never describe the latter as fully editable.

If there is no fixed delivery constraint, default to an HTML/image-native deck for a video or live presentation, and native PPTX for a client handoff.

## Operating rules

1. Pick one primary engine. Do not combine generators merely to use more tools.
2. Write a production contract before design: delivery format, reader context, required editability, source-data status, and the target reading speed. Do not let a tool silently redefine any of these.
3. For a visual deck, decide whether it is **glance** (the point is clear in 3–10 seconds) or **editorial** (the audience can dwell for 30+ seconds). Do not mix both visual grammars casually. Read [editorial-visual-system.md](references/editorial-visual-system.md).
4. Make a cover, a typical content slide, and the densest/data-heavy slide first. Preview or open the actual export before generating the rest.
5. Give every slide one audience takeaway. A data slide must use a title that states the finding, then support it with an honest visual encoding, annotation, and source—not a decorative chart.
6. Reuse a small visual vocabulary that comes from the topic or source material: at most one type family, one color system, one grid logic, and 2–3 recurring content compositions. Avoid generic dark-gradient, neon-card, floating-pill, and dashboard tropes unless they are specifically supported by the brand or subject.
7. If a data claim cannot be encoded honestly, state it as text or obtain the missing data. Do not manufacture density with arbitrary dots, fake detail, meaningless microcharts, or decorative interaction.
8. For editable delivery, test the actual file at its intended runtime. Read [native-pptx.md](references/native-pptx.md).
9. Before delivery, run the anti-homogenization check in [editorial-visual-system.md](references/editorial-visual-system.md). If the deck could be relabeled for an unrelated AI topic without changing its visual logic, revise its art direction.
10. For blackboard, ink, or watercolor work, keep claims and labels as native text whenever live editing or later revision is required. Generated art may be a background or replaceable illustration, but it is not editable structure.

Keep slide text short. If a page overflows, cut or split content; do not solve it by shrinking type. Use provided reference decks/templates as the source of truth for fixed branding, logos, footers, and layout constraints. Never install, start, deploy, sign into, or configure a workbench/service unless the user asks for that action.

## Existing capability selection

Use the named skill only after selecting its route. If the named skill is unavailable, state that and choose the closest installed route instead.

- `codex-slides`: end-to-end visual deck creation with a local studio and export.
- `frontend-slides` or `guizang-ppt-skill`: polished HTML presentation for a live talk or video.
- `ppt-master` or `slide-skill`: editable `.pptx`, templates, data, and formal delivery.
- `deck-dna`: derive a visual system from 2–3 approved reference decks before building a new branded deck.
- `GordenImage2PPTX`: reconstruct an image-first or PDF-page deck for local text/layout edits.
- `baoyu-slide-deck`: image-first knowledge decks when later editing is unlikely; it generates complete slide images and merges them into a PPTX.
- `baoyu-design`: HTML-first custom visual design or prototype-style slides. Use it for a live editable browser deck and, where its exporter is available, native PPTX text/shapes.

For selection criteria and uninstalled project boundaries, read [route-map.md](references/route-map.md).
