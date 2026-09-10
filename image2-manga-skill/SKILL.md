---
name: image2-manga-page
description: >
  Turn simple user-provided character, relationship, scene, and mood information into a readable
  one-page black-and-white manga image. The skill couples narrative, paneling, art direction,
  background density, character acting, screentone, black/white structure, and dialogue rhythm.
version: 0.2.0
tags:
  - image2
  - manga
  - black-and-white
  - screentone
  - shoujo
  - slice-of-life
---

# Image2 Manga Page

## Goal

The user should be able to give only a simple request, such as:

- who the characters are
- what their relationship is
- where they are
- what kind of manga they want
- optionally, what happens

The assistant reads this skill, fills in missing story logic conservatively, designs the page, and generates the manga image.

Do **not** ask the user to write a prompt.

Do **not** require the user to provide panel-by-panel direction unless they explicitly want to.

## Core principle

**Narrative, art direction, and paneling are one coupled system.**

Do not treat them as:
1. story,
2. visual style,
3. panel layout.

Instead, decide what the page needs to communicate, then choose:
- story beat
- character action
- shot distance
- panel size and shape
- black/white balance
- screentone density
- background detail
- dialogue rhythm

as one coordinated decision.

## Supported modes

Current refined modes:

- `slice-of-life-a`
- `shoujo-a`

Future modes such as battle, horror, sports, or suspense must not be improvised as if fully specified. They should be added only after dedicated study and testing.

## Required reading

Always read:

- `references/story-from-user-input.md`
- `references/black-white-medium.md`
- `references/panel-grammar.md`

Then read exactly one mode file:

- `references/slice-of-life-a.md`
- `references/shoujo-a.md`

After generation, use:

- `references/evaluation-and-retry.md`

## Workflow

### 1. Inspect what the user actually supplied

Identify:

- character identity and stable visual traits
- relationship state
- scene
- event, mood, or emotional goal
- exact dialogue, if any
- requested manga mode

Do not invent permanent character canon when the user has not supplied it.

### 2. Resolve missing information

Use `references/story-from-user-input.md`.

Prefer:
- small, scene-native events
- character-specific reactions
- relationship-specific consequences
- one clear page-level shift

Avoid:
- unnecessary melodrama
- generic romantic rescue beats
- random conflict unrelated to the setting
- turning one character into a helper NPC

### 3. Decide the page function

Choose one dominant function:

- introduction
- progression
- comedy beat
- relationship shift
- emotional landing
- quiet ending
- reveal

A page can contain several beats, but it should have one dominant purpose.

### 4. Build the page as a sequence

Use beginning → development → turn → landing.

The page must have readable cause and effect.

A panel may exist only to:
- establish
- react
- pause
- redirect attention
- reveal
- land

Not every panel needs to be beautiful or information-dense.

### 5. Choose panel grammar from narrative need

Use `references/panel-grammar.md`.

Panel size follows narrative importance.

Panel shape follows function.

Do not add irregular panels merely to make the page look “manga-like.”

### 6. Lock true black-and-white print language

Use `references/black-white-medium.md`.

This is a hard requirement.

If the result looks sepia, beige, warm gray, painterly, or like a desaturated illustration, treat the medium as failed even if the composition is good.

### 7. Handle reference images correctly

If user reference images are present:

Use them for:
- identity
- silhouette
- hairstyle
- body proportion
- clothing logic
- stable distinguishing traits

Unless the user explicitly asks otherwise, do **not** inherit:
- color palette
- lighting model
- painterly rendering
- soft shading
- illustration finish
- background treatment

For black-and-white manga tasks, requested manga medium outranks the rendering style of character reference images.

Priority:
1. requested manga medium
2. page storytelling function
3. character identity
4. rendering style of reference images

### 8. Generate directly

The assistant should perform the manga design internally and call the image generation tool.

Do not expose an internal prompt scaffold to the user unless they ask for it.

Do not ask the user to rewrite their request into image-model language.

### 9. Evaluate and retry by layer

Use `references/evaluation-and-retry.md`.

Do not rewrite everything blindly.

Identify whether the failure is:
- medium
- page readability
- story
- character acting
- background density
- panel hierarchy
- text

Then correct only the failed layer where possible.

## Hard invariants

1. The output is a **sequential manga page**, not an illustration collage.
2. Black-and-white is a **print system**, not a desaturation filter.
3. Important beats receive more visual space.
4. Background detail follows information need and character attention.
5. Characters act; they do not merely pose.
6. A page should contain a visible change, even if tiny.
7. Silence, empty space, repeated framing, and reaction-only panels are valid tools.
8. Reference images do not override the requested medium.
9. The assistant may fill gaps, but should not invent unnecessary permanent character traits.
10. If exact text rendering is unreliable, prioritize page storytelling over long dialogue.

## Mode routing

### Use `slice-of-life-a` when:
- the event is small and ordinary
- humor or warmth comes from behavior
- the user wants everyday life, domesticity, school life, casual interaction
- the page should feel observed rather than staged

### Use `shoujo-a` when:
- relationship change matters more than external plot
- gaze, hands, distance, hesitation, embarrassment, or attention are central
- the user wants romantic or emotionally delicate manga language
- subjective attention should influence background and panel shape

If both apply, choose the one matching the requested emotional center:
- “what happened and how they reacted” → slice-of-life
- “what changed between them” → shoujo

## Optional examples

Examples are evidence and demonstrations, not mandatory templates.

- `examples/static-electricity-laundromat.md` — successful small-event page showing how narrative, panel hierarchy, background density, object causality, and black-and-white treatment work together.
- `examples/case-study-notes.md` — development notes from successful and failed tests.

## Output behavior

When the user asks to create the manga:
- perform the internal design
- generate the image
- do not dump the analysis unless requested

When the user asks to study, refine, or diagnose:
- discuss the structural reason
- separate facts observed in the image from interpretation
- update this skill only after repeated evidence or a clear failed/successful test
