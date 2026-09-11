# MangaWeave

Teaching image models to think in manga pages, not illustration grids.

MangaWeave is a Codex skill for turning compact character, relationship, scene, and mood descriptions into readable one-page black-and-white manga. It couples narrative beats, panel hierarchy, page-density contrast, character acting, reference handling, screentone, black/white structure, and dialogue rhythm instead of treating them as separate stages.

## What it focuses on

- Sequential storytelling rather than a collage of standalone illustrations
- True black-and-white print language rather than desaturated digital painting
- Panel size and shape driven by narrative function
- Deliberate contrast between dominant, supporting, and quiet panels
- Background detail that follows spatial need and character attention
- Identity-anchor strategies that keep colored references from overriding manga print language
- Visible character or relationship shifts within a single page
- Layer-specific evaluation and retry guidance

The current refined modes are:

- `slice-of-life-a` — reaction-driven everyday manga
- `shoujo-a` — relationship-driven emotional amplification

## Historical example

The [static-electricity case description](image2-manga-page/examples/static-electricity-laundromat.md) explains how a small laundromat incident, reaction chain, panel hierarchy, and background reduction become one page-sized story. It is historical evidence rather than a fixed template.

## Install for Codex

Clone or copy `image2-manga-page` into your Codex skills directory:

```text
~/.codex/skills/image2-manga-page/
```

Or install it from this repository with the Codex skill installer using:

```text
repository: anhe2021212-spec/MangaWeave
path: image2-manga-page
```

The skill is automatically discoverable as `image2-manga-page`.

## Repository layout

```text
MangaWeave/
|-- README.md
|-- LICENSE
|-- NOTICE
|-- CONTRIBUTING.md
|-- CLA.md
|-- COMMERCIAL-LICENSING.md
`-- image2-manga-page/
    |-- SKILL.md
    |-- CHANGELOG.md
    |-- TESTING-NOTES.md
    |-- examples/
    `-- references/
```

## Usage

Give Codex a character reference or a short natural-language premise and ask for a one-page black-and-white manga. The skill performs the story and page design internally; users do not need to write panel-by-panel image prompts.

## License and commercial licensing

MangaWeave is distributed under the [GNU Affero General Public License v3.0 only](LICENSE) (`AGPL-3.0-only`), except where a file or notice states otherwise.

The AGPL permits commercial use. If you modify MangaWeave and make the modified program available for users to interact with over a network, the AGPL's network-source provisions may require you to offer the corresponding source code to those users.

For organizations that want to use eligible MangaWeave material in a proprietary product or service under separate terms, commercial licensing may also be available. See [COMMERCIAL-LICENSING.md](COMMERCIAL-LICENSING.md).

Contributions are accepted under the policy in [CONTRIBUTING.md](CONTRIBUTING.md) and the [Contributor License Agreement](CLA.md), which preserves contributors' ownership while giving the Project the rights needed to maintain both the AGPL edition and separate commercial licensing where applicable.

The initial repository revision was published under the MIT License. See [NOTICE](NOTICE) for the license transition and historical scope.
