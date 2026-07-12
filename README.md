# BaiduWP PHP Win7 EXE Builder

将 [baiduwp-php](https://github.com/yuantuo666/baiduwp-php) 打包为 Windows 7 兼容的桌面 EXE 应用程序。

## 快速开始

### 1. Fork 本仓库
点击右上角的 **Fork** 按钮，将本仓库复制到你的 GitHub 账号下。

### 2. 触发构建

#### 方式一：手动触发
1. 进入你 Fork 后的仓库页面
2. 点击 **Actions** → **Build Win7 EXE Package**
3. 点击 **Run workflow** → 选择分支 → **Run workflow**
4. 等待构建完成后，在 **Artifacts** 中下载 ZIP

#### 方式二：发布 Release（推荐）
1. 进入仓库的 **Releases** 页面
2. 点击 **Draft a new release**
3. 输入 Tag version，例如 `v1.0.0`
4. 点击 **Publish release**
5. Actions 会自动构建并将 ZIP 上传到 Release 附件中

## 构建产物

构建完成后，你会得到一个 `baiduwp-php-win7-x86-vX.X.X.zip` 文件，解压后：

```
baiduwp-php-win7/
├── phpdesktop.exe      # 主程序，双击运行
├── settings.json       # 程序配置
├── php/                # PHP 7.1.3 运行时
├── www/                # baiduwp-php 源码
└── webcache/           # 浏览器缓存
```

## 系统要求

| 项目 | 要求 |
|------|------|
| 操作系统 | Windows 7 SP1 / 8 / 8.1 / 10 / 11 |
| 架构 | x86 (32位) 或 x64 (64位) |
| 运行库 | Visual C++ Redistributable for VS 2015 (x86) |

> **注意**：如果双击 `phpdesktop.exe` 提示缺少 `VCRUNTIME140.dll`，请下载并安装 [Visual C++ Redistributable for Visual Studio 2015](https://www.microsoft.com/download/details.aspx?id=48145)。

## 配置 SVIP Cookie

运行程序后，在程序目录下找到 `www/` 文件夹中的配置文件，按照 [baiduwp-php 官方文档](https://github.com/yuantuo666/baiduwp-php) 配置你的百度网盘 SVIP Cookie（BDUSS）。

## 技术方案

- **封装工具**: [PHP Desktop Chrome 57](https://github.com/cztomczak/phpdesktop)（最后一个原生支持 Windows 7 的版本）
- **PHP 版本**: 7.1.3
- **浏览器内核**: Chromium 57
- **构建平台**: GitHub Actions (windows-latest)

## 免责声明

本项目仅用于学习研究目的，使用本工具产生的任何法律后果由使用者自行承担。详见 [baiduwp-php 免责声明](https://github.com/yuantuo666/baiduwp-php)。
