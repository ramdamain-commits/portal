# Projects Portal

個人プロジェクトの一覧ページ。GitHub Pages で静的ホスティングしている。

公開URL: https://ramdamain-commits.github.io/portal/

## 機能

| 機能 | 概要 |
|------|------|
| カテゴリフィルター | 全て / ツール / 学習 / ヘルスケア / AI / 創作 |
| カード登場アニメーション | IntersectionObserver + stagger で順次フェードイン |
| スティッキーヘッダー | スクロール連動で backdrop-blur を適用 |
| SSD最安値ウィジェット | ssd-deal-tracker の価格データを取得して最安値速報を表示 |
| アクセシビリティ | roving tabindex によるキーボードナビゲーション、prefers-reduced-motion 対応 |
| OGP / Twitter Card | og-image.svg + favicon.svg によるリッチプレビュー |
| レスポンシブ対応 | モバイル〜デスクトップに対応 |
| PWA 対応 | GitHub Pages 上でそのまま動作 |

## 技術スタック

- **フロントエンド**: バニラ HTML / CSS / JavaScript（フレームワーク不使用）
- **ホスティング**: GitHub Pages
- **CI/CD**: GitHub Actions（`main` ブランチへの push で自動デプロイ）

## ファイル構成

```
portal/
├── index.html           # メインページ（CSS・JS をインライン記述）
├── favicon.svg          # Favicon
├── og-image.svg         # OGP画像（1200×630）
└── .github/
    └── workflows/
        └── deploy.yml   # GitHub Pages デプロイワークフロー
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
