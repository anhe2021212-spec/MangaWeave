# MangaWeave

Teaching image models to think in manga pages, not illustration grids.

MangaWeave is a Codex skill for turning compact character, relationship, scene, and mood descriptions into readable one-page black-and-white manga. It couples narrative beats, panel hierarchy, character acting, background density, screentone, black/white structure, and dialogue rhythm instead of treating them as separate stages.

## What it focuses on

- Sequential storytelling rather than a collage of standalone illustrations
- True black-and-white print language rather than desaturated digital painting
- Panel size and shape driven by narrative function
- Background detail that follows spatial need and character attention
- Visible character or relationship shifts within a single page
- Layer-specific evaluation and retry guidance

The current refined modes are:

- `slice-of-life-a` — reaction-driven everyday manga
- `shoujo-a` — relationship-driven emotional amplification

## Example

![Static Electricity at the Laundromat](image2-manga-skill/examples/static-electricity-laundromat.png)

The accompanying [case description](image2-manga-skill/examples/static-electricity-laundromat.md) explains how a missing sock, static electricity, panel hierarchy, and background reduction become one page-sized story.

## Install for Codex

Clone or copy `image2-manga-skill` into your Codex skills directory:

```text
~/.codex/skills/image2-manga-skill/
```

Or install it from this repository with the Codex skill installer using:

```text
repository: anhe2021212-spec/MangaWeave
path: image2-manga-skill
```

The skill is automatically discoverable as `image2-manga-page`.

## Repository layout

```text
MangaWeave/
|-- README.md
|-- LICENSE
`-- image2-manga-skill/
    |-- SKILL.md
    |-- examples/
    `-- references/
```

## Usage

Give Codex a character reference or a short natural-language premise and ask for a one-page black-and-white manga. The skill performs the story and page design internally; users do not need to write panel-by-panel image prompts.

## License

MIT
