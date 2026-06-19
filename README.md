# proposal-maker

営業の提案資料づくりを、ヒアリングから構成・清書までまとめて手伝ってくれる Claude Code プラグインです。

- **使う人**：営業担当。資料づくりに毎回時間がかかって困っている人。
- **作る資料**：提案書、サービス紹介スライド、見積りの添え状。
- **読み手**：取引先の決裁者（部長〜役員クラス）。
- **出力形式**：パワポ（.pptx）と HTML（.html）の**両方**に対応。

## コマンド
- `/proposal-maker:hearing [お客様の会社名]` — 提案資料を作る前に、お客様・課題・予算・締切などを1問ずつ聞き取り、ヒアリングメモ（.md ファイル）にまとめて保存します。
- `/proposal-maker:draft [資料のタイトル]` — ヒアリングメモをもとに、「表紙→課題→提案→料金→次のステップ」の構成で提案資料の下書きを作ります。

## スキル（お願いしなくても自動で効く型・コツ）
- `hearing-memo` — 資料を作る前に、テーマ・お客様・課題・予算・締切などをヒアリングし、その結果を Markdown のヒアリングメモ（.md）として保存します。
- `slide-structure` — 構成・骨子を「1スライド1メッセージ」「結論→根拠3つ→次のアクション」の型で組み立てます。
- `material-design` — 資料を作る前に、配色・雰囲気・レイアウト・ロゴなど見た目の希望をヒアリングします。
- `html-material` — 1ファイル完結の `.html` を生成します。
- `pptx-material` — PowerPoint で編集できる `.pptx` を生成します。

## インストール（GitHub から）

1. このフォルダ（`proposal-maker/`）を GitHub リポジトリとして公開します。
   ```
   git init && git add -A && git commit -m "init"
   git branch -M main && git remote add origin <あなたのリポジトリURL>
   git push -u origin main
   ```
2. Claude Code で次を実行します（`<GitHubユーザー名>/<リポジトリ名>` は自分のものに置きかえ）：
   ```
   /plugin marketplace add <GitHubユーザー名>/<リポジトリ名>
   /plugin install proposal-maker@proposal-maker-marketplace
   ```

## アップデート（更新）方法

### 作った人が中身を直したとき（配布元）
プラグインのフォルダ（`proposal-maker/`）を直したら、GitHub に反映します：
```
git add -A && git commit -m "update"
git push
```

### 使う人が最新版を取り込むとき
Claude Code で `/plugin` を開き、メニューから対象プラグインを更新できます。コマンドで行う場合：
```
/plugin marketplace update proposal-maker-marketplace
/plugin update proposal-maker
```

## できた資料の開き方
- **HTML**：できた `.html` をダブルクリックするとブラウザで開きます（Mac は Finder、Windows はエクスプローラから）。開けないときは右クリック →「このアプリで開く」→ ブラウザを選びます。
- **パワポ**：`.pptx` を PowerPoint / Keynote / Google スライドで開きます。拡張子が見えないときは、表示設定で拡張子を表示してください。

## ご注意（免責）
この資料は下書きです。金額・実績・日付・固有名詞・引用などは、対外提出の前に必ず人が事実確認してください。最終的な内容の責任は利用者にあります。

## 配布するときの注意
プラグインのインストールは、中身（commands / skills の処理や Python の実行）を確認したうえで、作った本人や信頼できる人のものだけにしてください。
