# FairSing AI v3.1 Firebase 正式發布流程

Firebase 專案：`fairsing-ai`

## 已完成的程式整合

- Firebase Web App 設定
- Google 登入
- Cloud Firestore 雲端同步
- 訪客本機模式
- 無網路時本機暫存
- Firebase Hosting 設定
- Firestore 安全規則
- 單頁應用 rewrite

## Firebase Console 必查項目

### 1. Authentication

Firebase Console → Authentication → Sign-in method：

- 啟用 Google
- 設定專案支援電子郵件
- 儲存

Authentication → Settings → Authorized domains：

確認至少包含：

- `localhost`
- `fairsing-ai.web.app`
- `fairsing-ai.firebaseapp.com`

### 2. Cloud Firestore

Firebase Console → Firestore Database：

- 確認資料庫已建立
- 建議選擇離台灣較近且符合需求的區域
- 部署本資料夾的 `firestore.rules`

本版資料路徑：

`teachers/{登入者UID}/app/state`

每位教師只能讀寫自己的資料。

### 3. Firebase Hosting

本發布包已設定：

- Project ID：`fairsing-ai`
- Hosting public：`public`
- 所有網址回到 `index.html`

## 使用 Cloud Shell 部署

1. 將本資料夾上傳到 Cloud Shell。
2. 進入資料夾。
3. 執行：

```bash
firebase login
firebase use fairsing-ai
firebase deploy --only hosting,firestore:rules
```

完成後網站通常位於：

- `https://fairsing-ai.web.app`
- `https://fairsing-ai.firebaseapp.com`

## 正式使用前測試

1. Google 登入成功。
2. 建立測試班級與學生。
3. 重新開啟網站，確認資料仍存在。
4. 另一部裝置使用同一 Google 帳號登入，確認資料同步。
5. 進入 Assessment，完成麥克風設備校正。
6. 測試學生唱一段 10–20 秒旋律。
7. 儲存成績並查看 Reports。
8. 匯出 Excel 與 JSON 備份。

## 注意

Firebase Web 設定中的 apiKey 不是伺服器密碼；真正的資料安全由 Authentication 與 Firestore Rules 控制。請勿把 Firestore 保持在完全公開的測試規則。
