# I Am the AI

A web game for kids: play a simple AI (a bigram language model), build sentences by counting which word comes next, change the AI's data, and earn a certificate.

一个给孩子玩的网页游戏：扮演一个最简单的AI（二元语言模型），通过数“下一个词出现几次”来造句，再亲手改变AI的数据，最后获得证书。

## 文件说明

```
i-am-the-ai-site/
├── public/                  ← 网站本身（Render 发布这个文件夹）
│   ├── index.html           ← 整个游戏
│   └── vendor/
│       └── html2canvas.min.js   ← 保存证书图片用的工具库（v1.4.1）
├── render.yaml              ← Render 部署设置
├── README.md
└── .gitignore
```

这是纯静态网站，不需要安装任何东西，也不需要构建步骤。

## 第一步：上传到 GitHub

1. 登录 GitHub，点右上角 **+** → **New repository**。
2. 填写仓库名（例如 `i-am-the-ai`），选择 **Public**，点 **Create repository**。
3. 在新仓库页面点 **uploading an existing file**。
4. 把解压后 `i-am-the-ai-site` 文件夹**里面的所有内容**（`public` 文件夹、`render.yaml`、`README.md`、`.gitignore`）拖进去。
   注意：拖的是文件夹里面的内容，不是外层文件夹本身。
5. 点 **Commit changes**。

> `.gitignore` 是隐藏文件，Mac 上按 `Cmd + Shift + .` 可以显示。漏传它也不影响网站。

## 第二步：在 Render 上部署

**方法 A：Static Site（推荐，最简单）**

1. 登录 [render.com](https://render.com)，点 **New** → **Static Site**。
2. 连接你的 GitHub 账号，选择刚才的仓库。
3. 填写设置：
   - **Branch**：`main`
   - **Build Command**：留空
   - **Publish Directory**：`public`
4. 点 **Create Static Site**。一两分钟后会得到一个网址，例如 `https://i-am-the-ai.onrender.com`。

**方法 B：Blueprint**

点 **New** → **Blueprint**，选择仓库。Render 会读取 `render.yaml` 自动完成设置。

## 以后怎么更新

在 GitHub 上替换 `public/index.html` 并提交，Render 会自动重新部署。

## 说明

- **进度保存**：保存在孩子自己的浏览器里，换设备或清除浏览器数据后会从头开始。
- **朗读声音**：使用设备自带的声音。Edge 上优先用微软自然女声（Ava、Aria、Jenny），Safari 上用 Samantha。老师模式里可以手动换声音。
- **保存证书**：点击后直接下载为 PNG 图片。
- **字体**：从 Google Fonts 加载。如果所在网络无法访问 Google，会自动换成系统字体，游戏照常运行。
