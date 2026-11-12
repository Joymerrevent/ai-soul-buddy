# バディ — AI のソウル

<img src="soul/avatar/avatar.svg" alt="バディ" width="128" height="128">

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
| `soul/avatar/avatar.svg` | アバター画像（32×32 のドット絵） |
| `soul/STYLE.md` | 話し方 |
| `soul/examples/` | 話し方を合わせるための、良い例と悪い例 |
| `README.md`、`README.ja.md` | 説明（英語と日本語） |

## 使い方

`soul/` の中のファイルを、使っている AI がペルソナのファイルを読む場所へコピーします。`SOUL.md` を読める AI なら、どれでも使えます。

## 変更のしかた

このリポジトリは GitHub Flow で運用します。

1. `main` からブランチを作る
2. PR を作る。`ci` のチェックが、`soul/` に ClawSouls の検査と SoulScan をかける
3. `ci` が通ったら PR をマージする。`main` へは PR を通してしか変更を入れられない

## 公開のしかた

公開は GitHub Actions で行います。[ClawSouls][clawsouls] に送られるのは `soul/` フォルダだけです。

1. PR で `soul/soul.json` の `version` を上げて、マージする
2. GitHub の Release を、`v` に続けてその版を書いたタグ（例：`v0.2.0`）で公開する
3. `publish` のワークフローが、タグと `soul.json` の版が一致することを確かめ、検査と SoulScan を通してから公開する

ワークフローは、ClawSouls の API トークンを組織のシークレット `CLAWSOULS_TOKEN` から読みます。組織のシークレットの許可に、このリポジトリを入れておきます。environment `clawsouls` にはトークンを置きません。environment のシークレットは組織のシークレットより優先されるため、古い値が残っていると公開が失敗します。トークンは <https://clawsouls.ai/dashboard> で発行します。

## ライセンス

[MIT][license]

[readme-en]: README.md
[soulspec]: https://github.com/clawsouls/soulspec
[clawsouls]: https://clawsouls.ai
[license]: LICENSE
