# 工程品質

[English](ENGINEERING_QUALITY.md) · [繁體中文](ENGINEERING_QUALITY.zh-TW.md)

研究與交易的邊界，必須有程式實作和測試作為保障，而不能只靠文件宣告。

## 開發驗證

- Python 3.12、`mypy` 型別檢查、`Ruff` 程式碼檢查與 `pytest`。
- 單元與整合測試涵蓋資料、研究契約、交易所 Adapter，以及強型別的風控與執行邊界。
- 離線端到端（E2E）測試涵蓋策略投影、TradingHost、復原路徑與多部署狀態隔離。
- 線上 Testnet 檢查需明確啟用；**離線 E2E 通過不等於**線上、GCP、無人值守或正式交易認證。

## 防禦性設計

**無法確認就停止：** 來源證據不足、Artifact Identity 不符、部署契約不相容、風控輸入過期或持倉歸屬不明時，拒絕受影響的操作，而不是放寬規則。

**時間點一致的研究：** 開發研究不得任意讀取超出核准時間或證據範圍的資料；Protected Holdout 另有獨立權限。

**精確財務狀態：** 價格、數量、餘額與風控計算以 `Decimal` 等精確表示處理。所有新單都須先通過全域與部署級曝險檢查。

**原子資金分配：** 共用 Portfolio 與 SQLite Journal 協調多部署 Reservation，以確定性的准入順序避免行情抵達順序決定資金分配結果。

**保留並復原不確定狀態：** 逾時及不明委託保留 `UNKNOWN`，先完成對帳。Checkpoint、訂單身分、預留資金與持倉在程序重啟後仍可追溯；無法證明的部署歸屬不靠猜測。

## 可追溯性

Formal Research 綁定 Git 版本中的設定、封存證據與精確 Run Identity。Trading Deployment 另需固定的策略／Catalog 語意和明確 Manifest；研究結果不直接授予送單權限。

這些測試證明的是**工程邊界**，並不證明策略獲利或已取得真實資金下單授權。
