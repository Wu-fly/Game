# GitHub Pages 部署指南

本指南将帮助你将游戏部署到GitHub Pages，让任何人都可以通过网址访问。

## 准备工作

### 1. 创建GitHub账号

如果你还没有GitHub账号，请访问 [github.com](https://github.com) 注册一个免费账号。

### 2. 安装Git（如果还没有）

下载并安装Git：[git-scm.com](https://git-scm.com/downloads)

## 方法一：使用GitHub网页界面（最简单）

### 步骤1：创建新仓库

1. 登录GitHub
2. 点击右上角的 `+` 号，选择 `New repository`
3. 填写仓库信息：
   - **Repository name**: 输入仓库名称（例如：`taobao-bomberman-game`）
   - **Description**: 可选，输入描述（例如：伪装成淘宝页面的泡泡堂游戏）
   - **Public/Private**: 选择 `Public`（公开）或 `Private`（私有）
4. 点击 `Create repository`

### 步骤2：上传文件

1. 在新创建的仓库页面，点击 `uploading an existing file`
2. 将以下文件拖拽到上传区域：
   - `index.html`
   - `README.md`
   - `.gitignore`
3. 在 "Commit changes" 区域输入提交信息（例如：`Initial commit`）
4. 点击 `Commit changes`

### 步骤3：启用GitHub Pages

1. 进入仓库页面
2. 点击上方的 `Settings` 标签
3. 在左侧菜单中找到 `Pages`（在 "Code and automation" 部分）
4. 在 `Build and deployment` 部分：
   - **Source**: 选择 `Deploy from a branch`
   - **Branch**: 选择 `main` 分支
   - **Folder**: 选择 `/ (root)`
5. 点击 `Save`

### 步骤4：等待部署

1. 保存后，GitHub会自动开始部署
2. 等待1-3分钟
3. 在Pages设置页面会显示你的网站URL，格式为：`https://你的用户名.github.io/仓库名/`

### 步骤5：访问游戏

在浏览器中打开显示的URL即可开始游戏！

---

## 方法二：使用Git命令行（推荐）

### 步骤1：创建新仓库

按照方法一的步骤1创建新仓库，但**不要**初始化README、.gitignore或license。

### 步骤2：初始化本地Git仓库

打开命令行（CMD或PowerShell），进入项目目录：

```bash
cd c:\Users\admin\Desktop\game
```

### 步骤3：初始化Git并提交

```bash
# 初始化Git仓库
git init

# 添加所有文件
git add .

# 提交更改
git commit -m "Initial commit - 淘宝伪装版泡泡堂游戏"
```

### 步骤4：连接远程仓库

```bash
# 添加远程仓库（替换为你的仓库地址）
git remote add origin https://github.com/你的用户名/你的仓库名.git

# 重命名主分支为main
git branch -M main

# 推送到GitHub
git push -u origin main
```

如果遇到身份验证问题，GitHub会提示你使用Personal Access Token。

### 步骤5：启用GitHub Pages

按照方法一的步骤3-5启用GitHub Pages。

---

## 方法三：使用GitHub Actions自动部署（最自动化）

### 步骤1-4：按照方法二完成

先按照方法二的步骤1-4完成仓库创建和代码推送。

### 步骤5：启用GitHub Actions

1. 进入仓库页面
2. 点击 `Settings` -> `Pages`
3. 在 `Build and deployment` 部分：
   - **Source**: 选择 `GitHub Actions`
4. 选择 `Static HTML` 工作流（如果提示）
5. 点击 `Configure`

或者，项目已经包含了 `.github/workflows/deploy.yml` 文件，GitHub会自动识别并部署。

### 步骤6：启用Pages

1. 在Pages设置页面，确认 `Source` 已设置为 `GitHub Actions`
2. GitHub会自动运行部署工作流
3. 等待1-3分钟，部署完成后会显示网站URL

---

## 获取GitHub Personal Access Token（如需要）

如果使用Git命令行时遇到身份验证问题：

1. 登录GitHub
2. 点击右上角头像 -> `Settings`
3. 左侧菜单 -> `Developer settings`
4. `Personal access tokens` -> `Tokens (classic)`
5. 点击 `Generate new token` -> `Generate new token (classic)`
6. 填写信息：
   - **Note**: 输入描述（例如：`Git access for game repo`）
   - **Expiration**: 选择过期时间（建议选择 `No expiration` 或较长时间）
   - **Scopes**: 勾选 `repo`（全部权限）
7. 点击 `Generate token`
8. **重要**：复制生成的token（只显示一次）

### 使用Token推送

```bash
# 推送时会提示输入用户名和密码
# 用户名：你的GitHub用户名
# 密码：粘贴刚才复制的Personal Access Token
git push -u origin main
```

---

## 更新游戏

当你修改了游戏代码后，更新到GitHub：

```bash
# 查看修改的文件
git status

# 添加所有修改
git add .

# 提交更改
git commit -m "更新游戏内容"

# 推送到GitHub
git push
```

GitHub会自动重新部署，几分钟后即可在网站上看到更新。

---

## 常见问题

### Q: 部署后页面显示404

**A**: 确保你的仓库中有 `index.html` 文件，并且文件名完全匹配（小写）。

### Q: 图片无法加载

**A**: 检查 `index.html` 中的图片URL是否使用HTTPS协议。

### Q: 游戏无法运行

**A**: 确保所有JavaScript代码都在 `index.html` 中，没有外部依赖文件。

### Q: 如何修改网站URL？

**A**: GitHub Pages的URL格式是固定的：`https://你的用户名.github.io/仓库名/`。如果需要自定义域名，可以在Pages设置中配置。

### Q: 如何让仓库私有但网站公开？

**A**: GitHub Pages不支持私有仓库的公开网站。如果需要私有代码，可以考虑使用Vercel或Netlify。

---

## 其他部署平台

如果GitHub Pages不满足需求，你也可以使用：

### Vercel

1. 访问 [vercel.com](https://vercel.com)
2. 使用GitHub账号登录
3. 点击 `New Project`
4. 选择你的仓库
5. 点击 `Deploy`

### Netlify

1. 访问 [netlify.com](https://netlify.com)
2. 使用GitHub账号登录
3. 点击 `Add new site` -> `Import an existing project`
4. 选择你的仓库
5. 点击 `Deploy site`

---

**祝你部署成功！🎉**