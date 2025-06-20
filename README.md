# 四格漫畫生成器 (4-Panel Comic Generator)

![Version](https://img.shields.io/badge/version-v1.0.2-blue.svg)
![Status](https://img.shields.io/badge/status-stable-green.svg)
![Python](https://img.shields.io/badge/python-3.8+-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)

一個使用 Google Gemini API 自動生成四格漫畫的 Python 工具。支援命令列和網頁界面，根據關鍵詞搜尋新聞，生成有趣的漫畫腳本，並將腳本轉換為實際的漫畫圖像。

**🎯 當前版本**: v1.0.2 (穩定版) | **🔄 最後更新**: 2025-06-21

## 🌟 功能特色

- 🔍 **新聞搜尋**: 根據關鍵詞自動搜尋相關新聞
- ✍️ **智能腳本生成**: 使用 Gemini 2.5 Flash Preview 生成有趣的四格漫畫腳本
- 🎨 **圖像生成**: 將腳本轉換為實際的漫畫圖像
- 🖼️ **自動拼貼**: 將四格圖像合併成完整的漫畫
- 🌐 **網頁界面**: 美觀的網頁介面，支援即時生成和瀏覽
- � **響應式設計**: 支援桌面和行動裝置
- �📁 **組織化輸出**: 為每個關鍵詞創建專屬資料夾
- 💬 **智能對話處理**: 區分場景描述和對話內容
- 🔄 **即時進度**: 網頁界面顯示生成進度
- 📊 **漫畫清單**: 自動管理和顯示所有生成的漫畫

## 🚀 快速開始

### 1. 安裝依賴
```bash
pip install -r requirements.txt
```

### 2. 設定 API 金鑰
創建 `.env` 檔案並設定你的 Google API 金鑰：
```env
GOOGLE_API_KEY=你的_Google_API_金鑰
```

### 3. 啟動服務

**完整網頁服務（推薦）:**
```bash
start_full_service.bat
```
- 🌐 網頁界面: http://localhost:8000
- 🔧 API 服務: http://localhost:5000

**只瀏覽現有漫畫:**
```bash
start_local_server.bat
```
- 🌐 網頁界面: http://localhost:8000
**命令列模式:**
```bash
python comic_generator.py
```

## 📁 專案結構

```
comics/
├── 📄 comic_generator.py        # 主要的漫畫生成程式
├── 🌐 comic_api_server.py       # Flask API 服務器
├── 📋 generate_manifest.py      # 漫畫清單生成器
├── 🔧 requirements.txt          # Python 依賴套件
├── 🚀 start_full_service.bat    # 啟動完整服務
├── 🚀 start_local_server.bat    # 啟動本地伺服器
├── 🧹 auto_cleanup.bat          # 自動清理工具
├── 🧹 interactive_cleanup.bat   # 互動式清理工具
├── 🧹 check_comics.bat          # 檢查漫畫完整性
├── 🧹 full_cleanup.bat          # 完整清理流程
├── 🧹 cleanup_comics.py         # Python 清理腳本
├── 📁 docs/                     # 網頁檔案和漫畫輸出
│   ├── 🌐 index.html           # 主要網頁界面
│   ├── 📜 comic-api.js          # 前端 JavaScript
│   ├── 📊 comics_manifest.json  # 漫畫清單
│   └── 📁 comic_output_*/       # 生成的漫畫資料夾
└── 📚 docs/README.md            # 詳細文檔
```

## 📱 網頁界面功能

### 🎨 主要功能
- **關鍵詞輸入**: 輸入任何新聞相關關鍵詞
- **即時生成**: 點擊生成按鈕開始創作
- **進度顯示**: 實時顯示生成進度和狀態
- **漫畫瀏覽**: 瀏覽所有已生成的漫畫作品
- **腳本查看**: 查看每個漫畫的完整腳本

### 🖼️ 界面特色
- 現代化卡片設計
- 響應式布局（支援手機、平板、桌面）
- 優雅的動畫效果
- 直觀的操作流程

## 📄 輸出格式

每次執行都會創建一個專屬資料夾，包含：

```
comic_output_{關鍵詞}_{時間戳}/
├── comic_script.txt          # 完整腳本（包含新聞來源）
├── comic_panel_1.png         # 第一格圖像
├── comic_panel_2.png         # 第二格圖像
├── comic_panel_3.png         # 第三格圖像
├── comic_panel_4.png         # 第四格圖像
├── four_panel_comic.png      # 完整四格漫畫
└── debug_panel_*.raw         # 調試文件（如需要）
```

## 腳本格式

生成的腳本會清楚分離場景和對話：

```
第一格：
場景：[視覺場景描述]
對話：[實際對話內容] 或 "無"
```

## 圖像生成邏輯

- **場景描述**：轉換為視覺圖像呈現
- **對話內容**：以對話氣泡形式顯示在圖像中
- **風格**：漫畫風格，適合四格漫畫呈現

## 🛠️ 維護工具

### 🧹 清理工具
本專案提供多種清理工具來維護漫畫資料夾的整潔：

```bash
# 自動清理無效漫畫（靜默模式）
auto_cleanup.bat

# 互動式清理（會詢問確認）
interactive_cleanup.bat

# 檢查漫畫完整性
check_comics.bat

# 完整清理流程（檢查 + 清理 + 更新清單）
full_cleanup.bat
```

### 📊 清單管理
```bash
# 重新生成漫畫清單
python generate_manifest.py

# 更新本地漫畫清單
update_local_comics.bat
```

### 🔧 服務管理
```bash
# 啟動完整服務（網頁 + API）
start_full_service.bat

# 只啟動網頁服務（瀏覽現有漫畫）
start_local_server.bat
```

## 🛠️ 技術架構

### 後端技術
- **Python 3.8+**: 主要開發語言
- **Google Gemini API**: AI 腳本生成和圖像生成
- **Flask**: Web API 框架
- **PIL/Pillow**: 圖像處理
- **Requests**: HTTP 請求處理

### 前端技術
- **HTML5/CSS3**: 現代網頁標準
- **JavaScript ES6+**: 前端邏輯
- **Responsive Design**: 響應式設計
- **CSS Grid/Flexbox**: 布局系統

### API 架構
- **RESTful API**: 標準 REST 接口
- **CORS 支援**: 跨域請求支援
- **JSON 格式**: 標準數據交換格式

## 🎬 範例展示

### 生成步驟
1. 在網頁中輸入關鍵詞：`老翁開車`
2. 點擊「生成漫畫」按鈕
3. 系統會顯示進度：
   - 🔍 搜尋相關新聞...
   - ✍️ 生成漫畫腳本...
   - 🎨 生成圖像中...
   - 🖼️ 合併四格漫畫...
4. 完成後自動顯示結果

### 腳本範例
```
四格漫畫腳本：老翁開車

第一格：
場景：一位年長的老翁坐在駕駛座上，雙手緊握方向盤
對話：「今天天氣不錯，出門走走」

第二格：
場景：老翁開車經過紅綠燈路口，有點疑惑的表情
對話：「咦？這是紅燈還是綠燈？」

第三格：
場景：交通警察在路邊揮手示意，背景有其他車輛
對話：「先生，請靠邊停車」

第四格：
場景：老翁下車和警察對話，旁邊有家人陪同
對話：「可能該考慮不開車了...」
```

## 🔧 API 說明

### 主要端點
- `POST /api/generate-comic` - 生成新漫畫
- `GET /api/progress/<task_id>` - 查詢生成進度
- `GET /api/comics` - 獲取漫畫清單

### 使用範例
```javascript
// 生成漫畫
fetch('/api/generate-comic', {
    method: 'POST',
    headers: {'Content-Type': 'application/json'},
    body: JSON.stringify({keyword: '關鍵詞'})
})

// 查詢進度
fetch(`/api/progress/${taskId}`)
    .then(response => response.json())
    .then(data => console.log(data.status))
```

## 🚨 常見問題

### Q: 為什麼圖片生成失敗？
A: 可能是 Google API 配額用完，請等待配額重置或檢查 API 金鑰。

### Q: 網頁無法訪問怎麼辦？
A: 確保執行了 `start_full_service.bat` 並等待服務完全啟動。

### Q: 漫畫清單沒有更新？
A: 執行 `python generate_manifest.py` 或 `update_local_comics.bat` 重新生成清單。

### Q: 有很多無效的漫畫資料夾怎麼辦？
A: 使用清理工具：
- `auto_cleanup.bat` - 自動清理
- `interactive_cleanup.bat` - 互動式清理
- `full_cleanup.bat` - 完整清理流程

### Q: 如何檢查漫畫的完整性？
A: 執行 `check_comics.bat` 查看所有漫畫的狀態。

## 📊 系統需求

- **作業系統**: Windows 10+ / macOS 10.14+ / Linux
- **Python**: 3.8 或更高版本
- **記憶體**: 建議 4GB 以上
- **網路**: 穩定的網際網路連線
- **瀏覽器**: Chrome、Firefox、Safari、Edge 現代版本

## 🔄 更新日誌

### v1.0.2 (2025-06-21) ⭐ 當前穩定版
- 🧹 **重大重構**: 完整的程式碼重構和優化
- �️ **新增清理工具**: 
  - `auto_cleanup.bat` - 自動清理無效漫畫
  - `interactive_cleanup.bat` - 互動式清理
  - `check_comics.bat` - 檢查漫畫完整性
  - `full_cleanup.bat` - 完整清理流程
  - `cleanup_comics.py` - Python 清理腳本
- 📚 **文檔大幅改善**: 重寫所有 README 和設置指南
- 🔧 **API 修復**: 修正網頁端無法生成圖片的問題
- 📊 **Manifest 改善**: 只包含完整的漫畫作品
- 🏗️ **架構優化**: 改善錯誤處理和用戶體驗
- 🧼 **專案清理**: 移除無用檔案和測試快取
- � **穩定性提升**: 全面測試和驗證

### v1.0.1 (2025-06-20)
- 🐛 修正各種小問題
- 📝 改善腳本生成品質
- 🔧 優化圖片處理流程

### v1.0.0 (2025-06-17)
- 🎉 初始版本發布
- ✍️ 基本腳本生成功能
- 🎨 圖像生成功能
- 🌐 網頁界面
- 🔧 Flask API 服務
- 📊 漫畫清單管理

##  作者與貢獻

- **主要開發者**: GitHub Copilot Assistant  
- **版本**: v1.0.2 (當前穩定版)
- **使用技術**: Google Gemini API, Python, Flask, HTML5/CSS3/JavaScript
- **授權**: MIT License

## 🤝 貢獻

歡迎提交 Issues 和 Pull Requests！

### 貢獻指南
1. Fork 此專案
2. 創建功能分支 (`git checkout -b feature/amazing-feature`)
3. 提交更改 (`git commit -m 'Add some amazing feature'`)
4. 推送到分支 (`git push origin feature/amazing-feature`)
5. 開啟 Pull Request

## ⚠️ 重要提醒

- 🌐 **網路需求**: 需要穩定的網際網路連線
- 🔑 **API 限制**: 免費 Google API 有配額限制
- ⏱️ **生成時間**: 圖像生成可能需要較長時間（1-2分鐘）
- 🌍 **地區限制**: 某些地區可能無法使用圖像生成功能
- 💾 **儲存空間**: 確保有足夠的磁碟空間儲存生成的圖像
- 🧹 **定期清理**: 建議定期使用清理工具維護專案整潔
- 📊 **清單同步**: 新增或刪除漫畫後請更新清單

## 🔗 相關連結

- [Google AI Studio](https://makersuite.google.com/app/apikey) - 取得 API 金鑰
- [Google Gemini API 文檔](https://ai.google.dev/docs) - API 詳細說明
- [Flask 官方文檔](https://flask.palletsprojects.com/) - Web 框架文檔

---

🎨 **四格漫畫生成器 v1.0.2 - 享受創作的樂趣！** 🎨

> **穩定版功能**：完整的漫畫生成流程 | 網頁界面 | 自動清理工具 | 完善文檔  
> **GitHub**: [comics](https://github.com/sheng-luen-chung/comics) | **最新版本**: v1.0.2
