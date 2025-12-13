你是一名资深全栈架构师。请为我生成一个**完整可运行**的 Monorepo 全栈项目脚手架，严格遵循工程最佳实践。

## 核心要求
- 所有代码必须完整、可复制、可直接运行
- 使用 **Taro 3.6.x** 实现一套代码同时支持 Web（H5）和微信小程序
- 后端必须采用分层架构：Routes → Controllers → Services → Models
- 前后端通过 API 通信，H5 端使用代理，小程序直接请求
- 使用 pnpm workspace 管理 Monorepo
- **H5 端使用标准 CSS 响应式设计，禁用 pxtransform**

---

## [CRITICAL] 强制技术规范（禁止更改）

> **以下技术选型为强制要求，AI 不得擅自替换或更改。如有疑问必须先询问用户。**

| 组件 | 强制使用 | 禁止替换为 |
|------|----------|------------|
| 数据库 | **PostgreSQL 14+** | SQLite, MySQL, MongoDB |
| 数据库驱动 | **pg (node-postgres)** | better-sqlite3, mysql2, prisma |
| 前端框架 | **Taro 3.6.32 + React 18** | uni-app, React Native |
| 状态管理 | **Zustand 4.x** | Redux, MobX, Recoil |
| 后端框架 | **Express 4.x + TypeScript** | Koa, Fastify, NestJS |
| 运行工具 | **tsx** | ts-node, nodemon with tsc |

### AI 必读检查点

在开始任何代码生成之前，你**必须**完整阅读本文档并确认以下关键项：

1. [ ] 数据库类型已确认（PostgreSQL，非 SQLite）
2. [ ] 前端框架版本已确认（Taro 3.6.32）
3. [ ] 后端分层架构已理解（Routes → Controllers → Services → Models）
4. [ ] H5 样式策略已理解（禁用 pxtransform，使用原生 CSS）
5. [ ] JWT 密钥安全已理解（README 必须包含密钥生成命令和安全警告）

**如果本文档被截断或无法完整阅读，必须先向用户索取完整版本，禁止自行假设。**

---

### [WARNING] 严格禁止事项（必须遵守）
> **以下行为视为不合格输出，必须严格禁止：**

1. **禁止使用任何占位符代码**
   - [X] 禁止：`showToast('功能开发中')` 、`// TODO: 实现此功能`、`console.log('暂未实现')`
   - [X] 禁止：注释中包含 `simplified`、`placeholder`、`mock`、`待实现`、`开发中` 等字样
   - [OK] 要求：所有按钮、表单提交等用户交互必须有完整的业务逻辑实现

2. **禁止省略任何代码**
   - [X] 禁止：`// ... 其他代码`、`// 省略`、`// 类似实现`
   - [OK] 要求：每个文件必须是完整的、可直接复制使用的

3. **禁止功能不对称**
   - [X] 禁止：后端有注册 API，但前端注册按钮不调用它
   - [OK] 要求：定义的每个 API 端点必须在前端有对应的完整调用逻辑

4. **禁止样式只考虑单端**
   - [X] 禁止：样式只在 H5 正常显示，小程序端错位或不可用
   - [OK] 要求：每个页面必须在 H5 和微信小程序两端都正常显示

5. **禁止擅自更改技术选型**
   - [X] 禁止：用户指定 PostgreSQL，AI 自行改为 SQLite 或其他数据库
   - [X] 禁止：用户指定 Zustand，AI 自行改为 Redux 或其他状态管理
   - [X] 禁止：在文档被截断时自行假设技术栈
   - [OK] 要求：如有任何不确定，必须先询问用户确认

6. **禁止遗漏任何必需文件**
   - [X] 禁止：只生成代码文件，遗漏配置文件（如 `.env.example`、`tsconfig.json`）
   - [X] 禁止：只生成后端或前端，遗漏另一端
   - [OK] 要求：完成后必须对照下方"必须生成的文件清单"逐项确认

---

## [CRITICAL] 必须生成的文件清单（完成时逐项确认）

> **AI 在完成代码生成后，必须逐项确认以下所有文件均已生成。如有遗漏，必须补充。**

### 根目录
- [ ] `pnpm-workspace.yaml`
- [ ] `package.json`（**必须包含 `pnpm dev` 一键启动命令 + `concurrently` 依赖**）
- [ ] `tsconfig.base.json`
- [ ] `README.md`（必须包含 JWT 密钥生成说明 + 一键启动命令说明）
- [ ] `.gitignore`

### 后端 (packages/server)
- [ ] `package.json`
- [ ] `tsconfig.json`
- [ ] `.env.example`（包含数据库、JWT、CORS 配置）
- [ ] `src/index.ts`
- [ ] `src/config/database.ts`
- [ ] `src/models/user.model.ts`
- [ ] `src/services/user.service.ts`
- [ ] `src/controllers/user.controller.ts`
- [ ] `src/routes/index.ts`
- [ ] `src/routes/user.routes.ts`
- [ ] `src/middlewares/auth.middleware.ts`
- [ ] `src/utils/response.ts`

### 前端 (packages/client)
- [ ] `package.json`
- [ ] `tsconfig.json`
- [ ] `project.config.json`
- [ ] `babel.config.json`
- [ ] `config/index.ts`
- [ ] `config/dev.ts`
- [ ] `config/prod.ts`
- [ ] `src/app.tsx`（**注意：必须使用 .tsx 扩展名，因为包含 JSX**）
- [ ] `src/app.config.ts`
- [ ] `src/app.css`
- [ ] `src/store/userStore.ts`
- [ ] `src/api/request.ts`
- [ ] `src/api/user.ts`
- [ ] `src/pages/index/index.tsx` + `index.config.ts` + `index.css`
- [ ] `src/pages/login/index.tsx` + `index.config.ts` + `index.css`
- [ ] `src/pages/register/index.tsx` + `index.config.ts` + `index.css`

## 技术栈规范

### 1. Monorepo 结构
- **工具**：pnpm workspace
- **结构**：
  ```
  /
  ├── packages/taro-app   # Taro 跨端应用（Web + 小程序）
  ├── packages/server     # 后端服务
  ├── package.json        # workspace root
  └── pnpm-workspace.yaml
  ```

#### 根目录 package.json（一键启动命令）

> [!IMPORTANT]
> **必须包含一键启动命令**：根目录 `package.json` 必须包含 `pnpm dev` 命令，使用 `concurrently` 同时启动前后端。这是用户体验的关键，禁止遗漏！

```json
{
  "name": "my-fullstack-app",
  "version": "1.0.0",
  "private": true,
  "description": "Monorepo full-stack application with Taro frontend and Express backend",
  "scripts": {
    "dev": "concurrently \"pnpm --filter server dev\" \"pnpm --filter taro-app dev:h5\"",
    "dev:weapp": "concurrently \"pnpm --filter server dev\" \"pnpm --filter taro-app dev:weapp\"",
    "build:h5": "pnpm --filter taro-app build:h5",
    "build:weapp": "pnpm --filter taro-app build:weapp",
    "server": "pnpm --filter server start",
    "server:dev": "pnpm --filter server dev",
    "db:init": "psql -d my_app_db -f packages/server/src/db/schema.sql"
  },
  "devDependencies": {
    "concurrently": "^8.2.2"
  },
  "engines": {
    "node": ">=18.0.0",
    "pnpm": ">=8.0.0"
  },
  "packageManager": "pnpm@8.15.0"
}
```

**常用命令说明**：
| 命令 | 说明 |
|------|------|
| `pnpm dev` | **一键启动后端 + H5 网页版（推荐）** |
| `pnpm dev:weapp` | 一键启动后端 + 微信小程序编译 |
| `pnpm build:h5` | 构建 H5 生产版本 |
| `pnpm build:weapp` | 构建小程序生产版本 |
| `pnpm db:init` | 初始化数据库表结构 |

#### pnpm-workspace.yaml
```yaml
packages:
  - 'packages/*'
```

---

### 2. 后端技术栈 (packages/server)

#### 核心技术
| 技术 | 版本/说明 |
|------|----------|
| **运行时** | Node.js 18+ + TypeScript 5.x |
| **框架** | Express 4.x |
| **执行工具** | tsx（无需编译直接运行 TS） |
| **数据库** | PostgreSQL 14+ |
| **数据库驱动** | pg (node-postgres) |
| **环境变量** | dotenv |
| **日志** | pino + pino-pretty |
| **验证** | zod |
| **密码加密** | bcryptjs |
| **JWT** | jsonwebtoken |

#### 分层架构目录结构

```
packages/server/
├── src/
│   ├── index.ts              # 入口文件
│   ├── app.ts                # Express 应用配置
│   ├── routes/
│   │   ├── index.ts
│   │   └── user.routes.ts
│   ├── controllers/
│   │   └── user.controller.ts
│   ├── services/
│   │   └── user.service.ts
│   ├── models/
│   │   └── user.model.ts
│   ├── db/
│   │   ├── client.ts
│   │   └── schema.sql
│   ├── middleware/
│   │   ├── error.ts
│   │   ├── cors.ts
│   │   ├── auth.ts
│   │   └── validate.ts
│   └── utils/
│       ├── logger.ts
│       ├── response.ts
│       └── jwt.ts
├── package.json
├── tsconfig.json
├── .env.example
└── nodemon.json
```

#### 业务模块

**user**（用户管理）：
- POST `/api/users/register` - 用户注册
- POST `/api/users/login` - 用户登录
- GET `/api/users/profile` - 获取当前用户信息（需认证）
- PUT `/api/users/profile` - 更新用户信息（需认证）
- PUT `/api/users/password` - 修改密码（需认证）

#### 配置文件

**.env.example**：
```env
# Server
PORT=3000
NODE_ENV=development

# Database
DB_HOST=localhost
DB_PORT=5432
DB_NAME=my_app_db
DB_USER=postgres
DB_PASSWORD=password

# JWT
JWT_SECRET=your-super-secret-key-change-in-production
JWT_EXPIRES_IN=7d

# CORS
CORS_ORIGIN=http://localhost:10086
```

> [!CAUTION]
> **JWT 密钥安全要求**：
> - 生产环境**必须**使用随机生成的强密钥，禁止使用默认值
> - 密钥生成命令：`node -e "console.log(require('crypto').randomBytes(64).toString('hex'))"`
> - 或使用：`openssl rand -hex 64`
> - 密钥长度建议 64 字节以上
> - README 文档中必须包含此安全说明

##### 数据库连接池（使用分离变量）
```typescript
export const pool = new Pool({
  host: process.env.DB_HOST || 'localhost',
  port: parseInt(process.env.DB_PORT || '5432', 10),
  database: process.env.DB_NAME || 'my_app_db',
  user: process.env.DB_USER || 'postgres',
  password: process.env.DB_PASSWORD || 'password',
  max: 20,
  idleTimeoutMillis: 30000,
  connectionTimeoutMillis: 2000,
});
```

##### CORS 中间件（开发环境允许所有来源）
> [WARNING] **重要**：小程序端请求的 origin 与 H5 不同，开发环境需允许所有来源，否则会报 "Not allowed by CORS" 错误。

```typescript
// src/middleware/cors.ts
import cors from 'cors';

const isDevelopment = process.env.NODE_ENV !== 'production';

const corsOptions: cors.CorsOptions = {
  origin: (origin, callback) => {
    // 开发环境允许所有来源（方便小程序和 H5 调试）
    if (isDevelopment) {
      callback(null, true);
      return;
    }
    
    // 生产环境：允许无 origin 的请求（小程序、curl）
    if (!origin) {
      callback(null, true);
      return;
    }
    
    const allowedOrigins = (process.env.CORS_ORIGIN || '').split(',').map(o => o.trim());
    if (allowedOrigins.includes(origin) || allowedOrigins.includes('*')) {
      callback(null, true);
    } else {
      callback(new Error('Not allowed by CORS'));
    }
  },
  credentials: true,
  methods: ['GET', 'POST', 'PUT', 'DELETE', 'PATCH', 'OPTIONS'],
  allowedHeaders: ['Content-Type', 'Authorization'],
};

export const corsMiddleware = cors(corsOptions);
```

---

### 3. 前端技术栈 (packages/taro-app)

#### 核心技术
| 技术 | 版本/说明 |
|------|----------|
| **框架** | Taro 3.6.32 + React 18 + TypeScript |
| **UI 组件** | @nutui/nutui-react-taro@^2.3.0（注意：不要显式安装 @nutui/icons-react-taro，它会作为内部依赖自动安装；**Button 组件需使用 Taro 原生组件，见下方注意事项**） |
| **状态管理** | Zustand 4.x |
| **HTTP 请求** | Taro.request 封装 |
| **CSS 预处理** | Sass |
| **编译目标** | H5 (Web) + 微信小程序 (weapp) |

#### 必须包含的文件

**配置文件**：
- `package.json` - 依赖和脚本
- `tsconfig.json` - TypeScript 配置
- `babel.config.js` - Babel 配置（使用 babel-preset-taro）
- `.env.development` - 开发环境变量
- `.env.production` - 生产环境变量
- `project.config.json` - 微信小程序项目配置

**Taro 配置**：
- `config/index.ts` - Taro 主配置文件
- `config/dev.ts` - 开发环境配置（**必须包含 H5 proxy 配置**）
- `config/prod.ts` - 生产环境配置

**应用代码**：
- `src/app.config.ts` - 应用配置（页面路由，**登录页为默认启动页，无 tabBar**）
- `src/app.tsx` - 应用入口（**必须使用 .tsx 扩展名**）
- `src/app.scss` - 全局样式（**响应式设计，使用 CSS 变量和媒体查询**）
- `src/index.html` - H5 入口模板（**无移动端缩放脚本**）

**页面**：
- `src/pages/login/index.tsx` - 登录页（**默认启动页**）
- `src/pages/login/index.scss`
- `src/pages/index/index.tsx` - 首页
- `src/pages/index/index.scss`
- `src/pages/profile/index.tsx` - 个人中心页
- `src/pages/profile/index.scss`
- `src/pages/change-password/index.tsx` - 修改密码页
- `src/pages/change-password/index.scss`

**API 层**：
- `src/api/config.ts` - API 配置（根据 TARO_ENV 设置不同 baseURL）
- `src/api/http.ts` - Taro.request 封装（含请求/响应拦截器）
- `src/api/modules/user.ts` - 用户相关 API
- `src/api/index.ts` - API 模块统一导出

**公共模块**：
- `src/components/Loading/index.tsx` - 加载组件
- `src/components/EmptyState/index.tsx` - 空状态组件
- `src/utils/storage.ts` - 存储工具
- `src/utils/toast.ts` - 提示工具
- `src/store/user.ts` - 用户状态（Zustand）
- `src/store/index.ts` - Store 统一导出
- `src/types/index.ts` - 全局类型定义

#### 关键配置要求

##### package.json 关键配置
```json
{
  "browserslist": [
    "Chrome >= 67",
    "Safari >= 12",
    "Firefox >= 68",
    "Edge >= 79",
    "iOS >= 12",
    "Android >= 67"
  ],
  "devDependencies": {
    "@babel/core": "^7.23.2",
    "@pmmmwh/react-refresh-webpack-plugin": "^0.5.11",
    "@tarojs/cli": "3.6.32",
    "@tarojs/taro-loader": "3.6.32",
    "@tarojs/webpack5-runner": "3.6.32",
    "@types/react": "^18.2.37",
    "@types/webpack-env": "^1.18.3",
    "babel-preset-taro": "3.6.32",
    "postcss": "^8.4.31",
    "react-refresh": "^0.14.0",
    "sass": "^1.69.5",
    "typescript": "^5.2.2",
    "webpack": "^5.89.0"
  }
}
```

##### H5 开发模式 Proxy 配置（config/dev.ts）
```typescript
export default {
  h5: {
    devServer: {
      port: 10086,
      host: '0.0.0.0',
      proxy: {
        '/api': {
          target: 'http://localhost:3000',
          changeOrigin: true,
          pathRewrite: { '^/api': '/api' }
        }
      }
    }
  }
};
```

##### 编译器配置（config/index.ts - 禁用 prebundle）
> [WARNING] **重要**：Taro 3.6+ 必须在 `compiler` 对象中禁用 prebundle，否则小程序端会报 `module 'prebundle/xxx.wxss.js' is not defined` 错误。

```typescript
compiler: {
  type: 'webpack5',
  prebundle: {
    enable: false  // 禁用 prebundle，解决 NutUI icons CSS 模块加载错误
  }
},
```

##### H5 配置（config/index.ts 关键部分）
```typescript
h5: {
  publicPath: '/',
  staticDirectory: 'static',
  postcss: {
    autoprefixer: {
      enable: true,
      config: {}
    },
    // 禁用 H5 的 pxtransform，使用原生 CSS 像素实现响应式
    pxtransform: {
      enable: false
    },
    cssModules: {
      enable: false,
      config: {
        namingPattern: 'module',
        generateScopedName: '[name]__[local]___[hash:base64:5]'
      }
    }
  },
  esnextModules: ['@nutui/nutui-react-taro'],
  // 忽略 Taro 内部模块的警告
  webpackChain(chain) {
    chain.merge({
      ignoreWarnings: [
        /You don't need `webpackExports`/,
        /The generated code contains 'async\/await'/,
        /target environment does not appear to support/
      ]
    });
  }
}
```

##### index.html（无移动端缩放脚本）
```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
  <meta name="description" content="Taro Cross-Platform Application">
  <title>My App</title>
  <style>
    /* Note: * selector is fine in H5 index.html, but avoid in WXSS/SCSS files */
    html, body, div, p, span, input, button { box-sizing: border-box; }
    html, body { margin: 0; padding: 0; width: 100%; min-height: 100%; font-size: 16px; }
    #app { width: 100%; min-height: 100vh; }
  </style>
</head>
<body>
  <div id="app"></div>
</body>
</html>
```

##### app.config.ts（登录页为默认启动页，无 tabBar）
```typescript
export default defineAppConfig({
  pages: [
    'pages/login/index',      // 登录页设为默认启动页
    'pages/index/index',
    'pages/profile/index',
    'pages/change-password/index'
  ],
  window: {
    backgroundTextStyle: 'light',
    navigationBarBackgroundColor: '#fff',
    navigationBarTitleText: 'My App',
    navigationBarTextStyle: 'black'
  }
});
```

##### project.config.json（微信小程序项目配置）
> [WARNING] **重要**：必须指定 `libVersion` 调试基础库版本为 `3.11.3`，以获得更好的组件兼容性。

```json
{
  "miniprogramRoot": "dist/weapp/",
  "projectname": "my-app",
  "appid": "your-weapp-appid",
  "compileType": "miniprogram",
  "libVersion": "3.11.3",
  "setting": {
    "es6": false,
    "postcss": false,
    "minified": true,
    "enhance": true
  }
}
```

##### 响应式全局样式（app.scss）
```scss
/* 颜色和间距变量 */
:root {
  --primary-color: #fa2c19;
  --text-color: #333333;
  --text-secondary: #666666;
  --bg-color: #f5f5f5;
  --white: #ffffff;
  --spacing-md: 16px;
  --spacing-lg: 24px;
  --font-size-base: 16px;
  --radius-lg: 12px;
}

/* 基础样式 */
page {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
  font-size: var(--font-size-base);
  color: var(--text-color);
  background: var(--bg-color);
}

.container {
  min-height: 100vh;
  padding: var(--spacing-md);
  width: 100%;
}

.card {
  background: var(--white);
  border-radius: var(--radius-lg);
  padding: var(--spacing-md);
  margin-bottom: var(--spacing-md);
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05);
}

/* 平板端 (768px+) */
@media screen and (min-width: 768px) {
  .container { max-width: 720px; margin: 0 auto; padding: var(--spacing-lg); }
}

/* 桌面端 (1024px+) */
@media screen and (min-width: 1024px) {
  .container { max-width: 960px; }
  .card:hover { box-shadow: 0 6px 24px rgba(0, 0, 0, 0.12); }
}

/* 大屏 (1280px+) */
@media screen and (min-width: 1280px) {
  .container { max-width: 1200px; }
}
```

---

### 4. 小程序端样式适配规范

> [WARNING] **重要**：微信小程序与 H5 浏览器的 CSS 渲染存在差异，必须针对性处理。

#### 常见问题与解决方案

| 问题 | H5 表现 | 小程序表现 | 解决方案 |
|------|--------|-----------|----------|
| `*` 通配符选择器 | 正常 | **编译报错** | 使用 `view, text, image, button, input` 枚举替代 |
| `::before`, `::after` | 正常 | **不支持** | 使用实际元素或图片替代 |
| `100vh` 高度 | 正常 | 可能不包含导航栏高度 | 使用 `min-height: 100%` 或 Taro API 获取屏幕高度 |
| Flexbox 居中 | 正常 | 可能失效 | 确保父容器有明确高度 |
| CSS 变量 | 正常 | 需在 `page` 选择器中定义 | 在 `app.scss` 的 `page` 中定义变量 |
| `gap` 属性 | 正常 | 部分版本不支持 | 使用 `margin` 替代 |

#### 页面容器标准写法
```scss
// 小程序兼容的全屏居中布局
.page-container {
    min-height: 100%;  // 不要用 100vh
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    box-sizing: border-box;
}

// 确保 page 有高度（在 app.scss 中）
page {
    height: 100%;
    width: 100%;
}
```

#### 登录页样式示例（多端兼容）
```scss
.login-page {
    min-height: 100%;  // 小程序兼容
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    background: linear-gradient(135deg, #fff5f3 0%, #ffffff 50%, #fff9f8 100%);
    padding: 16px;
    box-sizing: border-box;
}

.login-container {
    width: 100%;
    max-width: 400px;
    background: #ffffff;
    border-radius: 16px;
    padding: 32px 24px;
    box-shadow: 0 10px 40px rgba(250, 44, 25, 0.08);
    box-sizing: border-box;
}

/* 小程序端输入框需要额外处理 */
.form-input {
    width: 100%;
    height: 48px;
    padding: 0 16px;
    border: 1px solid #e8e8e8;
    border-radius: 8px;
    font-size: 16px;
    box-sizing: border-box;
    background: #ffffff;
}
```

#### app.scss 必须包含的小程序兼容样式
```scss
/* 确保 page 容器有高度（小程序必需） */
page {
    height: 100%;
    width: 100%;
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
    font-size: 16px;
    color: #333333;
    background: #f5f5f5;
}

/* 小程序兼容的 box-sizing（禁止使用 * 通配符，会报编译错误） */
view, text, image, button, input, navigator {
    box-sizing: border-box;
}
```

##### 多端 API baseURL 处理（src/api/config.ts）
```typescript
const getBaseURL = (): string => {
  const env = process.env.TARO_ENV;
  
  if (env === 'h5') {
    return process.env.NODE_ENV === 'development' ? '/api' : 'https://your-domain.com/api';
  }
  
  return process.env.NODE_ENV === 'development' 
    ? 'http://localhost:3000/api'
    : 'https://your-domain.com/api';
};

export const API_BASE_URL = getBaseURL();
```

---

## 关键约束和最佳实践

### 代码规范
- 所有 TypeScript 必须开启 `strict` 模式
- 统一使用 async/await
- 错误处理必须完整（try-catch + 统一错误中间件）
- 前端组件使用函数式组件 + Hooks

### [CRITICAL] TypeScript 文件扩展名规范
> **这是强制规范，违反将导致编译错误！**

| 文件内容 | 必须使用的扩展名 | 禁止使用 |
|----------|-----------------|----------|
| 包含 JSX 语法（如 `<View>`, `<Text>`, `<>`, `<Component />`） | **`.tsx`** | `.ts` |
| 纯 TypeScript（无 JSX） | **`.ts`** | `.tsx`（可用但不推荐） |

**常见错误示例**：
```typescript
// ❌ 错误：app.ts 文件中使用了 JSX
// 文件名: app.ts
function App({ children }) {
  return <>{children}</>; // 报错: Type parameter list cannot be empty
}

// ✅ 正确：使用 app.tsx 扩展名
// 文件名: app.tsx
function App({ children }) {
  return <>{children}</>; // 正常编译
}
```

**AI 自检清单**：
- [ ] 所有包含 `<` 和 `>` 作为 JSX 标签的文件使用 `.tsx` 扩展名
- [ ] `app.tsx`（入口文件）使用 `.tsx` 而非 `.ts`
- [ ] 页面组件文件使用 `.tsx`（如 `pages/login/index.tsx`）
- [ ] 纯工具函数文件使用 `.ts`（如 `utils/storage.ts`）

### TSX 泛型语法
- 在 `.tsx` 文件中，单个泛型参数的箭头函数需要添加尾随逗号：
  ```typescript
  // [X] 错误
  const fn = <T>(arg: T) => arg;
  
  // [OK] 正确
  const fn = <T,>(arg: T) => arg;
  ```

### H5 响应式设计
- 禁用 pxtransform，使用原生 CSS 像素（px）
- 使用 CSS 变量实现主题一致性
- 使用媒体查询断点：768px（平板）、1024px（桌面）、1280px（大屏）
- 页面样式文件包含响应式媒体查询

### API 设计
- RESTful 风格
- 统一响应格式：`{ code: number, data: T | null, message: string }`
- HTTP 状态码：200/201/400/401/403/404/500

### 多端兼容性
- 使用 `process.env.TARO_ENV` 判断当前运行环境
- 避免使用 Web 独有 API（如 window、document）
- 小程序端使用 rpx，H5 端使用 px + 媒体查询

### 路由跳转注意事项
> [WARNING] **重要**：由于本脚手架配置无 tabBar，**禁止使用 `Taro.switchTab`**，否则小程序端会报错 `switchTab:fail can not switch to no-tabBar page`。

**路由 API 使用规范**：
| 场景 | 使用的 API |
|------|-----------|
| 普通页面跳转（可返回） | `Taro.navigateTo({ url: '/pages/xxx/index' })` |
| 登录成功后跳转首页（不可返回） | `Taro.redirectTo({ url: '/pages/index/index' })` |
| 返回上一页 | `Taro.navigateBack()` |

### Button 组件注意事项
> [WARNING] **重要**：NutUI 的 Button 组件在小程序端存在兼容性问题（`block` 属性无效、文字不显示等），**必须使用 Taro 原生 Button 组件**。

**解决方案**：使用 Taro 原生 Button 组件（`@tarojs/components`），样式手动定义：
```tsx
import { Button } from '@tarojs/components';
// 不要使用 block 属性，通过 CSS width: 100% 实现全宽
<Button className="submit-btn" type="primary" loading={loading} onClick={handleSubmit}>登录</Button>
```

**按钮样式示例**（SCSS）：
```scss
.submit-btn {
    width: 100% !important;
    margin-top: 24px;
    height: 48px !important;
    line-height: 48px !important;
    border-radius: 24px !important;
    font-size: 16px !important;
    background: linear-gradient(135deg, #fa2c19 0%, #ff6b35 100%) !important;
    color: #fff !important;
    border: none !important;
}
```

### Cell 组件注意事项
> [WARNING] **重要**：NutUI 的 Cell 组件在小程序端可能存在渲染问题（内容不显示、样式丢失等），**建议使用自定义 View 组件替代**。

**问题表现**：在微信小程序中，Cell 组件的 `title` 和 `description` 可能不显示，或样式与 H5 端不一致。

**解决方案**：使用 Taro 原生组件（`View`、`Text`）构建自定义菜单项：
```tsx
import { View, Text } from '@tarojs/components';

// 菜单项数据
const menuItems = [
    { icon: '用户', title: '个人中心', description: '查看和编辑个人信息', onClick: handleProfile },
    { icon: '设置', title: '系统设置', description: '应用偏好设置', onClick: handleSettings },
    { icon: '帮助', title: '帮助中心', description: '常见问题解答', onClick: handleHelp },
];

// 渲染菜单列表
<View className="menu-list">
    {menuItems.map((item, index) => (
        <View key={index} className="menu-item" onClick={item.onClick} hoverClass="menu-item-hover">
            <View className="menu-item-icon">{item.icon}</View>
            <View className="menu-item-content">
                <Text className="menu-item-title">{item.title}</Text>
                <Text className="menu-item-desc">{item.description}</Text>
            </View>
            <Text className="menu-item-arrow">›</Text>
        </View>
    ))}
</View>
```

**菜单项样式示例**（SCSS）：
```scss
.menu-list {
    background: var(--white);
    border-radius: 12px;
    overflow: hidden;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05);
}

.menu-item {
    display: flex;
    align-items: center;
    padding: 16px;
    background: var(--white);
    border-bottom: 1px solid var(--border-color);

    &:last-child { border-bottom: none; }
}

.menu-item-hover {
    background-color: #f5f5f5 !important;
}

.menu-item-icon {
    width: 40px;
    height: 40px;
    border-radius: 10px;
    background: linear-gradient(135deg, rgba(250, 44, 25, 0.1) 0%, rgba(255, 107, 53, 0.1) 100%);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 20px;
    margin-right: 12px;
}

.menu-item-content {
    flex: 1;
    display: flex;
    flex-direction: column;
}

.menu-item-title {
    font-size: 15px;
    font-weight: 500;
    color: var(--text-color);
    margin-bottom: 4px;
}

.menu-item-desc {
    font-size: 12px;
    color: var(--text-secondary);
}

.menu-item-arrow {
    font-size: 20px;
    color: var(--text-light);
    margin-left: 8px;
}
```

### 安全性
- 密码使用 bcryptjs hash 存储
- JWT 密钥使用环境变量
- 使用参数化查询防止 SQL 注入
- CORS **开发环境允许所有来源**（方便小程序和 H5 调试），生产环境仅允许配置的域名

---

## 输出要求总结

### 代码完整性要求
1. **所有代码必须完整**，不使用 `// ... 其他代码` 省略
2. **必须可直接运行**，复制粘贴即可使用
3. **配置文件必须完整**，包含所有必要字段
4. **明确版本号**，避免依赖冲突
5. **注释清晰**，关键逻辑处添加注释

### 功能完整性要求
6. **所有用户可见功能必须完整实现**
   - 每个按钮点击必须有完整的业务逻辑
   - 禁止使用 `showToast('功能开发中')` 等占位符
   - 前端定义的每个 API 调用必须与后端对应
7. **前后端功能必须对称**
   - 后端有 `/users/register`，前端必须调用它
   - 后端有 `/users/login`，前端必须调用它
   - 所有 CRUD 操作必须前后端完整闭环

### 架构与设计要求
8. **遵循分层架构**，各层职责清晰
9. **H5 使用响应式设计**，禁用 pxtransform
10. **登录页为默认启动页**，无 tabBar

### 多端兼容性要求
11. **样式必须双端测试验证**
    - 每个页面在 H5 和小程序端都必须正常显示
    - 使用 `min-height: 100%` 而非 `100vh`
    - 确保 `page { height: 100%; }` 在 app.scss 中定义
12. **避免使用小程序不支持的 CSS/WXSS 特性**
    - **禁止 `*` 通配符选择器**，会导致 WXSS 编译报错 `unexpected token *`
    - **禁止 `::before`, `::after` 伪元素**，小程序不支持
    - 用 `margin` 替代 `gap`
    - 用固定值替代复杂的 CSS 变量嵌套
    - 用 `view, text, image, button, input` 枚举替代 `*` 选择器

---

## [WARNING] 最终检查清单（生成后自检）

在生成代码后，请逐项确认：

- [ ] 注册按钮点击后调用了 `userApi.register()` 并处理成功/失败
- [ ] 登录按钮点击后调用了 `userApi.login()` 并处理成功/失败
- [ ] 登录/注册成功后正确跳转到首页
- [ ] 个人中心能正确获取并显示用户信息
- [ ] 修改密码功能完整可用
- [ ] 所有页面在小程序端样式正常（无错位、无遮挡）
- [ ] 没有任何 `// TODO`、`功能开发中`、`暂未实现` 等占位内容
- [ ] 后端所有 API 端点都被前端调用

请开始生成，确保输出内容完整、规范、可执行。**禁止偷懒，禁止使用占位符。**
