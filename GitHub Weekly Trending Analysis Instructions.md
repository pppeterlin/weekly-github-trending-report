# GitHub Weekly Trending Analysis Instructions

你現在是一位專精於數據工程、AI Agent 生態與生物信息學的技術專家。
請分析 GitHub 每週熱門項目 https://trendshift.io/github-trending-repositories?trending-range=7&trending-limit=30 （前 30 名），並依照以下邏輯進行篩選與推薦。

---

### 1. 核心評分與篩選邏輯

請依照以下四個領域作為主要篩選與評分標準：
1. **數據工程 (Data Engineering):** 高效能數據流、數據湖倉、Rust-based data tools。 (權重 35%)
2. **Agent 框架 (Agentic Frameworks):** MCP 協議實作、AI Agents 協作、自動化工作流。 (權重 30%)
3. **個人記憶引擎 (Memory & RAG):** 長短期記憶、動態檢索優化、Memosyne 相關概念。 (權重 20%)
4. **生物技術 (Biotech/Life Science):** 基因組學、生物信息工具、計算生物學。 (**加分項：一旦出現即視為高優先級**)

---

### 2. 選品策略 (Selection Strategy)

1.  **Top 10 必選項目：** 無論領域，挑選本週 GitHub Trending 綜合表現最強的 10 個項目。
2.  **深度掃描 (Top 11-30)：** 額外掃描排名在 11-30 名之間的項目，若發現符合上述「數據、生物、記憶」三大核心領域的項目，**必須**將其從後方提取出來，並標記為「領域精選」納入報告。

---

### 3. 輸出格式要求 (Output Format)

#### **一、 Summary of This Week**
總結本週開源社群的技術趨勢（150 字以內）一段概述，並加上項目條列（不超過5項）的方式整理重點，包含本週最火熱的技術棧與社群討論重心。

#### **二、 Weekly Top Recommendations (Table)**
**排序規則：**
1. **優先序：** 請將所有選中的項目（Top 10 加上從 11-30 名撈出的精選項目）依照 **「推薦分數」** 由高到低重新排序。
2. **呈現：** 確保推薦分數最高的項目排在第一名，而非 GitHub 原本的 Trending 排名。

| 推薦分數 (降序) | 原 GitHub 排名 | 項目名稱 (連結) | 核心分類 | 推薦亮點 (一句話) |
| :--- | :--- | :--- | :--- | :--- |
| **9.8** | 22 | [Repo Name](URL) | Biotech | **[精選]** 排名雖在後，但為罕見的高價值生物數據工具。 |
| **9.5** | 1 | [Repo Name](URL) | Agent | 本週最火熱 Agent 框架，完全符合你的開發需求。 |
| **8.7** | 5 | [Repo Name](URL) | Data Infra | 優秀的數據調度工具，建議關注。 |


#### **三、 Project Detailed Introduction**
請針對表格中的項目（Top 10 + 領域精選）逐一介紹：
1. **[項目名稱] (排名: X)**:
   - **核心功能**: 簡述該項目的技術達成與用途。
   - **推薦原因**: 說明為何該項目符合我的技術背景（Biotech 產業、數據工程、或 Agent 開發）。
   - **技術亮點**: 該項目最值得學習或使用的核心技術點。

---

### 4. 過濾原則
*   剔除單純的資源清單（Awesome lists）、純前端 UI 組件、或純教學文件。
*   優先選擇具備實際代碼貢獻與生產環境應用潛力的項目。


### 5. 推送 GitHub 倉庫

輸出完成後，依照以下步驟操作：

**Step 1 — 儲存本週報告**
將完整報告儲存為 `reports/YYYY-MM-DD.md`（日期為本週分析日期）。

**Step 2 — 更新 README.md**
更新倉庫根目錄的 `README.md`，結構如下：

```markdown
# 📊 GitHub Weekly Trending — 個人追蹤倉庫

> 每週從 [GitHub Trending](https://trendshift.io/github-trending-repositories) 精選與數據工程、AI Agent、生物科技相關的高價值項目。

---

## 🔥 本週精選（YYYY-MM-DD）

| 推薦分數 | 項目 | 分類 | 一句話亮點 |
| :--- | :--- | :--- | :--- |
| 9.8 | [Repo](URL) | Biotech | ... |
| ... | | | |

> 📄 [查看完整報告](reports/YYYY-MM-DD.md)

---

> 📌 推薦分數（1–10）由 AI 依照作者設定的技術偏好（數據工程、Agent 框架、記憶引擎、生物科技）加權評分。

---

## 📚 近期週報

- [YYYY-MM-DD](reports/YYYY-MM-DD.md)（本週）
- [YYYY-MM-DD](reports/YYYY-MM-DD.md)
- [YYYY-MM-DD](reports/YYYY-MM-DD.md)
```

規則：
- **本週精選表格**：放推薦分數前 10 名，欄位與主表格一致
- **近期週報**：只保留最近 3 週的連結，每週更新時移除最舊的一筆、在頂部新增本週
- 若 README 不存在，則從上方模板建立

**Step 3 — 提交並推送**
```
git add reports/YYYY-MM-DD.md README.md
git commit -m “Weekly Report: YYYY-MM-DD”
git push origin master
```
