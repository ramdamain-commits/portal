# Projects Portal

個人プロジェクトの一覧ページ。GitHub Pages で静的ホスティングしている。

公開URL: https://ramdamain-commits.github.io/portal/

## 機能

| 機能 | 概要 |
|------|------|
| カテゴリフィルター | 全て / ツール / 学習 / ヘルスケア / AI / 創作 / ゲーム |
| カード登場アニメーション | IntersectionObserver + stagger で順次フェードイン |
| スティッキーヘッダー | スクロール連動で backdrop-blur を適用 |
| SSD最安値ウィジェット | ssd-deal-tracker の価格データを取得して最安値速報を表示 |
| アクセシビリティ | roving tabindex によるキーボードナビゲーション、prefers-reduced-motion 対応 |
| OGP / Twitter Card | og-image.svg + favicon.svg によるリッチプレビュー |
| レスポンシブ対応 | モバイル〜デスクトップに対応 |

## 技術スタック

- **フロントエンド**: バニラ HTML / CSS / JavaScript（フレームワーク不使用）
- **ホスティング**: GitHub Pages
- **データ連携**: SSD価格トラッカーの GAS API を参照

## Life Ops Console

`life-ops.html` は個人プロジェクト群の **総合ダッシュボード（司令塔）** です。

開いたときに3つのことが分かる:

1. **今日やること** — 人間アクションの期日・鮮度確認
2. **今週のタスク** — 全PJ横断のタスクと更新履歴
3. **判断の根拠** — 意思決定履歴・前提条件・PJ一覧

### 3ゾーン構造

| ゾーン | 確認頻度 | 内容 |
|--------|---------|------|
| 今日やること | 毎日 | 期日30日以内の人間アクション、鮮度インジケーター |
| 今週のタスク | 週次 | TASKS.md ベースのタスク一覧、更新履歴 |
| 判断の根拠 | 月次 | 前提条件・意思決定・プロジェクト一覧（デフォルト折りたたみ） |

### データソース

setting repo の JSON データ（projects / assumptions / decisions / reviews / changelog）+ TASKS.md を集約。

- **自動読込**: 同ディレクトリの `life-ops-export.json` を `fetch()` で取得して即表示
- **フォールバック**: JSON がない場合は localStorage → 手動ファイルアップロードの順で読込

### データ更新

```powershell
# setting repo で生成 + portal にコピー
& "C:\Users\ramda\projects\setting\Run-LifeOpsConsole.cmd"

# GitHub Pages まで反映
& "C:\Users\ramda\projects\setting\Run-LifeOpsConsole.cmd" -Deploy
```

仕様書: `setting/docs/life-ops-console-spec.md`

## ファイル構成

```
portal/
├── index.html              # メインページ（CSS・JS をインライン記述）
├── life-ops.html           # Life Ops Console ビューア
├── life-ops-export.json    # Life Ops データ（自動生成。GitHub Pages の fetch 用にコミット対象）
├── favicon.svg             # Favicon
└── og-image.svg            # OGP画像（1200×630）
```

## ローカル開発

静的ファイルのみで動作するため、任意の HTTP サーバーで確認できる。

```bash
# Python が使える場合
python -m http.server 8080 --directory .

# Node.js が使える場合
npx serve .
```

ブラウザで `http://localhost:8080` を開く。

## カタログ更新

`index.html` の `CATALOG-START` / `CATALOG-END` 間は手編集しない。正本は `C:\Users\ramda\projects\setting\projects.json` とし、次で反映する。

```powershell
& "C:\Users\ramda\projects\setting\Run-ProjectCatalog.cmd" -Format portal-cards -Apply
```
