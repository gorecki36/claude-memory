---
name: Visual creation process (two pipelines)
description: Two pipelines for creating visuals. Hero images/backgrounds via fal.ai (JSON prompt → generate-hero.py → PNG). Diagrams/data visuals via Figma MCP. Full process in Obsidian: Processes/Visual Creation for Presentations.md
type: reference
---

Two pipelines for presentation visuals:

**Pipeline 1: Hero images (fal.ai)**
- JSON prompt → `python3 scripts/generate-hero.py hero-images/prompts/{file}.json` → PNG
- Prompts saved in `~/Documents/marketing-embeddings/hero-images/prompts/`
- Images land in `~/Documents/marketing-embeddings/hero-images/images/`, MMA copies to `~/Documents/mma-global/images/`
- Styles: Newsletter = 3D sculptural, Essay = editorial ink sketch, Presentation = dark editorial
- fal.ai API, Nano Banana 2 model, FAL_KEY in ~/.zshenv

**Pipeline 2: Diagrams and data visuals (Figma MCP)**
- For labeled diagrams, frameworks, convergence visuals
- Workflow: whoami → create_new_file → use_figma (Plugin API) → get_screenshot → iterate
- Never use PowerPoint shapes or matplotlib

**When to use which:**
- Background/texture/illustration → fal.ai
- Diagram/framework/chart with labels → Figma
- Both → fal.ai for background, Figma for composition

**Full process with code snippets:** Obsidian vault `Processes/Visual Creation for Presentations.md`
