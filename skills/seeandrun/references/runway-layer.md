# Runway visual refinement for Seedance 2.5

Apply this layer to the user's existing direction after the Seedance task and asset roles are established. It is a craft checklist, not a second engine's prompt template.

## What to refine

- Replace an abstract performance instruction with a visible expression, gesture, gaze, pause, or posture that preserves the stated emotion. Do not turn an internal thought into newly invented dialogue.
- Identify the moving element. A rotating object under a stationary camera differs from a camera circling a stationary object. A physical push-in differs from a lens zoom; a pan rotates the view from one position.
- Make an existing camera instruction explicit enough to execute: subject, starting view, direction, speed, and what becomes visible. Do not automatically add all of these when the source is already clear.
- Relate background motion to the action when requested or established by the reference: impact and rebound, a step and displaced dust, or movement and trailing fabric. Preserve the central event and its ending state.
- In text-only generation, supply the requested visual world and its movement. In reference-led generation, let the asset provide established appearance and composition. Keep text focused on the requested changes while retaining asset bindings.
- Resolve contradictions in the intended result. A fixed view and an orbit cannot describe the same simultaneous camera behavior. Preserve the user's clear choice; clarify if incompatible choices are both essential.
- If a user reports a failed generation, change the element implicated by that result before rewriting everything. A longer prompt is not inherently better. Do not automatically produce several variants.

## Rules that must stay scoped to their source model

The Runway resource article's one-action, one-movement, and no-sequence-language advice is an introductory simplification strategy. Do not impose it on Seedance 2.5. Preserve multi-shot sequences and supported timing controls when they serve the user's story.

Runway Gen-4's positive-only advice does not erase Seedance's explicit negative controls. Desired-state language is useful, but requested no-subtitle or no-music requirements remain part of the Seedance prompt.

Camera-first ordering is an organization option. Runway's newer text-to-video documentation prioritizes clarity rather than placement. Keep the Seedance compiler's native organization.

## Small transformations

- "The camera rotates" becomes an explicit camera path around the named subject, when that path is what the user meant. Do not convert object rotation into a camera orbit.
- "She is nervous" can become a held gaze, tightened grip, or hesitant movement if those choices fit the user-authorized performance direction. Preserve the emotion and avoid adding new plot facts.
- "Make it cinematic" needs a concrete interpretation drawn from the requested genre or references. If no interpretation is supported and creative completion was not authorized, retain the broad preference without appending a camera/lens/lighting pack.

## Official sources checked on 2026-10-09

- General resource article: https://runway.com/resources/ai-video-prompting-guide
- Gen-4 scope and iteration: https://help.runwayml.com/hc/en-us/articles/39789879462419-Gen-4-Video-Prompting-Guide
- Visual detail and clarity: https://help.runwayml.com/hc/en-us/articles/46182941379347-Introduction-to-Prompting
- Text-to-video and ordering: https://help.runwayml.com/hc/en-us/articles/42460036199443-Text-to-Video-Prompting-Guide
- Image-to-video and sequential prompting: https://help.runwayml.com/hc/en-us/articles/48324313115155-Image-to-Video-Prompting-Guide
- Camera terminology: https://help.runwayml.com/hc/en-us/articles/47313504791059-Camera-Terms-Prompts-Examples
