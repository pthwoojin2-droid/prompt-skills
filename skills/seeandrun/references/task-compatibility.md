# Seedance task and parameter compatibility

Use the actual input roles and the user's intended operation to select a mode. A natural-language instruction cannot itself change API roles. The rules below distinguish reference-led generation from edits and boundary inputs using the model documentation.

| Operation | Actual input/mode | Parameter relationship |
|---|---|---|
| Semantic reference generation | reference_image, reference_video, reference_audio | Output ratio and duration can be selected within model limits. A prompt asking an image to guide the beginning/end is approximate reference behavior. |
| First or first/last-frame generation | first_frame, optionally last_frame | ratio=adaptive; output ratio follows the first-frame input. Use compatible first/last image ratios. Duration is configurable. |
| Video editing | A unique reference_video master and editing intent | ratio=adaptive, duration=-1; preserve the master's ratio and approximate duration. Keep all unrequested content inherited. |
| Video extension | A unique reference_video source and extension intent | ratio=adaptive; preserve source ratio, specify forward/backward continuation, and keep the source segment unchanged. Duration is configurable. |

Do not label a semantic reference task as hard first-frame generation solely because the text says "Use Image 1 as the first frame." Preserve the requested boundary intent, and set or recommend the actual role only when the user is asking for settings or execution. During prompt-only rewriting, do not claim that you changed settings.

When a user asks to change the source ratio, or to change its duration beyond an explicit extension, do not classify the result as an ordinary edit. Use reference-led generation when reconstruction serves the request, or extension when continuation is the actual operation. If reconstruction would violate an essential promise of strict original preservation, ask one consolidated clarification rather than silently guaranteeing both. If the source settings are unknown, do not invent them or declare a conflict without evidence.

For a confirmed settings conflict, identify the operation as a newly generated video guided by the source, and place any necessary settings explanation in a single note outside the prompt. Do not add an editing disclaimer to every prompt that mentions a video reference.

An edited video's frame count or duration can differ slightly from its source. Reference frames, timestamps, subtitle exclusions, and dialogue synchronization guide generation; they do not establish guarantees of perfect reproduction.

Settings and service capabilities can change. Check current official documentation when answering parameter/API questions, validating an actual submission, or reconciling a version mismatch. Do not burden an ordinary text rewrite with network access solely for maintenance.

Official sources checked on 2026-10-09:

- https://docs.byteplus.com/en/docs/modelark/seedance-2-5-prompt-guide?redirect=1
- https://docs.byteplus.com/en/docs/modelark/seedance-2-5
- https://docs.byteplus.com/en/docs/modelark/create-video-generation-task-api
