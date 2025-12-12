

> 📢 **让零基础小白也能生成专业级的 Taro + Node.js 全栈项目，成为全栈工程师的路上踏出第一步。**

> ⚠️ **温馨提示**：这份提示词还在不断完善中，可能存在一些小问题。如果你在使用过程中遇到任何 Bug 或有改进建议，欢迎在评论区反馈，帮助我一起优化它！

---

## 🎯 这篇文章写给谁？

也许你是：
- 👔 有想法但不会写代码
- 🎓 想学全栈，不知道从哪开始

**我相信在 AI 时代，技术不应该成为实现想法的门槛。**

这份提示词就是为了帮助你——只要你有想法，AI + 这份提示词，就能帮你迈出全栈开发的第一步。

---

## 📊 技术栈一览

| 层级 | 技术选型 |
|------|----------|
| **跨端框架** | Taro 3.6.32 |
| **前端框架** | React 18 + TypeScript |
| **UI 组件库** | NutUI React Taro |
| **状态管理** | Zustand |
| **后端框架** | Express 4.x |
| **数据库** | PostgreSQL |
| **运行时** | Node.js 18+ (tsx 直接运行 TS) |
| **包管理** | pnpm workspace |

---

### 初衷

很多人有好的产品想法，却因为不会全栈开发而放弃。

**技术不应该成为实现想法的门槛**

我希望这份提示词能成为一座桥梁，让更多人迈出第一步。

### 我的背景

日常用 Vue 开发，一码多端选择的 uni-app。

最近想尝试 **React + Taro** 技术栈。但从 Vue 切到 React，配置、写法都不一样。

于是尝试用 AI 来帮我生成项目脚手架，效果出乎意料！


### 🙋 邀请你一起完善

这份提示词不是终点，而是一个起点。它还有很多可以改进的地方：

- 🗄️ 支持更多数据库（MySQL、MongoDB）
- 📱 支持更多小程序平台（支付宝、抖音、快手）
- 🧩 增加更多业务模块模板（支付、文件上传、消息推送）
- 🎨 优化 UI 组件和样式
- ...

**欢迎你参与贡献：**

| 你的情况 | 欢迎你 |
|----------|--------|
| 试用后发现了 Bug | 提 Issue 反馈 |
| 有更好的配置方案 | 提 PR 改进 |
| 想增加新功能模块 | Fork 后扩展，欢迎分享 |
| 成功上线了产品 | **在评论区分享你的故事！** |

**让我们一起，用 AI 降低技术门槛，让更多人能把想法变成现实。**

---

## 🛠️ 小白必看：电脑环境准备

在开始之前，请确保你的电脑安装了以下工具：

### 1. Node.js（必装）
- **作用**：运行 JavaScript/TypeScript 代码
- **版本要求**：18.0 或更高
- **下载地址**：https://nodejs.org/
- **验证安装**：打开终端输入 `node -v`，显示版本号即成功

### 2. pnpm（必装）
- **作用**：包管理工具，比 npm 更快更省空间
- **安装命令**：
  > ⚠️ **Windows 用户注意**：请右键「以管理员身份运行」命令提示符或 PowerShell，否则可能安装失败！
  ```bash
  npm install -g pnpm
  ```
- **验证安装**：`pnpm -v`

### 3. Git（推荐）
- **作用**：代码版本管理
- **下载地址**：https://git-scm.com/
- **验证安装**：`git --version`

### 4. VS Code（推荐）
- **作用**：代码编辑器
- **下载地址**：https://code.visualstudio.com/
- **推荐插件**：
  - ES7+ React/Redux/React-Native snippets
  - Prettier - Code formatter
  - TypeScript Vue Plugin (如果你也写 Vue)

### 5. 微信开发者工具（开发小程序必装）
- **作用**：预览和调试微信小程序
- **下载地址**：https://developers.weixin.qq.com/miniprogram/dev/devtools/download.html

### 6. PostgreSQL（后端数据库）
- **作用**：存储用户数据
- **下载地址**：https://www.postgresql.org/download/
- **或者用 Docker**：`docker run -d -p 5432:5432 -e POSTGRES_PASSWORD=123456 postgres:14`

---

## ✅ 环境检查清单

在终端运行以下命令，确保都能正常显示版本号：

```bash
node -v      # 应显示 v18.x.x 或更高
pnpm -v      # 应显示 8.x.x 或更高
git --version  # 应显示 git version x.x.x
```

全部 OK？那就可以开始了！ 🎉

---

## 🎯 这份提示词能帮你做什么？

### 👶 如果你是 Taro 新手

| 你的困惑 | 这份提示词怎么帮你 |
|----------|-------------------|
| 不知道项目怎么组织 | 直接给你 Monorepo 最佳实践结构 |
| 不懂配置怎么写 | 所有 config 文件都是完整可用的 |
| 担心代码不规范 | 遵循分层架构 + TypeScript 严格模式 |
| 怕踩坑浪费时间 | 已经帮你填好了常见的坑 |

**核心价值**：**从第一天就按最佳实践写代码**，而不是先写错再改。

---

### 💼 如果你是专业开发者

| 你的诉求 | 这份提示词怎么帮你 |
|----------|-------------------|
| 快速启动新项目 | 10 分钟生成完整脚手架，直接开始业务开发 |
| 不想重复造轮子 | 用户认证、API 封装、状态管理都写好了 |
| 保持技术选型一致 | 固定版本号，避免依赖冲突 |
| 需要可定制的模板 | 提示词结构清晰，随时按需修改 |

**核心价值**：**把重复的架构工作交给 AI**，你专注业务逻辑。

---

## 🚀 快速体验

### 让 AI 帮你生成

把下载下面的提示词发给 **AI**：

```
https://github.com/Luchen-0420/fullstack-prompt.git
```

AI 会生成完整的项目代码，你只需要：
1. 创建对应目录和文件
2. 粘贴代码
3. `pnpm install && pnpm dev`


---

## 🏃 如何运行项目

项目创建好后，需要同时启动**后端**和**前端**。

先进行数据库操作

### 数据库操作

#### step 1 : 登录账户

``` bash
psql -U postgres
```

#### step 2 : 建数据库

```bash
CREATE DATABASE prompt_demo;
```

#### step 3 :退出

```
\q
```

#### step 4 : 导入 schema.sql

```bash
psql -U postgres -d prompt_demo -f packages/server/src/db/schema.sql
```

### ⚡ 一键启动（推荐）

在项目**根目录**运行：

| 命令 | 说明 |
|------|------|
| `pnpm dev` | 一键启动后端 + H5 网页版 |
| `pnpm dev:weapp` | 一键启动后端 + 小程序编译 |

```bash
# 启动 H5 开发环境（后端 + 前端同时启动）
pnpm dev
```

> 💡 使用 `concurrently` 并行运行，无需手动开两个终端！

---

### 分步启动（详细说明）

如果一键启动遇到问题，可以分开启动：

#### Step 1: 启动后端服务

```bash
# 打开终端 1
cd packages/server

# 创建环境变量文件（首次运行）
cp .env.example .env

# 启动开发服务器
pnpm dev
```

看到以下输出表示成功：
```
🚀 Server is running on http://localhost:3000
```

#### Step 2: 启动 H5 网页版

```bash
# 打开终端 2
cd packages/taro-app

# 启动 H5 开发服务器
pnpm dev:h5
```

看到以下输出表示成功：
```
✔ Compiled successfully in xxx ms
```

打开浏览器访问 **http://localhost:10086** 即可看到页面。

#### Step 3: 启动微信小程序

```bash
# 打开终端 3
cd packages/taro-app

# 编译小程序
pnpm dev:weapp
```

编译完成后，需要用**微信开发者工具**打开：

1. 打开微信开发者工具
2. 点击「+」或「导入项目」
3. 项目目录选择：`packages/taro-app/dist/weapp`
4. AppID 可以先用「测试号」
5. 点击「导入」

导入后就能在模拟器中看到小程序运行了！ 🎉

### 常用命令速查

| 命令 | 说明 |
|------|------|
| `pnpm dev:h5` | 启动 H5 网页版 |
| `pnpm dev:weapp` | 编译微信小程序 |
| `pnpm build:h5` | 构建 H5 生产版本 |
| `pnpm build:weapp` | 构建小程序生产版本 |

---

## ❓ 启动常见问题

### 问题 1：后端启动报 `ECONNREFUSED` 或数据库连接失败

**原因**：PostgreSQL 没启动，或连接信息不对

**解决**：
```bash
# 检查 PostgreSQL 是否运行
# Windows: 打开"服务"，找 postgresql 服务
# Mac: brew services list

# 检查 .env 文件中的数据库配置
DB_HOST=localhost
DB_PORT=5432
DB_NAME=my_app_db
DB_USER=postgres
DB_PASSWORD=你的密码
```

### 问题 2：端口被占用 `EADDRINUSE`

**原因**：3000 或 10086 端口已被其他程序使用

**解决**：
```bash
# Windows 查看占用端口的进程
netstat -ano | findstr :3000

# 杀掉进程（用上面查到的 PID）
taskkill /PID 进程号 /F

# 或者修改 .env 中的 PORT
```

### 问题 3：H5 请求 API 返回 404

**原因**：代理配置不对，或后端没启动

**解决**：
1. 确认后端已启动（终端显示 `Server is running`）
2. 检查 `config/dev.ts` 中的 proxy 配置
3. 确保请求路径以 `/api` 开头

### 问题 4：小程序报 `module 'prebundle/xxx' is not defined`

**原因**：Taro 的 prebundle 功能与 NutUI 不兼容

**解决**：
在 `config/index.ts` 中确保：
```typescript
compiler: {
  type: 'webpack5',
  prebundle: { enable: false }  // 必须是 false！
}
```
然后删除 `dist/weapp` 文件夹，重新运行 `pnpm dev:weapp`

### 问题 5：小程序报 `Not allowed by CORS`

**原因**：后端 CORS 配置没有放行小程序请求

**解决**：
确保 `server/src/middleware/cors.ts` 中开发环境放行所有请求：
```typescript
if (process.env.NODE_ENV !== 'production') {
  callback(null, true);
}
```

### 问题 6：`pnpm` 命令不存在

**原因**：没有全局安装 pnpm

**解决**：
```bash
npm install -g pnpm
```

### 问题 7：Windows PowerShell 报 "无法加载文件，因为在此系统上禁止运行脚本"

**原因**：PowerShell 执行策略限制

**解决**：以管理员身份运行 PowerShell，执行：
```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

---

## ⚙️ 三个必须手动改的配置

即使用 AI 生成代码，也要**检查这三处**：

### 1. Prebundle 必须禁用
位置：`taro-app/config/index.ts`

```typescript
compiler: {
  type: 'webpack5',
  prebundle: { enable: false }  // ⚠️ 关键！
}
```

### 2. H5 开发代理
位置：`taro-app/config/dev.ts`

```typescript
h5: {
  devServer: {
    proxy: {
      '/api': {
        target: 'http://localhost:3000',
        changeOrigin: true
      }
    }
  }
}
```

### 3. CORS 开发模式
位置：`server/src/middleware/cors.ts`

```typescript
if (process.env.NODE_ENV !== 'production') {
  callback(null, true);  // 开发环境放行所有请求
}
```

---

## 🎯 适用场景

- ✅ 需要同时开发 **微信小程序 + H5 网页版** 的项目
- ✅ 全栈开发，前后端一体化管理
- ✅ 快速验证产品 MVP
- ✅ 学习 Taro + Node.js 全栈架构

---

## � 获取完整提示词

### 方式一：GitHub（推荐）

提示词文件托管在 GitHub，可以随时获取最新版本：

**🔗 https://github.com/你的用户名/taro-fullstack-prompt**

> 如果你会用 Git，直接 clone 下来即可；不会也没关系，点进去后点击绿色的「Code」按钮，选择「Download ZIP」下载。

### 方式二：百度网盘

如果你无法访问 GitHub，我在**评论区置顶**放了百度网盘链接，直接下载即可。

---

### 怎么用？

1. 下载 `taro-monorepo-scaffold-prompt-v2.md` 文件
2. 复制文件里的全部内容
3. 粘贴给 **Claude / GPT-4 / Gemini** 等 AI
4. AI 会生成完整的项目代码
5. 按照本文的「如何运行项目」章节操作即可

---

## 💬 写在最后



## 🔗 相关资源

| 资源 | 链接 |
|------|------|
| **GitHub 仓库** | https://github.com/Luchen-0420/fullstack-prompt.git |
| **百度网盘** | 见评论区置顶 |
| **Taro 官方文档** | https://taro-docs.jd.com |
| **NutUI React** | https://nutui.jd.com/react-taro |

---

## 🔮 下期预告：uni-app 版本即将上线

很多小伙伴在后台留言想要 **uni-app 版本**的脚手架提示词。

好消息！**下一个版本我会推出 uni-app + Node.js 全栈脚手架 Prompt**，敬请期待！

| 技术栈 | 说明 |
|--------|------|
| **前端框架** | Vue 3 + TypeScript |
| **跨端框架** | uni-app |
| **UI 组件库** | uv-ui / uView Plus |
| **后端** | 与现有版本一致（Express + PostgreSQL） |

如果你对 uni-app 版本感兴趣，请在评论区留言告诉我，你最希望看到哪些功能模块！


---

## 🙏 特别感谢

感谢**其来大哥**的项目启发，让我有了制作这份提示词的灵感。他在 AI 领域有很多干货分享，强烈推荐关注他的公众号：

【芝士AI吃鱼】


---

有任何问题，欢迎留言交流，我会尽力解答 ✨
