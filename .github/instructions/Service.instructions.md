---
applyTo: '**/*.service.ts'
---
# 服務層（Service）程式碼標準與指引

以下為本專案服務層（Service）設計與實作規範，請所有 AI 程式碼產生器（如 GitHub Copilot）遵循：

## 設計原則
- 服務層負責商業邏輯與資料處理，與控制器、資料存取層分離。
- 每個服務應為單一職責，易於測試與維護。
- 服務方法應為公開（public），輔助方法可設為私有（private/protected）。
- 支援相依性注入（Dependency Injection），避免硬編碼相依。

## 命名與結構
- 服務類別名稱以 Service 結尾（如 UserService）。
- 方法命名需清楚表達用途。
- 服務檔案與類別名稱一致。

## TSDoc 註解
- 所有服務類別與公開方法需加上 TSDoc 註解，說明用途、參數、回傳值與例外狀況。

## TSDoc 範例
```typescript
/**
 * 用戶服務，負責用戶相關商業邏輯處理。
 */
class UserService {
  /**
   * 依 ID 取得用戶資訊。
   *
   * @param id - 用戶 ID
   * @returns 用戶物件，若找不到則回傳 undefined
   * @throws NotFoundError 若用戶不存在
   */
  public getUserById(id: number): User | undefined {
    // ...existing code...
  }
}
```

## 其他建議
- 服務方法應避免副作用，盡量維持純粹。
- 加入必要的單元測試。
- 重要邏輯與特殊處理需加上註解。
