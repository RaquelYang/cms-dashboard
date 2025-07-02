# GitHub Pages 部署指南

## 自動部署設定完成 ✅

此專案已設定完整的 CI/CD 流程，包含：

### 已建立的檔案：
- `.github/workflows/deploy.yml` - GitHub Actions 工作流程
- `public/404.html` - SPA 路由支援
- 更新的 `src/index.html` - 路由處理腳本
- 更新的 `package.json` - 新增部署指令

### 自動執行流程：
1. **程式碼檢查** - 當推送到 master 分支時觸發
2. **相依套件安裝** - 使用 npm ci 確保乾淨安裝
3. **單元測試執行** - 確保程式碼品質
4. **生產建構** - 最佳化建構與正確的 base-href 設定
5. **自動部署** - 部署到 GitHub Pages

### 下一步操作：

1. **在 GitHub 上啟用 Pages：**
   ```
   Repository Settings → Pages → Source: GitHub Actions
   ```

2. **推送程式碼：**
   ```bash
   git add .
   git commit -m "Add CI/CD deployment setup"
   git push origin master
   ```

3. **檢查部署：**
   - 前往 GitHub Actions 標籤查看執行狀態
   - 部署完成後訪問: `https://RaquelYang.github.io/cms-dashboard/`

### 功能特色：
- 🚀 自動化部署
- 🧪 自動測試
- 📱 SPA 路由支援
- ⚡ 建構快取最佳化
- 🔒 安全的權限設定

### 本地開發指令：
```bash
npm start              # 開發伺服器
npm run build:prod     # 生產建構
npm run test           # 互動式測試
npm run test:ci        # CI 測試（無瀏覽器）
```

### 注意事項：
- 只有 master 分支的變更會觸發部署
- Pull Request 會執行測試但不會部署
- 部署過程大約需要 2-5 分鐘
- 確保 GitHub 儲存庫設定為公開（或有 GitHub Pro）以使用 GitHub Pages
