# remoteScreen for Mac

把 Mac 的屏幕、应用窗口或扩展屏投到 iPad / iPhone，并用触摸和键盘操作 Mac。

[![下载](https://img.shields.io/github/v/release/relume-studio/remoteScreen-app?label=下载)](https://github.com/relume-studio/remoteScreen-app/releases/latest)

## 下载

👉 [最新版本（Releases）](https://github.com/relume-studio/remoteScreen-app/releases/latest)

| 文件 | 说明 |
|---|---|
| `remoteScreen-macOS.dmg` | 安装包：打开后把 remoteScreen 拖进「应用程序」 |
| `remoteScreen-macOS.zip` | 压缩包：解压即用 |
| `remoteScreen-1.0-macOS.dmg` / `.zip` | 同上，带版本号的固定文件名 |

官网：[remotescreen-three.vercel.app](https://remotescreen-three.vercel.app)

## 系统要求

- macOS 26.2 及以上（Apple 芯片与 Intel 通用）
- iPad / iPhone：iPadOS / iOS 15 及以上（iPad / iPhone 端 App 即将上架 App Store）

## 首次打开

安装包已用 Developer ID 签名并通过 Apple 公证，正常情况双击即可打开，不会再出现「无法验证开发者」。

1. 打开 .dmg，把 remoteScreen 拖进「应用程序」文件夹
2. 双击打开 remoteScreen
3. 按引导授予「屏幕录制」和「辅助功能」权限

如果系统仍提示无法验证开发者（例如从浏览器下载后被加上了隔离标记），运行：

```bash
xattr -dr com.apple.quarantine /Applications/remoteScreen.app
```

## 校验文件

```bash
shasum -a 256 remoteScreen-macOS.dmg
```

当前版本 1.0（build 2）的 SHA256：

```
1c5c8d900b2392f85a4d13de432ec6606c1738c8dfaf279664db65893b3f17b3  remoteScreen-macOS.dmg
416bf447fc1d3b3b2cd7985685a6ed09ea7335de9c67c2262569f153e0d567a0  remoteScreen-macOS.zip
```

## 隐私

remoteScreen 不收集任何数据，不使用任何服务器：画面、声音和操作只在你自己的设备之间传输。详见[隐私政策](https://remotescreen-three.vercel.app/privacy)。

## 联系

[relume26@gmail.com](mailto:relume26@gmail.com)

审核人员请看 **[How to Use — Reviewer Guide](REVIEWER-GUIDE.md)**，里面有完整的双端安装、连接和付费功能测试步骤。也可以直接下载 [PDF 版](REVIEWER-GUIDE.pdf)。

---

Share your Mac's screen, app windows or an extended display to iPad and iPhone, and control the Mac with touch and keyboard.

**Download**: [Latest release](https://github.com/relume-studio/remoteScreen-app/releases/latest) · Website: [remotescreen-three.vercel.app/en](https://remotescreen-three.vercel.app/en)

**Requires** macOS 26.2 or later (universal binary). The iPad / iPhone app is coming soon to the App Store.
