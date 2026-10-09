---
name: seeandrun
description: Optimize Seedance 2.5 video prompts with documented Seedance workflows and Runway visual direction principles. Use for rewriting briefs, scenes, stories, reference-based generation, video editing, or extension while preserving the user's story and asset mappings.
metadata:
  version: 1.0.0
  reference_date: 2026-10-09
---

# seeandrun

Turn the user's intended scene into a clear **Seedance 2.5** prompt. Use Seedance task semantics for references, editing, and extension, and Runway craft principles to clarify visible action and camera movement. If the user explicitly selects another model, honor it and use that model's own workflow.

## Relevant references

- Read [seedance-foundation.md](references/seedance-foundation.md) for intent preservation, reference roles, and the applicable task format.
- Read [runway-layer.md](references/runway-layer.md) to refine existing visual direction.
- For editing, extension, first/last frames, or a parameter conflict, also read [task-compatibility.md](references/task-compatibility.md).

These references are an independently authored implementation informed by the official documentation and the official sd25-pe v0.1.1 skill. The package is self-contained and does not redistribute the vendor's original skill. Reading it does not authorize installation, self-update, media generation, or paid API calls.

## Compile and refine

1. Preserve the story contract: identities and counts, setting, event order, causality, exact dialogue, prop ownership, spatial relations, final state, and requested exclusions. Improve expression without changing the story.
2. Choose the actual primary operation: new generation, editing one master, or extending a source in the requested direction. Treat keyframes, storyboard panels, blockouts, and sound references as task modules. Apply the compatibility reference when output settings conflict with editing.
3. Preserve all asset labels exactly. Inspect accessible assets; otherwise retain the user's declared roles without guessing or claiming inspection. Keep subjects and voices separately mapped. Account for known available unused references without activating them merely because they exist.
4. Use the relevant foundation format. For reference-led generation, let the assigned assets supply established identity and appearance. For editing, preserve inherited content outside the edit scope. For extension, continue from the boundary state without rewriting the original segment.
5. Apply Runway's visual clarity to the user's direction: distinguish subject and camera motion, clarify requested direction and speed, and connect actions to their established physical effects. Do not add camera moves, lenses, style, lighting, sound, dialogue, or extra events to fill a formula. New creative choices require a request for creative completion or alternatives.
6. Check physical and temporal continuity. Show cause before response, define important start and end states, and keep transferred objects single and traceable. Preserve a multi-step story rather than reducing it to a single action.

## Keep the guides in scope

- Prefer concrete desired states where they preserve intent. Retain requested exclusions such as no subtitles or no BGM. Do not add a generic negative pack. An absent dialogue script alone does not authorize closed mouths, silence, no narration, or a ban on signs.
- Preserve explicitly supplied event ranges. Use numerical timing when supplied or requested; do not invent timestamps from a page/API total duration. Resolve genuinely incompatible hard timings with one concise question.
- Camera/scene/action/details is a review lens, not a mandatory sentence order. Keep the task's asset bindings and structure.
- Keep total duration, ratio, resolution, frame rate, and audio toggle outside the submitted prompt. Report an actual mode conflict in a single settings note.
- Text asking for a first or last frame does not set the API role. Distinguish semantic references from actual first_frame/last_frame inputs and avoid guarantees of exact matching.
- Follow the requested output language, otherwise the input language. Translate template instructions semantically; keep exact spoken lines, asset labels, and explicit language, accent, and speaker placement.

## Delivery

Normally return one complete optimized prompt body. Internal task labels are welcome when useful; omit surrounding commentary, Markdown titles, and code fences. Include an asset or settings note only when necessary. Provide explanations, comparisons, settings, or alternatives when the user asks, keeping them outside the submitted prompt.

Before returning, check that identities, speech, labels, task scope, hard time requirements, and the final state survived. Visual refinements must serve the user and respect inherited edit content. Exact timing, frame reproduction, rendered text, lip sync, and exclusions are generation goals rather than guarantees.

Video generation, uploads, source-media changes, and paid API calls require a separately authorized execution workflow.

## Sources

- [BytePlus Seedance 2.5 prompting guide](https://docs.byteplus.com/en/docs/modelark/seedance-2-5-prompt-guide?redirect=1)
- [BytePlus Seedance 2.5 tutorial](https://docs.byteplus.com/en/docs/modelark/seedance-2-5)
- [Official sd25-pe distribution](https://arkdocs-en.tos-ap-southeast-1.volces.com/skills/)
- Runway sources and scope are recorded in [runway-layer.md](references/runway-layer.md).

The reviewed official sd25-pe version was 0.1.1 on 2026-10-09. This is a community skill, with no claimed affiliation or endorsement from BytePlus or Runway.
