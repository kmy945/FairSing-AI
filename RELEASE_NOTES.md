# FairSing AI v3.3 登入修正版

- 移除行動裝置強制 `signInWithRedirect()`，避免 Google 400 `redirect_uri_mismatch`。
- 所有支援瀏覽器改用使用者點擊後的 Firebase `signInWithPopup()`。
- 新增彈出視窗被封鎖、使用者關閉視窗、網域未授權與網路失敗的繁體中文提示。
- 保留既有 Firebase 專案設定與其他功能。
