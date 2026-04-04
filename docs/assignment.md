# DSAP 專題作業

## 作業概述

本專題作業讓你透過自主選題，獨立完成一個程式專案。你可以自由選擇想做的題目與使用的程式語言，重點在於**探索的過程**，以及你能否認知並說明自己的作品與「進階程式設計」及「資料結構」之間的關聯。

你不需要強制使用特定的資料結構或演算法，但你需要思考並說明：你的專題與課程內容之間存在什麼關係。

**AI 使用政策：** 允許使用任何 AI 工具輔助開發，不需標註。

## 繳交方式

### GitHub Repo

1. 使用課程提供的 template repo，點選 **"Use this template"** 建立你自己的 repo
2. Repo 中已有 README.md 模板，請依各階段要求填寫對應區段
3. 程式碼建議放在 `src/` 目錄下，但可依你使用的語言或框架調整目錄結構
4. 如果你使用的語言不在預設的 `.gitignore` 中，請自行擴充

### GitHub Release

每個階段的繳交以 **GitHub Release** 為準。請在各階段 deadline 前建立對應的 Release：

| 階段 | Release Tag | 繳交內容 |
|------|-------------|---------|
| Proposal Report | `proposal` | README.md Proposal Report 區段 |
| Prototype Report | `prototype` | README.md 進度區段 + 程式碼 |
| Final Report | `final-report` | README.md 完整版 + 程式碼 |

**GitHub Release 的建立時間由 GitHub 伺服器記錄，無法事後修改，將作為繳交時間依據。**

#### 如何建立 GitHub Release

1. 在你的 repo 頁面，點選右側 **"Releases"**
2. 點選 **"Create a new release"**
3. 在 "Choose a tag" 輸入對應的 tag 名稱（如 `proposal`），選擇 **"Create new tag"**
4. 填寫 Release title（如 `Proposal Report`）
5. 點選 **"Publish release"**

### Demo 影片

Final Report 需錄製 **5 分鐘以內**的影片，上傳至 YouTube 後透過課程網頁繳交連結。

**影片建議結構：**
- ~1 分鐘：專案介紹（做了什麼、為什麼做）
- ~2 分鐘：功能展示（實際操作畫面）
- ~2 分鐘：課程關聯說明（與資料結構、進階程式設計的關聯）

## 三個階段

### 1. Proposal Report（Week 7）

完成 README.md 中的 Proposal Report 區段，建立 Release `proposal`。

**需要包含：**
- 題目名稱、動機與目標
- 預期功能
- 使用的技術 / 語言
- 初步時程規劃

**請思考並回答：** 你的專題可能涉及哪些資料結構或演算法概念？為什麼？

### 2. Prototype Report（Week 11）

更新 README.md 的 Prototype Report 區段，確保 repo 中有實質程式碼，建立 Release `prototype`。

**需要包含：**
- 目前完成了什麼
- 遇到什麼困難
- 接下來的計畫

**請思考並回答：** 到目前為止，你的實作中哪些部分與課程內容有關？關係是什麼？

### 3. Final Report（Week 15）

完成 README.md 所有區段，確保程式碼完整，建立 Release `final-report`。另外透過課程網頁繳交 Demo 影片的 YouTube 連結。

## 評分

| 階段 | 比例 | 評分重點 |
|------|------|---------|
| Proposal Report | 10% | 題目合理性、思考深度 |
| Prototype Report | 30% | 有實質程式碼進展、能說明與課程關聯 |
| Final Report | 60% | 完成度、影片呈現品質、課程關聯說明深度 |

## 互動機制

每個階段繳交後，老師會透過 GitHub **Issue** 提出回饋或修改要求。你需要：

1. 閱讀老師在 Issue 中提出的要求
2. 開一個 **Pull Request (PR)** 來回應，在 PR 描述中說明你的解決方案
3. 等待老師 review，如有進一步要求則繼續修改

Issue 與 PR 的互動紀錄也是評分的參考依據之一。

## 遲交政策

- 以 GitHub Release 的建立時間為準
- 每遲交 **1 天**，扣該階段分數的 **10%**
- 超過 **3 天**未繳交，該階段 **零分**

## 換題政策

允許中途換題，但你必須在 repo 中開一個 **Issue** 說明換題原因。

## 題目難度參考

以下為範例題目，供你參考難度等級。你不限於這些題目，可以自由發揮：

- **小型：** CLI 記帳工具 — 用檔案儲存資料，支援新增、查詢、統計功能
- **中型：** 迷宮生成與求解 — 實作迷宮生成演算法，並用 BFS/DFS 求解，以文字或圖形呈現
- **挑戰型：** 簡易搜尋引擎 — 讀取多份文件建立索引，支援關鍵字搜尋與排序
