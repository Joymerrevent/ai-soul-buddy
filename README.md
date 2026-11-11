# Buddy — an AI soul

<img src="soul/avatar/avatar.svg" alt="Buddy" width="128" height="128">

[日本語][readme-ja]

Buddy is a calm, dependable AI partner persona written in [Soul Spec][soulspec] v0.5. Buddy leads with the conclusion, keeps answers short, and says so plainly when it does not know something.

## What Buddy does

- Skips stock greetings and filler, and answers first.
- Never fills a gap with a guess. Buddy looks things up or says that it does not know.
- Uses the persona only in conversational replies, never in documents, commit messages, or pull requests.
- Replies in the language the user writes in.

## Repository layout

Only the `soul/` folder is the distributed package. Everything outside `soul/` is documentation for maintainers.

| Path | Contents |
| --- | --- |
| `soul/soul.json` | Package metadata (name, version, license, tags) |
| `soul/SOUL.md` | Personality, tone, principles, and boundaries |
| `soul/IDENTITY.md` | Name, vibe, and emoji |
| `soul/AGENTS.md` | How Buddy works in a session: checking facts, reporting results, asking before risky actions |
| `soul/avatar/avatar.svg` | Avatar image (32×32 pixel art) |
| `soul/STYLE.md` | How Buddy writes |
| `soul/examples/` | Good and bad outputs for calibrating the voice |
| `README.md`, `README.ja.md` | This description in English and Japanese |

## Usage

Copy the files in `soul/` into the place your agent reads persona files from. Any agent that reads `SOUL.md` can use Buddy.

## Making changes

This repository uses GitHub Flow.

1. Create a branch from `main`.
2. Open a pull request. The `ci` check runs the ClawSouls validator and SoulScan on `soul/`.
3. Merge the pull request after `ci` passes. `main` accepts changes only through pull requests.

## Publishing

Publishing runs in GitHub Actions. Only the `soul/` folder is uploaded to [ClawSouls][clawsouls].

1. In a pull request, raise `version` in `soul/soul.json` and merge it.
2. Publish a GitHub release whose tag is `v` followed by that version, for example `v0.2.0`.
3. The `publish` workflow checks that the tag matches `soul.json`, runs the validator and SoulScan, and publishes the soul.

The workflow reads the ClawSouls API token from the `CLAWSOULS_TOKEN` secret of the `clawsouls` environment. Issue the token at <https://clawsouls.ai/dashboard>.

## License

[MIT][license]

[readme-ja]: README.ja.md
[soulspec]: https://github.com/clawsouls/soulspec
[clawsouls]: https://clawsouls.ai
[license]: LICENSE
