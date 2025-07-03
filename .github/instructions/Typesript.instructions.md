---
applyTo: '**/*.ts'
---
# TypeScript 程式碼標準與指引

以下為本專案 TypeScript 程式碼撰寫規範，請所有 AI 程式碼產生器（如 GitHub Copilot）遵循：

## 命名規範
- 變數、函式名稱採用 camelCase。
- 類別名稱採用 PascalCase。
- 常數名稱採用全大寫加底線（如 MY_CONSTANT）。

## 型別與介面
- 優先使用型別註記（type annotation），避免 any。
- 使用 interface 定義物件結構，除非需用 type 支援聯集、交集等進階型別。
- 型別明確，避免隱式型別推斷。

## 函式
- 函式必須有明確的回傳型別。
- 避免過長的函式，建議單一職責。
- 參數多時，建議傳入物件。

## 類別與物件導向
- 優先使用 class 進行物件導向設計。
- 屬性與方法皆需標註存取修飾詞（public/private/protected）。
- 建議使用 constructor 進行依賴注入。

## 其他
- 使用 ES6+ 語法（如 let/const、箭頭函式、解構賦值等）。
- 善用 async/await 處理非同步。
- 盡量避免副作用（side effect），維持函式純粹。
- 加入必要的註解與文件說明。
- 程式碼需通過 linter 與 formatter（如 ESLint、Prettier）。

## 範例
```typescript
/**
 * User 物件結構
 * @property {number} id - 使用者唯一識別碼
 * @property {string} name - 使用者名稱
 */
interface User {
  id: number;
  name: string;
}

/**
 * UserService 類別，負責管理 User 物件
 */
class UserService {
  private users: User[] = [];

  /**
   * 新增一位使用者至 users 陣列
   * @param {User} user - 要新增的使用者物件
   * @returns {void}
   */
  public addUser(user: User): void {
    this.users.push(user);
  }

  /**
   * 依據 id 取得對應的使用者
   * @param {number} id - 使用者唯一識別碼
   * @returns {User | undefined} 找到則回傳 User，否則回傳 undefined
   */
  public getUser(id: number): User | undefined {
    return this.users.find(u => u.id === id);
  }
}
```

## TYPEDOC

- Use JSDoc-style comments with TypeScript-specific annotations for all public APIs
- Configure custom themes to match {{project_branding}} for consistent documentation
- Group related functionality using @module and @category tags for better organization
- Document edge cases and error handling for {{critical_functions}}
- Generate and publish documentation as part of the CI/CD pipeline to keep it current
- Include usage examples for complex interfaces and abstract classes
