# バディ — AI のソウル

[English][readme-en]

バディは、落ち着いていて頼れる AI の相棒のペルソナです。[Soul Spec][soulspec] v0.5 の形で書いています。バディは結論から短く答え、分からないことは分からないとはっきり伝えます。

ソウルの本体（`soul/` の中）は英語で書いています。このファイルは、日本語での説明です。

## バディのふるまい

- 決まり文句のあいさつや前置きを省き、先に答える
- 分からないことを推測で埋めない。調べるか、分からないと伝える
- キャラクターは会話の返答だけに使い、文書・コミットメッセージ・PR には使わない
- 利用者が書いた言語で返答する（日本語で話しかければ、日本語で答える）

## フォルダの構成

配布するのは `soul/` フォルダだけです。`soul/` の外は、保守のための資料です。

| パス | 中身 |
| --- | --- |
| `soul/soul.json` | パッケージの情報（名前・版・ライセンス・タグ） |
| `soul/SOUL.md` | 性格・口調・大事にすること・境界 |
| `soul/IDENTITY.md` | 名前・雰囲気・絵文字 |
| `soul/AGENTS.md` | 作業中のふるまい（事実を確かめる・結果をそのまま伝える・取り消しにくい操作の前に確かめる） |
| `soul/STYLE.md` | 話し方 |
| `soul/examples/` | 話し方を合わせるための、良い例と悪い例 |
| `README.md`、`README.ja.md` | 説明（英語と日本語） |

## 使い方

`soul/` の中のファイルを、使っている AI がペルソナのファイルを読む場所へコピーします。`SOUL.md` を読める AI なら、どれでも使えます。

## 公開のしかた

[ClawSouls][clawsouls] の CLI を、リポジトリの直下ではなく `soul/` フォルダに対して実行します。

```sh
npx clawsouls validate ./soul
npx clawsouls soulscan ./soul
npx clawsouls publish ./soul
```

公開するたびに、先に `soul/soul.json` の `version` を上げます。

## ライセンス

[MIT][license]

[readme-en]: README.md
[soulspec]: https://github.com/clawsouls/soulspec
[clawsouls]: https://clawsouls.ai
[license]: LICENSE
