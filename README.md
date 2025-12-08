```
下面是 **“已完整包裹为 Markdown 代码块、可直接复制即得到原始 Markdown 文件内容”** 的版本。

你只需要复制下面这整个代码块 👉 就能得到“原样显示、不被渲染”的 Markdown 文件。

---

# ✅ 完整 Markdown（已转义为 Markdown 代码块）

````markdown
# AI 时代，小白也能 10 分钟搭建全栈项目｜Taro 跨端脚手架 Prompt 分享

> 📢 **AI 提示词，让零基础小白也能生成专业级的 Taro + Node.js 全栈项目，让你成为全栈工程师的路上踏出第一步。**

---

## 🎯 这篇文章写给谁？

也许你是：
- 👔 想做副业的上班族，有想法但不会写代码
- 🚀 想验证 MVP 的创业者，不想花钱请外包
- 🎓 想学全栈的学生，不知道从哪开始
- 🔄 想从其他行业转行的朋友，觉得编程门槛太高

**我相信在 AI 时代，技术不应该成为实现想法的门槛。**

这份提示词就是为了帮助你——只要你有想法，AI + 这份提示词，就能帮你迈出全栈开发的第一步。

---

### � 我的初衷

我不是科班出身的程序员，但我相信在 AI 时代，**技术不应该成为实现想法的门槛**。

很多人有好的产品想法，却因为不会全栈开发而放弃。我希望这份提示词能成为一座桥梁，让更多人迈出第一步。

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
````

* **验证安装**：`pnpm -v`

### 3. Git（推荐）

* **作用**：代码版本管理
* **下载地址**：[https://git-scm.com/](https://git-scm.com/)
* **验证安装**：`git --version`

### 4. VS Code（推荐）

* **作用**：代码编辑器
* **下载地址**：[https://code.visualstudio.com/](https://code.visualstudio.com/)
* **推荐插件**：

  * ES7+ React/Redux/React-Native snippets
  * Prettier - Code formatter
  * TypeScript Vue Plugin (如果你也写 Vue)

### 5. 微信开发者工具（开发小程序必装）

* **作用**：预览和调试微信小程序
* **下载地址**：[https://developers.weixin.qq.com/miniprogram/dev/devtools/download.html](https://developers.weixin.qq.com/miniprogram/dev/devtools/download.html)

### 6. PostgreSQL（后端数据库）

* **作用**：存储用户数据
* **下载地址**：[https://www.postgresql.org/download/](https://www.postgresql.org/download/)
* **或者用 Docker**：`docker run -d -p 5432:5432 -e POSTGRES_PASSWORD=123456 postgres:14`

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

### 如果你是 Taro 新手

| 你的困惑      | 这份提示词怎么帮你                |
| --------- | ------------------------ |
| 不知道项目怎么组织 | 直接给你 Monorepo 最佳实践结构     |
| 不懂配置怎么写   | 所有 config 文件都是完整可用的      |
| 担心代码不规范   | 遵循分层架构 + TypeScript 严格模式 |
| 怕踩坑浪费时间   | 已经帮你填好了常见的坑              |

**核心价值**：**从第一天就按最佳实践写代码**，而不是先写错再改。

---

### 如果你是专业开发者

| 你的诉求     | 这份提示词怎么帮你             |
| -------- | --------------------- |
| 快速启动新项目  | 10 分钟生成完整脚手架，直接开始业务开发 |
| 不想重复造轮子  | 用户认证、API 封装、状态管理都写好了  |
| 保持技术选型一致 | 固定版本号，避免依赖冲突          |
| 需要可定制的模板 | 提示词结构清晰，随时按需修改        |

**核心价值**：**把重复的架构工作交给 AI**，你专注业务逻辑。

---

## 提示词设计的四个原则

这份提示词不是简单地"让 AI 帮我写代码"，而是遵循了四个设计原则：

### 1. 完整性约束

```
所有代码必须完整，不使用 `// ... 其他代码` 省略
```

普通提示词生成的代码经常是"示意性"的，这条约束让 AI 输出**可直接运行**的代码。

### 2. 版本锁定

```
Taro 3.6.32、React 18、TypeScript 5.x
```

明确版本号避免"我这能跑你那不能跑"的问题。

### 3. 多端兼容配置

```typescript
compiler: {
  type: 'webpack5',
  prebundle: { enable: false }  // 小程序必须
}
```

H5 和小程序的配置差异已经处理好了。

### 4. 分层架构模板

```
Routes → Controllers → Services → Models
```

后端代码遵循单一职责原则，新手也能写出可维护的代码。

---

## 🚀 快速体验

### 方式一：让 AI 帮你生成

把下面的提示词发给 **Claude / GPT-4 / Gemini**：

```
【粘贴 taro-monorepo-scaffold-prompt-v2.md 完整内容】
```

AI 会生成完整的项目代码，你只需要：

1. 创建对应目录和文件
2. 粘贴代码
3. `pnpm install && pnpm dev`

### 方式二：手动搭建（带命令）

```bash
# 1. 创建 Monorepo
mkdir my-app && cd my-app
pnpm init
echo "packages:\n  - 'packages/*'" > pnpm-workspace.yaml

# 2. 创建 Taro 前端
cd packages
npx @tarojs/cli@3.6.32 init taro-app
cd taro-app && pnpm add @nutui/nutui-react-taro zustand

# 3. 创建 Express 后端
cd ..
mkdir server && cd server
pnpm init
pnpm add express cors pg bcryptjs jsonwebtoken zod pino dotenv
pnpm add -D typescript tsx nodemon @types/node @types/express

# 4. 安装依赖
cd ../..
pnpm install
```

---

## 🏃 如何运行项目

项目创建好后，需要同时启动**后端**和**前端**。

### Step 1: 启动后端服务

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

### Step 2: 启动 H5 网页版

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

打开浏览器访问 **[http://localhost:10086](http://localhost:10086)** 即可看到页面。

### Step 3: 启动微信小程序

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

> 💡 **小白必知：热更新**
>
> 使用 `pnpm dev:weapp` 启动后，修改代码会**自动重新编译**，微信开发者工具也会**自动刷新**，不需要每次手动删除 dist 文件夹！
>
> **只有修改了 `config/index.ts` 配置文件或 `package.json` 依赖时**，才需要停止命令、删除 `dist/weapp`、重新运行 `dev:weapp`。

### 常用命令速查

| 命令                 | 说明         |
| ------------------ | ---------- |
| `pnpm dev:h5`      | 启动 H5 网页版  |
| `pnpm dev:weapp`   | 编译微信小程序    |
| `pnpm build:h5`    | 构建 H5 生产版本 |
| `pnpm build:weapp` | 构建小程序生产版本  |

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

# 范例：杀掉进程
taskkill /PID 进程号 /F
```

或者修改 `.env` 中的 `PORT=`。

---

## ⚙️ 三个必须手动改的配置

即使用 AI 生成代码，也要**检查这三处**：

### 1. Prebundle 必须禁用

`taro-app/config/index.ts`：

```typescript
compiler: {
  type: 'webpack5',
  prebundle: { enable: false }  // ⚠️ 必须！
}
```

### 2. H5 代理

`taro-app/config/dev.ts`：

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

### 3. CORS 开发模式放行全部请求

`server/src/middleware/cors.ts`：

```typescript
if (process.env.NODE_ENV !== 'production') {
  callback(null, true);
}
```

---

## 📊 技术栈一览

| 层级         | 技术选型                  |
| ---------- | --------------------- |
| **跨端框架**   | Taro 3.6.32           |
| **前端框架**   | React 18 + TypeScript |
| **UI 组件库** | NutUI React Taro      |
| **状态管理**   | Zustand               |
| **后端框架**   | Express               |
| **数据库**    | PostgreSQL            |
| **运行时**    | Node.js 18+           |
| **包管理**    | pnpm workspace        |

---

## 获取提示词

方式一：GitHub（推荐）
方式二：百度网盘（评论区置顶）

---

## 💬 写在最后

有任何问题，欢迎留言，我会尽力回答！

---

```

---

如果你后面还要「把另外一份提示词也转成 Markdown 代码块格式」，告诉我即可，我可以 *一键转换*、修正格式、保持可复制性。
```

```
