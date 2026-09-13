# PPT route map

Choose by the expected artifact, not by a tool's marketing label.

| Situation | Primary route | Why | Avoid as default |
|---|---|---|---|
| Video, keynote, or screen-recorded demo | `codex-slides`; use `frontend-slides` when a hand-crafted web aesthetic matters most | Visual canvas and browser preview make polish easy to inspect | Native-PPTX-first workflows unless the file must be handed off |
| Editorial or Swiss-style web talk | `guizang-ppt-skill` | Purpose-built layouts, presenter mode, and HTML output | Freeform tools that do not support the desired visual language |
| Client handoff with editable text/charts/template | `ppt-master` | Native PowerPoint objects and template-oriented delivery | Image-first deck generation |
| Fast deterministic editable deck / fixed template fill | `slide-skill` | SVG intermediate, editable PPTX, validation, and template-fill workflow | A visual-only web deck when Office editing is required |
| Match a client's established deck style | `deck-dna`, then `ppt-master` or `slide-skill` | Extracts design rules and real text-density limits from approved examples | Inventing a brand from a logo and a color alone |
| Image/PDF/screenshot must become editable | `GordenImage2PPTX` | Reconstructs background, frame, decoration, and text layers | Rebuilding every page from scratch unless fidelity is unimportant |
| Knowledge card or content that will remain image-first | `baoyu-slide-deck` | Strong visual storytelling through generated slide images | Formal client documents with frequent edits |
| Bespoke HTML visual system, mockup, or prototype-style slides | `baoyu-design` | Custom HTML-first design and flexible export paths | A strict corporate-template handoff |

## Installed workbenches and services

- `codex-slides` is an installed Codex plugin and is appropriate when the user wants a local, end-to-end slide studio.
- Presenton is a self-hosted/desktop presentation application with editable PPTX export and model-provider configuration. Deploy only on explicit request.
- LRriver/AIPPT is a full workbench for generation and page-level editing. Treat it as an app deployment, not a background skill.
- PPTAgent/DeepPresenter is a research-oriented agentic framework; its documentation states Windows use requires WSL and it may need models, Docker, and optional external services. Use only when the user explicitly wants that setup.

## Video-first default

For an educational video about AI-assisted PPT freelance work, use one visually impressive deck as the artifact and record its creation/preview. Start with `codex-slides` unless the user specifically wants an editorial web presentation (`guizang-ppt-skill`) or a fully bespoke visual direction (`frontend-slides`). The deck itself should show a believable client brief, an outline, a few polished slides, and the final export; do not turn the video into a catalog of tools.
