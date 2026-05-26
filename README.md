# 淘宝伪装版泡泡堂游戏

一个伪装成淘宝商品页面的Q版泡泡堂小游戏，包含人机对战和闯关机制。

## 游戏特色

- 🎮 **经典泡泡堂玩法**：放置炸弹，炸毁箱子，消灭敌人
- 🤖 **智能AI对战**：多个AI敌人，会追踪玩家并放置炸弹
- 📈 **闯关机制**：每关AI数量更多、移动更快、更智能
- 🎁 **道具系统**：炸弹数量、爆炸范围、护盾、速度提升、快速炸弹
- 🎭 **完美伪装**：游戏隐藏在淘宝商品页面中，鼠标悬停才显示游戏画面

## 游戏操作

- **移动**：方向键 或 WASD
- **放炸弹**：空格键
- **暂停**：P键

## 道具说明

- 💣 **炸弹数量**：增加可同时放置的炸弹数量
- 🔥 **爆炸范围**：增加炸弹爆炸的覆盖范围
- 🛡️ **护盾**：抵挡一次爆炸伤害
- ⚡ **速度提升**：暂时提升移动速度（5秒）
- ⏱️ **快速炸弹**：缩短炸弹引爆时间（10秒）

## 本地运行

### 方法一：使用Node.js服务器

1. 确保已安装Node.js
2. 在项目目录运行：
   ```bash
   node server.js
   ```
3. 在浏览器中打开 `http://localhost:8000`

### 方法二：直接打开

直接用浏览器打开 `index.html` 文件即可开始游戏。

## 部署到GitHub Pages

### 方法一：通过GitHub网页界面部署

1. 在GitHub上创建一个新仓库
2. 将 `index.html` 文件上传到仓库
3. 进入仓库的 **Settings** -> **Pages**
4. 在 **Source** 中选择 **Deploy from a branch**
5. 选择 `main` 分支和 `/ (root)` 目录
6. 点击 **Save**
7. 等待几分钟后，访问显示的GitHub Pages URL

### 方法二：通过Git命令部署

1. 初始化Git仓库：
   ```bash
   git init
   ```

2. 添加所有文件：
   ```bash
   git add .
   ```

3. 提交更改：
   ```bash
   git commit -m "Initial commit"
   ```

4. 添加远程仓库（替换为你的仓库地址）：
   ```bash
   git remote add origin https://github.com/你的用户名/你的仓库名.git
   ```

5. 推送到GitHub：
   ```bash
   git branch -M main
   git push -u origin main
   ```

6. 按照方法一的步骤3-6启用GitHub Pages

## 部署到Vercel

1. 访问 [vercel.com](https://vercel.com) 并登录/注册
2. 点击 **New Project**
3. 导入你的GitHub仓库
4. 点击 **Deploy**
5. 等待部署完成，Vercel会提供一个公共URL

## 部署到Netlify

1. 访问 [netlify.com](https://netlify.com) 并登录/注册
2. 点击 **Add new site** -> **Deploy manually**
3. 拖拽项目文件夹到上传区域
4. 等待部署完成，Netlify会提供一个公共URL

## 技术栈

- HTML5
- CSS3
- JavaScript (Canvas API)

## 许可证

MIT License

## 贡献

欢迎提交Issue和Pull Request！

---

**享受游戏！🎉**