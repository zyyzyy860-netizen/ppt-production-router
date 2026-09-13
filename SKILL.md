---
name: ppt-production-router
description: "Generate distinctive blackboard, ink, or watercolor presentations from a topic alone. Defaults to a 10-slide editable PowerPoint; use for client-ready decks, not simple text edits."
---

# PPT Production Router

Use this skill to choose one primary production path before making a deck. The goal is a convincing, audience-ready result with the right kind of editability—not the most tools or the most familiar AI-slide look.

## House visual identity

Default to a hand-rendered visual system: **blackboard chalk**, **black-and-white ink**, or **watercolor**. Use the subject to choose among them; an explicit user style or an approved brand overrides this preference. Do not fall back to corporate cards, neon gradients, floating pills, or generic photo-and-sidebar layouts.

Read [hand-rendered-modes.md](references/hand-rendered-modes.md) before choosing an engine for a blackboard, ink, or watercolor brief.

## Topic-first default

Treat a topic-only request such as “做一个关于香蕉的 PPT” as complete. Do not ask the user to choose a tool, slide count, audience, delivery mode, or style.

Use these defaults unless the user says otherwise:

- **Deliverable:** 10-slide, 16:9 editable `.pptx`.
- **Visual direction:** select blackboard chalk for explainers/processes, black-and-white ink for analytical or cultural topics, and watercolor for nature/lifestyle topics.
- **Audience:** a general university classroom audience.
- **Content:** create a concise narrative arc, original illustrations as replaceable assets when useful, and native titles, labels, arrows, diagrams, and charts.
- **Workflow:** make the cover, one normal content page, and the densest page first; inspect the real output; then complete the deck.

Ask one concise question only when a provided template, brand, source file, language, factual dataset, or deadline is essential and missing. The only delivery-mode exception is an explicit request for a video insert, poster-like visual, or uneditable final image deck; then use `baoyu-slide-deck` and say that it is image-first.

## Operating rules

1. Pick one primary engine. Do not combine generators merely to use more tools.
2. Infer the production contract from the topic-first defaults. Do not expose this internal step to the user unless an exception requires a decision.
3. For a visual deck, decide whether it is **glance** (the point is clear in 3–10 seconds) or **editorial** (the audience can dwell for 30+ seconds). Do not mix both visual grammars casually. Read [editorial-visual-system.md](references/editorial-visual-system.md).
4. Make a cover, a typical content slide, and the densest/data-heavy slide first. Preview or open the actual export before generating the rest.
5. Give every slide one audience takeaway. A data slide must use a title that states the finding, then support it with an honest visual encoding, annotation, and source—not a decorative chart.
6. Reuse a small visual vocabulary that comes from the topic or source material: at most one type family, one color system, one grid logic, and 2–3 recurring content compositions. Avoid generic dark-gradient, neon-card, floating-pill, and dashboard tropes unless they are specifically supported by the brand or subject.
7. If a data claim cannot be encoded honestly, state it as text or obtain the missing data. Do not manufacture density with arbitrary dots, fake detail, meaningless microcharts, or decorative interaction.
8. For editable delivery, test the actual file at its intended runtime. Read [native-pptx.md](references/native-pptx.md).
9. Before delivery, run the anti-homogenization check in [editorial-visual-system.md](references/editorial-visual-system.md). If the deck could be relabeled for an unrelated AI topic without changing its visual logic, revise its art direction.
10. Keep claims and labels as native text. Generated art may be a background or replaceable illustration, but it is not editable structure.

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
