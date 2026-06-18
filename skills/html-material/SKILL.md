---
name: html-material
description: 資料をHTML形式で出力するとき（1ファイル完結のWebページを作るとき）に使う。CSSとJavaScriptをHTML内に埋め込み、ブラウザでそのまま開ける .html を生成する。
---

資料を「1ファイル完結のHTML」で出力するときは、必ず次に従います。

## 出力ルール
- すべてを1つの `.html` に収める。CSSは `<style>`、JSは `<script>` として**ファイル内にインライン**で書く（外部CSS/JS・CDN・外部リンク参照をしない）。
- 先頭に `<!DOCTYPE html>`、`<html lang="ja">`、`<meta charset="utf-8">`、`<meta name="viewport" content="width=device-width, initial-scale=1">`。
- 日本語が綺麗なフォント：`font-family: system-ui, "Hiragino Kaku Gothic ProN", "Noto Sans JP", "Meiryo", sans-serif;`
- `material-design` でまとめた「■デザイン方針」（配色・トーン・レイアウト・ロゴ）を反映する。指定が無い項目は読みやすさ優先の既定で補う。
- 読みやすい配色・余白・行間。`max-width` で中央寄せ。スマホでも崩れない。見出し階層を明確に。
- 印刷／PDF化しやすいよう `@media print` を入れる。
- JavaScriptは必要な範囲だけ（目次ジャンプ、スライド送り等）。**JSが無くても内容は読めること**。
- ファイル名は内容に合わせた英数字（例：`proposal.html`）。作成後、保存場所を伝える。

## このスキルでも必ず守ること
- まず結論から。読み手は忙しい前提で、長くしすぎない。あいまいな点は先に質問する。
- 根拠のない数字や実績は作らない。カタカナの専門用語は避け、言い換える（ソリューション→解決策／アジェンダ→進め方／弊社→当社）。1文を長くしない。
- 文体は「です・ます」調。本文の見出しは「■」、箇条書きは「・」。価格は税抜き。読み手は取引先の決裁者（部長〜役員クラス）。
