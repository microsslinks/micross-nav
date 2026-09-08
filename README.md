<div align="center">

<img src="https://images.dukaworks.us.kg/picgo/microsslink.png" alt="Microsslinks" width="100">

# MicrossNav

> 由 [Microsslinks](https://github.com/microsslinks) 出品的轻量级个人导航页。

</div>

MicrossNav 是一个基于 Cloudflare Workers 部署的**可编辑、响应式、支持深浅色切换**的导航站点。它把常用的网站、工具按分类整理成卡片，同时提供 APP 视图、搜索、编辑模式、私密链接等功能。

---

## 在线预览

部署后即可通过 Worker 的 URL 访问，例如：

```text
https://micross-nav.your-subdomain.workers.dev
```

---

## 功能特性

- 🗂️ **分类管理**：自由创建、排序、隐藏、重命名分类。
- 🔗 **卡片式导航**：左图标 + 名称 + 描述的紧凑卡片；也支持 APP 网格视图。
- 🌙 **深浅色模式**：跟随系统或手动切换，保存用户偏好。
- 🔍 **实时搜索**：支持按名称、描述、URL 快速过滤。
- 🔐 **私密链接**：未登录时隐藏，登录后才可见。
- ✏️ **编辑模式**：拖拽排序、添加/编辑/删除站点，配置导出/导入。
- 📱 **响应式布局**：适配手机、平板、桌面多种屏幕。

---

## 界面截图

> 截图只在 README 中使用（不影响页面本身）。把图片上传后，把下面的 `![...](/images/xxx.png)` 换成图片地址即可。

| 截图 | 文件名 | 建议截取内容 |
|------|--------|--------------|
| 首页亮色 | `screenshot-home-light.png` | 亮色模式 + 图文卡片视图，展示多个分类 |
| 首页暗色 | `screenshot-home-dark.png` | 暗色模式 + 图文卡片视图 |
| APP 视图 | `screenshot-app-view.png` | APP 网格图标视图 |
| 编辑模式 | `screenshot-edit-mode.png` | 进入编辑模式后，显示「+」占位卡、分类操作按钮 |
| 设置菜单 | `screenshot-settings.png` | 顶部右侧头像/设置下拉菜单 |
| 移动端 | `screenshot-mobile.png` | 手机宽度下的首页效果 |
| 页脚 | `screenshot-footer.png` | 页面底部的 Logo \| Microsslinks 署名 |

示例（替换为你的实际图片地址即可）：

![首页亮色](/images/screenshot-home-light.png)

![首页暗色](/images/screenshot-home-dark.png)

![APP 视图](/images/screenshot-app-view.png)

![编辑模式](/images/screenshot-edit-mode.png)

---

## 快速开始



### 部署到 Cloudflare Workers

1. 登录 [Cloudflare Dashboard](https://dash.cloudflare.com/)。
2. 进入 **Workers & Pages** → 创建新的 Worker。
3. 将 `workers.js` 的内容完整粘贴到 Worker 编辑器中。
4. （可选）在 Worker 的「设置 → 变量」里配置管理员密码等环境变量，具体见 `workers.js` 头部注释。
5. 点击 **部署**。

### 6. 访问与配置

- 打开 Worker URL，即可看到导航页。
- 点击右上角头像/设置，打开 **编辑模式** 开始添加分类和站点。
- 登录后可见私密链接。

---

## 项目结构

```text
.
├── workers.js              # 主入口：Cloudflare Worker（HTML + API + 前端逻辑）
├── workers copy.js         # 源码备份
├── nav-sites-import.json   # 可导入的示例站点数据
└── README.md               # 本文件
```
---

## 开发说明

- 前端使用 Tailwind CSS CDN，无需本地构建。
- 交互逻辑全部在 `workers.js` 内完成，单文件即可运行。
- 数据持久化依赖 Cloudflare KV / D1 / 环境变量，具体以 `workers.js` 内实现为准。

---

## 致谢

- 项目：[MicrossNav](https://github.com/microsslinks/micross-nav)
- 工作室：[Microsslinks](https://github.com/microsslinks)
- 署名：<img src="https://images.dukaworks.us.kg/picgo/microsslink.png" alt="Microsslinks" width="28" height="28" align="center"> | Microsslinks

---

## 许可证

[MIT](LICENSE) © 2026 Microsslinks. All rights reserved.
