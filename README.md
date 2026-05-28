# 个人主页 - GitHub Pages

这是一个使用 Vue 3 + Vite 构建的个人主页项目，专为 GitHub Pages 部署配置。

## 项目结构

```
testgithubpages/
├── src/
│   ├── App.vue          # 主应用组件
│   ├── main.js          # 应用入口
│   └── style.css        # 全局样式
├── dist/                # 编译后的生产文件（用于部署）
├── index.html           # HTML 模板
├── vite.config.js       # Vite 配置
└── package.json         # 项目依赖
```

## 如何部署到 GitHub Pages

### 方法 1：手动部署 dist 目录

1. 将整个项目推送到 GitHub 仓库
2. 在 GitHub 仓库设置中：
   - 进入 "Settings" -> "Pages"
   - 在 "Build and deployment" 部分，选择 "Source" 为 "Deploy from a branch"
   - 选择分支（例如 main 或 gh-pages）
   - 选择文件夹为 `/ (root)` 或 `/dist`（取决于你的设置）
3. 或者，你可以只将 dist 目录的内容推送到 gh-pages 分支

### 方法 2：使用 gh-pages 工具（推荐）

1. 安装 gh-pages：
   ```bash
   npm install -D gh-pages
   ```

2. 在 package.json 中添加部署脚本：
   ```json
   "scripts": {
     "deploy": "gh-pages -d dist"
   }
   ```

3. 运行部署：
   ```bash
   npm run deploy
   ```

### 注意事项

- 本项目已在 vite.config.js 中配置了 base 为 `/testgithubpages/`，确保你的仓库名一致
- 如果仓库名不同，请修改 vite.config.js 中的 base 配置
- 每次修改代码后，需要重新运行 `npm run build` 然后部署

## 开发

```bash
# 安装依赖
npm install

# 启动开发服务器
npm run dev

# 构建生产版本
npm run build
```

## 自定义内容

你可以修改 src/App.vue 中的以下内容：
- 姓名和职位
- 个人简介
- 社交链接
- 技术栈
