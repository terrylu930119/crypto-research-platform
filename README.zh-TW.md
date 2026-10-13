# 加密貨幣量化研究與受控交易平台

[English](README.md) · [繁體中文](README.zh-TW.md)

這是一套以 Python 開發的加密貨幣量化研究與受控交易平台。它不以累積漂亮的回測結果為目標，而是重視資料可信度、可重現的科學驗證，以及研究和實際交易權限之間的明確分界。

## 已實作的主要能力

- **資料與證據：** Binance Spot、USD-M 研究資料、來源追蹤、時間點一致的資料視圖，以及不接觸未來結果的預檢。
- **受治理的研究流程：** 分階段量測、封存研究標準與產物、明確的科學決策，以及受保護的證據邊界。
- **自主開發研究：** Agent 在限定範圍內操作 Stage 1–3，並能進行 Stage4A 設計準備；研究採用確定性驗證與科學協作。完成的 Campaign 可經 READY 發布及 GitHub 流程整合。
- **共用策略語意：** Research 與 Trading 使用中立的策略引擎，經由 Catalog 與 Deployment Manifest 明確綁定策略。
- **受控交易：** 離線重播、Shadow 與受權限限制的 Binance Spot Testnet。多部署 Host 支援全域與各部署風控、原子資金預留、持久化狀態、交易所對帳與復原。
- **工程檢查：** 型別檢查、程式碼檢查、單元、整合與離線端到端（E2E）測試。

## 能力邊界

這**不是已投入正式市場的自動交易服務**，目前核准上線的 Production Strategy 為 **0**。長駐 Testnet Runtime 與多策略部署功能已有實作，但離線測試不等於完成 B8 線上 Testnet 驗證或 GCP 無人值守認證。正式市場送單、期貨交易及真實資金權限均不在目前 Trading 範圍內。

## 公開範圍

完整程式碼保留在私人 Repository。公開文件只說明工程架構、研究方法與設計取捨，不公開策略假說、完整規則、參數、量測結果、Protected Holdout 證據或操作密鑰。

- [系統架構](ARCHITECTURE.zh-TW.md)
- [研究方法](RESEARCH_METHODOLOGY.zh-TW.md)
- [工程品質](ENGINEERING_QUALITY.zh-TW.md)
- [設計案例](CASE_STUDIES.zh-TW.md)
- [公開邊界](SECURITY_AND_DISCLOSURE.zh-TW.md)
