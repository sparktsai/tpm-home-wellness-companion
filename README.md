# HomeWellness Companion - 家庭健康關懷伴侶

主動式健康關懷與用藥提醒系統，透過 AI Agent 與 IoT 整合，為長者提供個人化的健康管理與生活關懷。

---

## 📋 核心文件說明

### 1. [prd_snippet.pdf](./prd_snippet.pdf)
**產品需求文件（Product Requirements Document）**
- 項目定位與功能概述
- 雙 Persona 用戶旅程設計：
  - **Journey A - 王阿姨**：主動式健康關懷（IoT 血壓計觸發）
  - **Journey B - 李爺爺**：喚聲式數位陪伴（語音查詢觸發）
- 用戶故事與使用情境
- 功能架構與數據流
- 規格重點與超出範圍項目

**參考位置**：架構設計與需求理解的起點

---

### 2. [health-companion-chat-flow.json](./health-companion-chat-flow.json)
**健康伴侶聊天流程（Langflow 實作）**
- **Flow ID**：`health-companion-chat-flow-v1`
- **應用場景**：Journey B - 長者日常健康查詢對話
- **核心功能**：
  - 聊天輸入/輸出處理
  - AI Agent 對話推理
  - 生活狀態分享與健康諮詢
  - 結構化回應格式化與驗證
- **技術棧**：Langflow 組件編排，支持記憶與工具調用

**參考位置**：了解聊天互動流程與 AI 對話邏輯

---

### 3. [iot-event-care-flow.json](./iot-event-care-flow.json)
**IoT 事件關心流程（Langflow 實作）**
- **Flow ID**：`iot-event-care-flow-v1`
- **應用場景**：Journey A - 血壓計事件主動觸發關懷
- **核心功能**：
  - IoT 裝置事件驗證與解析
  - 相對生命體徵分析（Relative Vital Analyzer）
  - 事件路由與場景判定（高血壓 + 心率組合分類）
  - 提示詞模板生成主動關懷訊息
  - 結構化輸出驗證
- **技術棧**：自定義組件、提示詞工程、結構化輸出

**參考位置**：理解物聯網驅動的主動關懷邏輯

---

### 4. [home_wellness_companion.pptx](./home_wellness_companion.pptx)
**專案簡報與視覺呈現**
- 項目概述與商業目標
- 用戶旅程與場景演示
- 系統架構圖
- 關鍵功能與設計亮點

**參考位置**：快速掌握項目願景與整體架構

---

## 🏗️ 架構概覽

```
HomeWellness Companion
├─ Journey A: 主動關懷流程 (iot-event-care-flow-v1)
│  ├─ 觸發源：IoT 血壓計 → 裝置事件
│  ├─ 核心邏輯：相對生命體徵分析 → 場景判定 → 提示詞生成
│  └─ 輸出：結構化關懷訊息（自動下發）
│
└─ Journey B: 聊天查詢流程 (health-companion-chat-flow-v1)
   ├─ 觸發源：用戶語音/文字查詢
   ├─ 核心邏輯：AI Agent 對話 → 工具調用（取得用藥記錄/睡眠史等）
   └─ 輸出：個人化健康建議與陪伴訊息（實時互動）
```

---

## 🔗 相關資源

- **Langflow 文檔**：https://docs.langflow.org/
- **自定義組件參考**：見各 Flow JSON 內的 `RelativeVitalAnalyzer`、`PromptTemplate` 等定義
- **數據結構**：詳見 PRD 第 4 節「觸發條件與資料流」

---

## 📝 快速導航

| 用途               | 參考檔案             |
| ------------------ | -------------------- |
| 理解產品願景與需求 | prd_snippet.pdf      |
| 查看實際 Flow 配置 | .json 檔案           |
| 向他人介紹項目     | home_wellness_companion.pptx            |
| 確認技術實作細節   | 各 Flow 內的組件代碼 |