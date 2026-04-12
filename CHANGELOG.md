# Changelog

## 2026-04-13

### Changed
- Life Ops Console を3ゾーン構造に再設計（今日やること / 今週のタスク / 判断の根拠）
- UI全面日本語化（サマリーカード・バッジ・見出し・ラベル）
- 「判断の根拠」ゾーンをデフォルト折りたたみに変更
- 鮮度インジケーター追加（最終更新N日前、7日超で警告色）
- 0件表示を「今日は期日アクションなし」に明示
- README の Life Ops Console セクションを再設計後の内容に更新

## 2026-04-10

### Changed
- README のカテゴリ一覧を現状に合わせて更新し、`ゲーム` カテゴリとカタログ更新手順を追記
- `CATALOG-START` コメント表記を `Invoke-ProjectCatalog.ps1` ベースに統一
- ローカル専用の `.claude/` を `.gitignore` で追跡除外

## 2026-03-29

### Changed
- カードリストを `setting/projects.json` ベースの catalog 管理に移行（CATALOG-START/END マーカー追加）
- 健康管理「律」カードから token 付き GAS URL を除去（P0-1 対応。リンク先は仮置き `#`）
- FP3級過去問トレーニング → FP3級ドリル に名称変更（README 修正に合わせて統一）
- README から PWA 対応の記載を削除（manifest.json / sw.js が存在しないため）

## 2026-03-28

### Added
- SSD最安値ウィジェット追加（GAS API 連携、買い時フィルタ、graceful degradation、スケルトンローディング付き）
- FP3級過去問トレーニングのカードをポータルに追加
- カテゴリフィルター追加（全て / ツール / 学習 / ヘルスケア / AI / 創作）
- カード登場アニメーション追加（IntersectionObserver + stagger）
- スティッキーヘッダー追加（スクロール連動 backdrop-blur）
- OGP画像（og-image.svg）・Favicon（favicon.svg）追加
- Twitter Card メタタグ追加
- GitHub Pages デプロイ workflow 追加
- アクセシビリティ強化（roving tabindex、prefers-reduced-motion 対応）

### Fixed
- SSD ウィジェットのレビュー指摘対応
- 健康管理カードの認証注記を改善（共有リンクで体重推移グラフを閲覧可能な旨を明記）
- ヘルスケアリンクをサマリページ（体重推移）に変更
- カードグリッドのリストマーカー（`•`）をリセット CSS で非表示化
- GAS Web App URL を現在のデプロイメントに更新
