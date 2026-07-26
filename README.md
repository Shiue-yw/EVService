# 外泌體純化及粒徑分析服務申請單（網頁版）

依原 REDCap 問卷格式重製的靜態網頁表單，可直接部署在 GitHub Pages。

## 部署到 GitHub Pages 的步驟

1. 到 GitHub 建立一個新的 repository（例如：`ev-service-form`），設為 Public。
2. 把這個資料夾裡的 `index.html` 上傳到該 repository 的根目錄
   （網頁介面：Add file → Upload files，把 `index.html` 拖進去 → Commit）。
3. 進入 repository 的 **Settings → Pages**。
4. 在 "Build and deployment" 底下，Source 選擇 **Deploy from a branch**，
   Branch 選 `main`（或 `master`）、資料夾選 `/ (root)`，按 Save。
5. 等 1–2 分鐘，GitHub 會給一個網址，通常是：
   `https://<你的帳號名稱>.github.io/ev-service-form/`
6. 打開這個網址即可看到表單。

## 目前功能

- 版面、欄位、必填標示、公告文字都仿照原問卷樣式。
- 表單按下「送出」後，會檢查必填欄位，接著開啟使用者的電子郵件軟體，
  自動帶入主旨與內容，寄送到技術員信箱 yinwen@ntuh.gov.tw（因為是純靜態頁面，
  沒有後端伺服器可以直接收資料，用 mailto 是最簡單可行的收件方式）。

## 如果想要收到「表單資料庫」而不是 Email

純 GitHub Pages 無法內建資料庫。若你需要把回覆自動存進試算表或資料庫，
常見做法是串接以下其中一種（都需要你自己申請帳號、我可以協助改程式碼串接）：
- Google 表單 / Google Sheets（透過 Apps Script webhook）
- Formspree / Getform 等免費表單後端服務
- 自架的簡單 API（例如 Cloudflare Worker + 資料庫）

有需要的話告訴我你想用哪一種，我可以幫你把送出邏輯改成寫入該服務。
