# Seedance 2.5 prompting foundation

An original working reference for seeandrun. It supports Seedance task planning; the companion Runway layer helps clarify visual direction. It produces prompt text, not uploaded assets, media edits, or a generation request. Task selection and service settings are covered in [task-compatibility.md](task-compatibility.md).

## Establish the brief

Before rewriting, identify the intended operation and the facts that must survive it: each subject and count, the setting, ordered events, their causes, relationships, important props and their owners, speech, and the ending state. Preserve requested inclusions and exclusions. Keep shot numbers and asset numbers as identifiers rather than interpreting them as camera angles.

Improve how the brief can be seen and heard without replacing its story. Make an existing movement, expression, or camera instruction clearer where needed. Do not fill gaps with new lighting, style, camera moves, sounds, dialogue, or generic exclusion packs. Broad creative completion is appropriate only when authorized.

For a long source, use the requested scene, trailer, or overview scope. If no scope is given, select a causally complete event only when that choice is clear from context. Ask one consolidated question when equally plausible choices would produce different core stories. Remove repetitive exposition while retaining required events and speech.

## Establish the inputs

- With text alone, write from the supplied facts. Do not invent references or require assets merely to rewrite a prompt.
- Retain every established asset label exactly, including its spacing and syntax. An unavailable, damaged, or unreadable reference keeps its user-declared role. Do not claim to have inspected it or infer its content from a filename or URL.
- Inspect accessible media within tool limits. For video, check subjects, action, cuts, and boundary states; for audio, check its content and intended function. Sparse previews do not support an exhaustive inventory or precise source timeline.
- Bind each used asset to a specific contribution: a subject, prop, setting, action, camera pattern, voice, dialogue, or sound category. State only features actually observed or supplied by the user.
- Give each subject a separate binding. A single-person image does not define two simultaneous named people. Multiple views can jointly define one subject when that relationship is established.
- User assignments take precedence over automatic matching. Do not activate similar spare assets to reinforce a role already covered. Select additional assets only to fill a required gap or when the user asks for selection or combination.
- For supplied assets without labels, use known runtime labels or stable aliases by media type and supplied order. Keep the source-to-alias correspondence; do not fabricate missing assets or expose internal service IDs as prompt prose.
- Identify every known available asset left unused, by its exact label, inside the prompt. Do not invent an unused set when the inventory is unavailable. Inactive assets have no contribution to people, props, setting, action, camera, or sound.

Resolve an ambiguous identity mapping from context where possible. If two mappings are equally credible and would change the result, include that ambiguity in one necessary question rather than presenting a guess as a fact.

## Build one primary task

The following are drafting patterns, not required headings. Replace bracketed content and omit empty lines. Translate optional section labels into the output language. Merge sections when a short paragraph communicates the same information clearly.

### New footage from text

```text
[Named subjects and starting situation].
[Ordered visible events, including the trigger before its reaction].
The sequence finishes with [positions, prop ownership, and final condition].
[Only the visual, camera, and audio direction supplied or authorized by the user].
```

Keep a prop transfer continuous: who initially holds it, when the receiving person takes it, and who holds it at the end. Distinguish an actual injury or breakage from pretending, a near miss, or an intact object. A natural consequence may accompany the main change; preserve multi-step stories rather than forcing everything into one action.

### New footage guided by references

```text
Brief: [the requested scene or sequence].
Bindings:
[Exact asset label] supplies [one subject or element] with [adopted attributes or behavior].
[Another exact label] supplies [its separately bounded contribution].
Progression: [opening condition] → [ordered actions and visible causes] → [ending condition].
Carry through: [identity, count, spatial, prop, and audio relationships needed for continuity].
Inactive inputs: [each known unused label], with no role in this sequence.
```

Let references supply their established appearance rather than repeating speculative descriptions. Where an asset contains unrelated people, scenery, or sounds, bound the adopted contribution so those elements are not accidentally imported. This is reference scoping, not a generic negative prompt.

### Change one source video

Designate one video as the master. An action or blockout reference is not automatically an editing master. Use the compatibility reference before routing a specification conflict.

```text
Master: [exact video label] supplies the existing footage and its timeline.
Change: [original target] becomes [requested target], limited to [region, attribute, count, and any supplied event interval].
Replacement input: [exact label and the attributes it contributes, if a replacement asset exists].
Inherited behavior: [replacement or affected element] follows its original appearances, movement, occlusions, and exits.
Retained content: [explicit adjacent content that matters]; every element outside the stated edit scope keeps its source behavior and appearance, including other subjects, props, background, shots, event order, and unmodified audio.
```

For additions and removals, specify the requested quantity, location, and presence interval where supplied or observable. A background change applies outside the retained subject's outline. A replacement follows the original target's movement slot rather than introducing another instance beside it.

Inventory visible categories when the whole master is inspectable; assign only the requested changes and keep the remainder. With limited access, state the explicit targets and close the scope over all other visible elements without claiming a complete inventory. If the user instead requests retaining only named elements, make that removal scope explicit: retain those elements and remove the remaining visible subjects as requested. Do not silently widen a local edit to an entire group.

Keep camera work, actions, cuts, timing, and sound outside the requested scope inherited from the master. Add an event condition only when it is stated or observed reliably; do not reconstruct the source timeline from sparse frames.

### Change only sound in the master

```text
Master: [exact video label] supplies the footage and speaking windows.
Audio change: [speaker or category] receives [requested removal, replacement, or adjustment] during [the stated scope].
Audio binding: [exact audio label] contributes [voice, words, music, ambience, or effect], if supplied.
Retained content: the source visuals, actions, mouth movement timing, camera work, cuts, and all audio outside this scope continue unchanged.
```

Removing music needs no invented replacement clip. A voice change retains the existing words and speaking times unless the user also requests a rewrite. An authorized language change preserves meaning and speaker assignment; do not add lines or change the visual performance to fill the new recording.

### Add footage before or after a source

Use one source and an explicit extension direction. If the direction is unresolved, ask one consolidated question. Generate the new segment beyond the boundary; keep the original segment unchanged.

```text
Source and direction: [exact video label], [continue after its ending / add a lead-in before its beginning].
Join state: [confirmed or user-declared subject pose, orientation, prop state, layout, camera view, lighting, motion trend, and existing audio state at the relevant boundary].
New passage: [the requested continuation, or the preceding action that arrives at the source's opening state].
Continuity: each continuing subject remains one instance, without splitting into separate copies, with consistent structure and parts through turns, occlusions, exits, and returns. [Any additional established identity, prop, scene, or audio relationships].
```

For a forward extension, begin the new passage from the source's final state. For a backward extension, end the new passage at the source's initial state; do not introduce elements that belong only later in the story. Additional references can guide requested details but must not replace the source boundary state.

## Add only the modules the task needs

### Boundary images and intermediate states

Identify each image separately as the intended opening state, closing state, or intermediate state. Describe the visible positions, poses, prop condition, and view that matter, then connect those states with the requested action. For several images, list their order explicitly and give each its own state; do not hide distinct bindings in a range.

```text
Opening target: [label and its required state].
Next state: [label and the change reached here, with supplied event time if any].
Closing target: [label and its required final state].
Transition: [continuous actions linking the states in that order].
```

Prompt intent and actual `first_frame` / `last_frame` input roles are different. Preserve a requested boundary without claiming that wording changed API settings. Intermediate references guide meaningful states rather than automatically creating static holds. Neither semantic references nor actual boundary roles justify a promise of perfect frame reproduction.

### Storyboard panels

Bind the grid or storyboard label, its reading order, each panel's shot function, and the ending state. Refer to panel positions within the actual asset rather than inventing upload labels for individual panels. Keep character, prop, and setting references separate. Carry across only the requested shot order and composition; identify any present sketch conventions, annotations, or stand-ins that are production guidance rather than final scene content.

```text
Board: [label], read [the intended panel order].
Panel [position]: [the corresponding shot, event, and visible state].
Panel [position]: [the next shot and resulting state].
Final appearance and audio: [only the supplied direction and bindings].
```

### Blockout footage

For a coarse blockout, map each relevant geometric stand-in individually to its final subject or prop, then name the blocking, paths, camera work, cuts, or rhythm to inherit. Supply final appearance from the user's text or assigned references.

For a detailed blockout, preserve its established structures, actions, and spatial relationships while applying the requested surfaces, appearance, or environment. State which visible production markers are scaffolding rather than scene content. Treat the blockout as a generation reference unless the intended operation establishes it as the master.

```text
Layout guide: [label and whether it supplies coarse movement or detailed structure].
Object mapping: [one stand-in] → [one final subject or prop].
Inherited information: [the specific layout, action, or camera contribution].
Rendered content: [requested appearance, materials, setting, and assigned references].
```

### Speech and other audio

Bind voice, spoken content, music, ambience, and effects as different contributions. In each speaking beat, identify the speaker, their audio reference if any, exact supplied words, delivery, requested language or accent, and whether the voice is on-screen or off-screen. Preserve user-established notation and exact speech, including a fragment that is not a full sentence. Do not expand a fragment or turn a speaking intention into invented dialogue.

When a character is meant to speak from an audio reference whose words cannot be verified, retain that speaking role and reference without inventing a transcript. Keep different speakers and voices distinct. Add language or accent instructions only when given or clearly established; do not infer a regional accent from English text or a spoken language from a writing system.

An absent dialogue script does not mean silence, closed mouths, no narration, or no signs. Apply such restrictions only when requested. Preserve specified sound sources and speaking states; do not append a music track, generic ambience, or a subtitle ban.

## Check time and delivery

- Keep supplied hard event times and ranges as requirements, with their original values. Use numeric event timing when the user provides it or explicitly asks for it; otherwise organize by stages, shots, and causal order. Do not manufacture event timestamps from a page or API total duration.
- If required times cannot coexist with the required events, ask one consolidated question about the conflicting requirements. Do not silently drop a time, compress away a required event, or promise exact alignment.
- Keep total duration, ratio, resolution, frame rate, and the audio toggle outside the submitted prompt. Follow [task-compatibility.md](task-compatibility.md) for mode routing and locked settings.
- Check the final state, subject count, prop ownership, asset labels and roles, speech, and every requested scope boundary. Ensure no placeholders remain.
- Use the requested output language; otherwise keep the input language. Retain exact labels and quoted speech even when surrounding instructions are translated.
- Normally deliver one complete prompt body, with optional internal labels and no preface, title, reasoning, or code fence. Include each known unused asset inside it. Provide alternatives, explanations, comparisons, or settings outside it when the user asks for them.
- Add at most one concise asset/parameter note when an actual hard input limit or setting conflict requires action before submission. Do not add a missing-reference warning merely because media could not be inspected. Verify current official limits when validating a real submission rather than treating this reference as an API specification.
- Preserve demands for exact text, synchronization, or boundary states, but do not guarantee perfect lettering, lip sync, frame matching, or event timing. An expressly requested sequence of operations may use a separate prompt per operation, with the preceding result named as the next master.

## Functional sources

These links document the model and official distribution. This original reference does not bundle or reproduce the vendor skill snapshot.

- [BytePlus Seedance 2.5 prompt guide](https://docs.byteplus.com/en/docs/modelark/seedance-2-5-prompt-guide?redirect=1)
- [BytePlus Seedance 2.5 model tutorial](https://docs.byteplus.com/en/docs/modelark/seedance-2-5)
- [BytePlus video generation task API](https://docs.byteplus.com/en/docs/modelark/create-video-generation-task-api)
- [Official skill distribution](https://arkdocs-en.tos-ap-southeast-1.volces.com/skills/)
