# RAG Web App - Portfolio Edition 🤖

將你的 RAG 專案改造成可部署到 Vercel 的 Web App。支援 **OpenAI** 與 **Google Gemini**，具備 **文件上傳** 與 **對話記憶** 功能。

## 🌟 核心特色
- **BYOK (Bring Your Own Key)**: 用戶輸入自己的 API Key，開發者零成本維護。
- **Session-scoped Memory**: 每個會話獨立擁有向量儲存與對話記憶。
- **Demo Mode**: 內建「香港創新科技藍圖」示範資料，訪客無需 Key 即可體驗。
- **多格式支援**: 支援 PDF, DOCX, TXT, Markdown。
- **Premium UI**: 深色模式、Glassmorphism 風格、打字動畫。

## 🚀 快速部署到 Vercel
1. 將 `rag-web-app` 資料夾上傳到 GitHub。
2. 在 Vercel 連結該 Repository。
3. 保持預設設定，點擊 **Deploy** 即可。

## 🛠️ 本地開發
```bash
cd rag-web-app
npm install
npm run dev
```
開啟 `http://localhost:3000` 即可使用。

## 📂 專案結構
- `/app/api/upload`: 處理文件解析、切片與向量化。
- `/app/api/chat`: 執行 RAG 檢索與 LLM 對話。
- `/app/api/demo`: 示範模式專用的預設 Q&A。
- `/lib/ragEngine.ts`: 核心 RAG 邏輯（自定義內置向量儲存）。
- `/lib/sessionStore.ts`: 管理內存中的 Session 資料。

---
Built with Next.js 14, LangChain.js, and Vanilla CSS.
