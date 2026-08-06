# FairSing AI v3.1 Firebase 正式發布版

此版本以 Firebase 專案 `fairsing-ai` 為正式發布目標。

## 主要檔案

- `public/index.html`：正式網站
- `firebase.json`：Hosting 與 Firestore 設定
- `.firebaserc`：Firebase 專案 ID
- `firestore.rules`：教師個人資料安全規則
- `FIREBASE_DEPLOY.md`：部署與正式測試步驟

## 資料同步

登入教師的資料儲存在：

`teachers/{uid}/app/state`

訪客資料只存於目前裝置，不會上傳 Firestore。
