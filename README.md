# 待買書單知識庫與選書推薦系統（Book Wishlist Wiki）

這是一個專為愛書人設計的個人待買書單知識庫，結合純前端靜態展示網頁（GitHub Pages）與本機 AI 選書顧問。

---

## 🌟 系統亮點

1. **嚴格 9 大分類白名單**：
   - 哲學、社會與政治、心理與個人成長、歷史、科學與科普、性別研究、商業與經濟、文學與小說、飲食、生活與藝術美學。
2. **三層跨領域標籤架構**：
   - `primary_category`（主分類，單選）
   - `secondary_categories`（跨領域副分類，複選 0～2 個）
   - `concepts`（微觀核心概念，雙向串聯不同維度書籍）
3. **概念實體化門檻機制**：
   - 概念出現次數達到 $\ge 2$ 本書時，AI 自動在 `wiki/concepts/` 晉升建立實體筆記，打造網狀知識庫。
4. **溫暖實木書櫃與翻開一本書（Open Book Spread）**：
   - 仿照實體書店實木層架與立體書脊陰影。
   - 點擊書籍立即展開「左右對開跨頁」，左頁檢視身分與標籤，右頁深讀核心看點與概念連結。
   - 提供「今天帶哪本回家？（隨機選書）」與跨領域概念過濾。
5. **本機 AI 選書顧問**：
   - 在對話框隨時提出需求（例如「想找入門級但跨哲學與歷史的書」），AI 依據 `agent.md` 自 `to-buy` 清單嚴選推薦。

---

## 📁 檔案結構

```
book-wishlist-wiki/
├── agent.md                    # AI 選書顧問與防幻覺標準作業手冊
├── README.md                   # 系統介紹與使用指南
├── index.html                  # 溫暖書櫃前端靜態網頁（純原生 HTML/CSS/JS）
├── data/
│   └── books.json              # 核心書籍資料庫（供 index.html 讀取）
├── wiki/
│   ├── index.md                # 知識庫總覽目錄
│   ├── books/                  # 所有單本書籍 Markdown 筆記（平鋪存放）
│   └── concepts/               # 累計達 2 本以上實體化的概念 Wiki 頁
└── assets/
    └── covers/                 # 本地存放的自訂書籍封面圖
```

---

## 🚀 如何使用與部署

### 1. 本地預覽
使用任何本地 HTTP 伺服器啟動專案目錄（例如使用 VSCode Live Server 或 Python 內建伺服器）：
```bash
python -m http.server 8000
```
瀏覽器開啟 `http://localhost:8000` 即可享受溫暖書櫃體驗。

### 2. 部署到 GitHub Pages
1. 將本專案推送至您的 GitHub Repository。
2. 進入 Repository 的 **Settings -> Pages**。
3. Source 選擇 **Deploy from a branch**，Branch 選擇 `main` / `root`。
4. 儲存後數十秒內即可獲得專屬的線上待買書櫃網址！
