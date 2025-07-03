---
applyTo: '**/*.util.ts'
---
# 工具（Util）檔案程式碼標準與指引

以下為本專案工具（Util）檔案設計規範，請所有 AI 程式碼產生器（如 GitHub Copilot）遵循：

## 設計原則
- 工具僅負責通用、可重用的輔助功能，無業務邏輯。
- 工具函式應為純函式，避免副作用。
- 優先使用靜態方法或獨立函式，不需建立實例。
- 工具類別名稱以 Util 或 Helper 結尾（如 DateUtil、StringHelper）。

## 命名與結構
- 方法與函式命名需清楚表達用途。
- 工具檔案與類別名稱一致。

## TSDoc 註解
- 所有工具類別、函式需加上 TSDoc 註解，說明用途、參數、回傳值與例外狀況。

## TSDoc 範例
```typescript
/**
 * 檢查字串是否為有效的 Email 格式。
 * @param email - 欲檢查的字串
 * @returns 若為有效 Email 則回傳 true，否則回傳 false
 */
export function isValidEmail(email: string): boolean {
  // ...existing code...
}
```

## 其他建議
- 工具函式應有單元測試。
- 重要邏輯與特殊處理需加上註解。
