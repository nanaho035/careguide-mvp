# 長照 2.0 小幫手（MVP）

前端：Vite + React + TypeScript（本地埠 `3000`）  
後端：Express + TypeScript（本地埠 `8787`）

**下載包 / Release：**  
- 👉 https://github.com/nanaho035/careguide-mvp/releases/tag/v0.1.0  
  內含 `careguide-mvp.zip`（前端與後端原始碼，含啟動教學）。

---

## 功能摘要
- **資格快篩**：依輸入回傳「可能符合/暫不符合」，並提供下一步建議  
- **自付額試算**：依等級與服務頻率估算每月自付額（區間）  
- **縣市流程**：各縣市申請步驟與注意事項  
- **測試 API**：顯示規則版本與時間（`/api/status`）

## 本機啟動方式

> 需要 Node.js 18+（建議 20+）

### 1) 啟動後端
```bash
cd server
npm install
npm run dev              # → http://localhost:8787
# 正式模式：
# npm run build && npm run start
### 2) 啟動前端
# 回到專案根目錄
cd ..
npm install
npm run dev              # → http://localhost:3000
API 一覽

GET /api/status — 服務狀態與規則版本

POST /api/assess — 資格快篩

POST /api/copay — 自付額試算

專案結構
careguide/
├─ server/              # Express + TypeScript
│  ├─ src/
│  │  ├─ routes/api.ts
│  │  └─ index.ts
│  └─ package.json
├─ src/                 # React + TS (Vite)
│  ├─ pages/            # Assess / Copay / Locale 等頁面
│  ├─ api.ts            # 前端呼叫後端的 API 客戶端
│  └─ App.tsx
├─ .env                 # VITE_API_BASE=...
├─ README.md
└─ screenshots/         # 截圖（可選）
免責

本專案為學習/作業用 MVP，資料與估算僅供參考，實際資格、自付額與服務內容以官方公告與照管中心評估為準。
