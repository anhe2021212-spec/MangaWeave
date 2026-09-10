# Reference Handling

## Purpose

Keep identity information while preventing reference images from silently overriding the requested manga medium.

## Identity-anchor strategy

### 1. Text-only identity anchor
Best for:
- single-page tests
- strong black-and-white requirements
- testing whether paneling and page rhythm work
- situations where colored references are polluting the medium

Use:
- stable appearance traits described in text
- silhouette
- proportions
- hairstyle
- face tendencies
- ears, tails, rings, moles, accessories
- clothing logic
- recurring temperament cues

### 2. Mono-character anchor
Best for:
- multi-page continuity
- preserving face and body consistency
- black-and-white manga production after identity has already been standardized

This means first generating one or two black-and-white character anchor images, then using those in later page generation.

### 3. Direct image reference
Use only when:
- the final output is not black-and-white manga
- or the user explicitly wants to preserve the rendering style of the reference itself

## Rule for black-and-white manga

For black-and-white manga, prefer:

1. text-only identity extraction
2. mono-character anchor
3. direct colored character references

## What reference images are allowed to control

Allowed:
- identity
- silhouette
- hairstyle
- body proportion
- stable facial structure tendencies
- clothing logic
- special traits

Not allowed by default:
- color palette
- painterly rendering
- soft shading
- glossy finish
- cinematic lighting
- gray-wash illustration style
- dense decorative background treatment

## If the user provided visual references

Extract identity facts into text first.

If continuity matters, standardize them into black-and-white anchors.

Do not pass colored reference images directly into final black-and-white page generation unless there is a strong reason.

## Priority order

1. requested manga medium
2. page storytelling function
3. character identity
4. rendering style of reference images
