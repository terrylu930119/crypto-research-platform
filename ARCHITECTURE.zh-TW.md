# 系統架構

[English](ARCHITECTURE.md) · [繁體中文](ARCHITECTURE.zh-TW.md)

平台把市場資料、研究與下單執行拆成不同邊界。某一層出問題時，不應默默改變其他層的行為或研究結論。

```mermaid
flowchart TD
    A[Binance 市場資料] --> B[已驗證的本地資料]
    B --> C[受時間邊界限制的研究資料]
    C --> D[研究 Agent 與確定性研究流程]
    D --> E[封存前的確定性驗證]
    E --> F[寫入 Git 的研究依據]
    F --> G[正式量測與研究決策]

    A --> H[交易所介面層]
    H --> I[測試網下單]
```

## 主要邊界

**資料層**負責下載、標準化、完整性檢查、交易時段判定與來源追蹤。

**研究層**只能使用受時間邊界限制的資料。正式量測、研究解讀與是否進入下一階段分開處理。

**執行層**使用強型別資料模型，價格、數量與餘額以 `Decimal` 計算。無法確認結果的委託會進入 `UNKNOWN` 狀態，而不是直接重試。

**治理層**把正式研究、後續階段與版本控制中的設定及研究產物綁定。deterministic validators 在首次 Git seal 前檢查 schema、criteria 語意、資料能力與 exact artifact identity。這些檢查驗證格式與 authority，不代表科學假說或因果設計已獲認可；同儕意見屬選用。

**自動研究**不會繞過這些邊界。主要研究 Agent 依 bounded control plane 完成 Stage 1–3 開發研究，並可在條件符合時完成 Stage4A 準備。量測後 frozen methodology 與 evidence identity 維持固定；correctness、VOID、已消耗輪次修復、Stage 4 formal 與 Protected Holdout 仍由 Human 決定。
