# Buddy — an AI soul

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
| `soul/STYLE.md` | How Buddy writes |
| `soul/examples/` | Good and bad outputs for calibrating the voice |
| `README.md`, `README.ja.md` | This description in English and Japanese |

## Usage

Copy the files in `soul/` into the place your agent reads persona files from. Any agent that reads `SOUL.md` can use Buddy.

## Publishing

Run the [ClawSouls][clawsouls] CLI against the `soul/` folder, not the repository root.

```sh
npx clawsouls validate ./soul
npx clawsouls soulscan ./soul
npx clawsouls publish ./soul
```

Raise `version` in `soul/soul.json` before each publish.

## License

[MIT][license]

[readme-ja]: README.ja.md
[soulspec]: https://github.com/clawsouls/soulspec
[clawsouls]: https://clawsouls.ai
[license]: LICENSE
