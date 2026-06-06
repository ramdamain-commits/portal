# Repo Rules

- 親 `C:\Users\ramda\projects\CLAUDE.md` を先に適用する
- ポータルの変更はコミット後に **必ず push する**（GitHub Pages に即反映するため）。確認不要で push してよい
- カード追加・URL 変更は `setting/projects.json` を先に更新し、`Invoke-ProjectCatalog.ps1 -Format portal-cards -Apply` で反映する。index.html の CATALOG マーカー間を直接編集しない（次回 Apply で消える）
- SSD ウィジェットや Life Ops Console など JS 内の URL は CATALOG 外なので直接 index.html を編集する
