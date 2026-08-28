> Mintlify の製品知識(コンポーネント、設定、ライティング規約)については、
> `npx skills add https://mintlify.com/docs` で Mintlify のスキルをインストールしてください。

# Documentation project instructions

## About this project

- makkii.jp が提供する Stormworks 向けツール群の、公開ユーザー向けドキュメントサイトです。
- 対象読者はツールを実際に使うユーザーです。実装の詳細を解説する社内ドキュメントではありません。
- [Mintlify](https://mintlify.com) 上に構築されています。ページは YAML frontmatter 付きの MDX ファイルです。
- サイト全体の設定は `docs.json` にあります。
- コンテンツ・設定の編集には Mintlify MCP サーバー (`https://mcp.mintlify.com`) を使用できます。
- Mintlify の使い方に関する情報の取得には、Mintlify docs MCP サーバー (`https://www.mintlify.com/docs/mcp`) を使用できます。

## 構造

- 各プロダクトのページは `<slug>/` (リポジトリ直下) に置きます。ドキュメントの URL パスは
  `/<slug>/...` です。対応する実際のアプリは
  `https://www.makkii.jp/tools/stormworks/<slug>/` にあります (アプリ側の URL 構造とは異なります)。
  旧 URL (`/tools/stormworks/<slug>/...`) は `docs.json` の `redirects` で新 URL に転送されます。
- ナビゲーションは `docs.json` の `navigation.products` で管理します。各プロダクトは
  それぞれ独立した1つのサイトとして扱います (プロダクトスイッチャー)。
  - Storm Editor のみ `tabs` (Storm Studio / Storm Draft) を持ちます。
  - 他のプロダクトは `groups` を直接持ちます。
- 新しいページを追加したら、必ず `docs.json` の該当プロダクトの `groups`/`pages` にも
  追加してください。追加しないとサイドバーに表示されません。

## Terminology

| 用語 | 使用方針 |
|---|---|
| マイクロコントローラー (MC) | 略さず「マイクロコントローラー」、必要に応じて「MC」を併記 |
| ビークル | Stormworks の vehicle。「乗り物」等に言い換えない |
| Lua スクリプト | ビークル/MC 上で動く Lua コード |
| Physics Frame Codegen | プロダクト名。正式名称のまま表記 |
| Number Codec Compiler | プロダクト名。正式名称のまま表記 |
| StormMin | プロダクト名。正式名称のまま表記 |
| Storm Editor / Storm Studio / Storm Draft | プロダクト名。Storm Editor は総称、Storm Studio (フル版)・Storm Draft (軽量版) はエディション名 |
| Storm Code | プロダクト名。正式名称のまま表記 |

## Style preferences

- 全ての文章は日本語で書きます。技術用語・固有名詞・識別子は原語のまま表記します。
- です/ます調で統一します。
- 第二人称 (「あなた」を明示しない自然な日本語の敬体) で、能動的かつ簡潔に書きます。
- 見出しは体言止めまたは簡潔な言い切りにします。
- マーケティング的な言葉遣い ("強力な"、"シームレスな" など) や、
  "念のため"、"簡単に" のような冗長な修飾は使いません。
- ファイル名・コマンド・パス・コード参照はコードフォーマットで表記します。
- コードブロックには必ず言語タグを付けます。

## Content boundaries

- ユーザーが使う上で必要な範囲でのみ、内部の挙動を説明します。実装の詳細
  (アーキテクチャ、内部データ構造、社内ワークフローなど) は書きません。
- 将来の計画やロードマップ、未確定の推測は書きません。
- API キーや認証情報などの秘匿情報は書きません。
- 各プロダクトの概要ページには、そのプロダクトの機能に基づく内容だけを書き、
  内容のない見出し (例: 書くことがない "Installation" セクション) は作りません。
