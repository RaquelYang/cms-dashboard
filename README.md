# CmsDashboard

這個專案是使用 [Angular CLI](https://github.com/angular/angular-cli) 版本 20.0.3 建立的。

## 開發伺服器

要啟動本地開發伺服器，請執行：

```bash
ng serve
```

一旦伺服器執行，請開啟瀏覽器並導航至 `http://localhost:4200/`。當您修改任何原始檔案時，應用程式會自動重新載入。

## CI/CD 部署

此專案已設定 GitHub Actions 自動部署到 GitHub Pages。

### 設定步驟

1. **在 GitHub 儲存庫設定中啟用 GitHub Pages：**
   - 前往您的 GitHub 儲存庫
   - 點擊 `Settings` 標籤
   - 滾動到 `Pages` 區段
   - 在 `Source` 下選擇 `GitHub Actions`

2. **推送程式碼到 master 分支：**
   ```bash
   git add .
   git commit -m "Add CI/CD workflow"
   git push origin master
   ```

3. **檢查部署狀態：**
   - 前往 `Actions` 標籤查看工作流程執行情況
   - 部署完成後，您的網站將可在 `https://yourusername.github.io/cms-dashboard/` 存取

### 工作流程功能

- **自動測試：** 每次推送都會執行單元測試
- **建構驗證：** 確保專案可以成功建構
- **自動部署：** 只有 master 分支的變更會觸發部署
- **快取最佳化：** 使用 npm 快取加速建構過程

## 程式碼原理圖

Angular CLI 包含強大的程式碼原理圖工具。要產生新元件，請執行：

```bash
ng generate component component-name
```

For a complete list of available schematics (such as `components`, `directives`, or `pipes`), run:

```bash
ng generate --help
```

## Building

To build the project run:

```bash
ng build
```

This will compile your project and store the build artifacts in the `dist/` directory. By default, the production build optimizes your application for performance and speed.

## Running unit tests

To execute unit tests with the [Karma](https://karma-runner.github.io) test runner, use the following command:

```bash
ng test
```

## Running end-to-end tests

For end-to-end (e2e) testing, run:

```bash
ng e2e
```

Angular CLI does not come with an end-to-end testing framework by default. You can choose one that suits your needs.

## Additional Resources

For more information on using the Angular CLI, including detailed command references, visit the [Angular CLI Overview and Command Reference](https://angular.dev/tools/cli) page.
