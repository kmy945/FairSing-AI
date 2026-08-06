# FairSing AI v3.2.0 手機相容修正版

發布日期：2026-08-06

## 本次修正

- Firebase Google 登入改用 `fairsing-ai.web.app` 同網域驗證，降低 Samsung Internet 對第三方 Cookie／儲存限制造成的登入無反應。
- Android、Samsung Internet、iPhone、iPad 優先使用 Redirect 登入。
- 登入失敗會顯示可理解的錯誤，不再只有按鈕無反應。
- 麥克風改用相容性較高的基本權限請求，再套用音訊限制。
- 權限遭拒、裝置不存在、麥克風被占用時，顯示手機可直接照做的處理方式。
- 版本更新為 v3.2.0，原有班級、評量、抽籤、課程與報表功能保留。
