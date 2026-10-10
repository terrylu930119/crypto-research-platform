# 設計案例

[English](CASE_STUDIES.md) · [繁體中文](CASE_STUDIES.zh-TW.md)

## 不靠猜測處理資料缺口

缺一根 K 線，不代表一定是資料損壞或交易所停機。只有來源證據足夠時才分類，否則就維持「尚未確認」。

重點是：不能因為資料麻煩，就把研究規則放寬。

## 下單逾時不等於下單失敗

請求逾時時，交易所仍可能已經收到委託。如果直接重試，可能產生重複部位。

因此執行模型保留明確的 `UNKNOWN` 狀態，必須先和交易所狀態核對，再決定是否重試。

## 確定性驗證後再封存研究內容

主要研究 Agent 可以提出假說、控制組設計、判定標準或下一階段的研究方案。封存前的 deterministic validators 會檢查 schema、criteria 語意、source capability 與 artifact identity；同儕意見屬選用。

這些機械檢查能確定 artifact 格式和 identity 合法，卻無法判斷研究設計是否有公平控制、合理解讀或適當的 claim 範圍。移除強制審查後，這部分科學品質保障不再由 workflow gate 提供。

正式量測完成後 frozen methodology 與 evidence identity 不得變更；correctness、VOID 與已消耗輪次修復仍須 Human 決定。

## 自動化不能越過研究邊界

自主研究流程可以協調第一到第三階段的開發研究，也能在第三階段通過後完成受限的第四階段準備工作，但它不能繞過正式研究權限、第四階段的正式授權或保護性留出控制。
