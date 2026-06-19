---
name: pptx-material
description: 資料をパワポ形式で出力するとき（PowerPointで編集できる .pptx を作るとき）に使う。python-pptx でネイティブな .pptx を生成する。
---

資料を「PowerPointで編集できる .pptx」で出力するときは、次に従います。

## 生成方法（python-pptx）
- **まだ「■デザイン方針」が決まっていなければ、生成の前に必ず `material-design` スキルでデザインの希望をヒアリングする**（ユーザーは「おまかせ」でも可）。デザインを聞かずに生成を始めない。
1. `python-pptx` が使えるか確認。なければ案内・実行：`python3 -m pip install python-pptx`。
2. 計画した各スライドの内容をもとに python-pptx を使う Python スクリプトを書き、実行して `.pptx` を生成する。
3. 文字は**画像化せず**、タイトル／本文のプレースホルダ・テキストボックスに入れる（編集可能にするため）。
4. 日本語フォント（例 `Meiryo` / `Yu Gothic`）を指定。タイトル＋本文の階層を保つ。
5. `material-design` でまとめた「■デザイン方針」を反映（配色→図形・タイトルの色、トーン→余白や文字量、ロゴ→指定があれば各スライドに配置）。
6. 生成後、`.pptx` の保存場所を伝える。

## 最小スケルトン（内容に合わせて拡張）
```python
from pptx import Presentation
prs = Presentation()
s = prs.slides.add_slide(prs.slide_layouts[0])      # 表紙
s.shapes.title.text = "タイトル"
s.placeholders[1].text = "サブタイトル"
s = prs.slides.add_slide(prs.slide_layouts[1])      # 本文（箇条書き）
s.shapes.title.text = "見出し"
tf = s.placeholders[1].text_frame
tf.text = "ポイント1"
tf.add_paragraph().text = "ポイント2"
prs.save("output.pptx")
```
※ 上は最小例。日本語フォント（Meiryo / Yu Gothic）は各段落の `run.font.name` に設定して拡張する。

## このスキルでも必ず守ること
- まず結論から。読み手は忙しい前提で、長くしすぎない。あいまいな点は先に質問する。
- 根拠のない数字や実績は作らない。カタカナの専門用語は避け、言い換える（ソリューション→解決策／アジェンダ→進め方／弊社→当社）。1文を長くしない。
- 文体は「です・ます」調。本文の見出しは「■」、箇条書きは「・」。価格は税抜き。読み手は取引先の決裁者（部長〜役員クラス）。
