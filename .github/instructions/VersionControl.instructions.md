---
applyTo: '**'
---

# 版本控制指引

## GIT

- 使用約定式提交 (Conventional Commits) 建立有意義的提交訊息
- 使用具有描述性名稱的功能分支，遵循以下命名規範:
  - `feature/[功能描述]`：新功能開發（例如：`feature/user-authentication`）
  - `bugfix/[問題描述]`：錯誤修復（例如：`bugfix/login-validation`）
  - `release/v[版本號]`：發布準備（例如：`release/v1.2.0`）
  - `hotfix/[問題描述]`：緊急修復（例如：`hotfix/critical-auth-issue`）
- 撰寫有意義的提交訊息，解釋「為什麼」進行變更，而非僅描述「做了什麼」
- 保持提交專注於單一邏輯變更，以便於程式碼審查和二分查找
- 在合併功能分支前使用互動式 rebase 清理歷史記錄
- 利用 git hooks 在提交和推送前強制執行程式碼品質檢查

## 分支策略

- 維護兩個永久分支：
  - `main`：正式環境分支，僅包含穩定、可發布的程式碼
  - `develop`：開發環境分支，整合已完成的功能
- 遵循 Gitflow 工作流程：
  - 所有新功能從 `develop` 分支建立功能分支
  - 功能完成後透過合併請求 (Pull Request) 合併回 `develop`
  - 發布準備時從 `develop` 建立發布分支
  - 發布完成後合併至 `main` 與 `develop`
  - 線上問題從 `main` 建立熱修復分支，完成後合併回 `main` 與 `develop`
- 使用語意化版本規範 (Semantic Versioning)：`主版本.次版本.修補版本`
- 每次發布都在 `main` 分支上建立對應的標籤

## GITHUB

- 使用合併請求範本標準化提供給程式碼審核的資訊
- 為受保護分支 (`main`, `develop`) 實施分支保護規則以強制品質檢查
- 設定必要狀態檢查，防止合併失敗測試或程式碼風格檢查的程式碼
- 使用 GitHub Actions 建立 CI/CD 工作流程以自動化測試和部署
- 實作 CODEOWNERS 檔案，根據程式碼路徑自動指派審核者
- 使用 GitHub Projects 追蹤工作項目並將其連接到程式碼變更

## 提交與審核流程

- 每個合併請求至少需要一名審核者核准
- 自動化測試必須通過才能合併至主要分支
- 合併前使用互動式 rebase 整理提交歷史
- 使用 Squash and merge 策略合併小型功能分支
- 使用 Merge commit 策略合併大型功能分支或發布分支
- 定期清理已合併的功能分支
