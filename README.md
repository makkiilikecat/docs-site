# makkii.jp Docs

[makkii.jp](https://www.makkii.jp/) が提供するツール群の公式ドキュメントサイトです。
公開先: **https://docs.makkii.jp**

[Mintlify](https://mintlify.com) で構築しています。ページは YAML frontmatter 付きの MDX ファイルです。

## 収録しているもの

| プロダクト | パス | 概要 |
| --- | --- | --- |
| Storm Editor (Storm Studio / Storm Draft) | `/storm-editor/` | Stormworks 向け非公式ビークルエディター |
| Storm Code | `/storm-code/` | Stormworks 向け Lua 開発環境 |
| StormMin | `/stormmin/` | Stormworks Lua の難読化・最小化ツール |
| Physics Frame Codegen | `/physics-codegen/` | 物理フレーム生成 |
| Number Codec Compiler | `/codec-compiler/` | 数値コーデックコンパイラ |
| Stormworks Wiki | `/stormworks/` | Stormworks 本体の挙動・仕様の解説 |

## フィードバック・貢献

**誤り・分かりにくい説明・不足している情報を見つけたら、遠慮なく教えてください。**

- **Issue**: 小さな誤字から「この項目の説明が足りない」まで歓迎します。
  該当ページの URL と、どこがどう分かりにくかったかを書いていただけると助かります。
- **Pull Request**: 直接直していただけるのが一番早いです。下の手順でローカルプレビューできます。
  - 1 PR = 1 トピックにしていただけると読みやすいです。
  - 文章は日本語・です/ます調です。技術用語は原語のまま使います。
  - 新しいページを追加したら `docs.json` の該当プロダクトの `groups` / `pages` にも追加してください
    (追加しないとサイドバーに出ません)。
- **ツール本体の不具合・要望**は、ドキュメントではなく各ツールのフィードバック窓口へお願いします。

## ローカルプレビュー

[Mintlify CLI](https://www.npmjs.com/package/mint) をインストールします。

```sh
npm i -g mint
```

`docs.json` のあるリポジトリルートで実行します。

```sh
mint dev
```

`http://localhost:3000` で確認できます。

## リポジトリ構成

- `<slug>/` — 各プロダクトのページ。URL は `/<slug>/…` になります。
- `docs.json` — サイト全体の設定とナビゲーション (`navigation.products`)。
- `AGENTS.md` — 執筆規約 (AI エージェント向けですが、人が読んでも執筆の指針になります)。
