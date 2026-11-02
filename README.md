# remoteScreen for Mac

把 Mac 的屏幕、应用窗口或扩展屏投到 iPad / iPhone，并用触摸和键盘操作 Mac。

[![下载](https://img.shields.io/github/v/release/ouyongyong/remoteScreen-app?label=下载)](https://github.com/ouyongyong/remoteScreen-app/releases/latest)

## 下载

👉 [最新版本（Releases）](https://github.com/ouyongyong/remoteScreen-app/releases/latest)

| 文件 | 说明 |
|---|---|
| `remoteScreen-macOS.dmg` | 安装包：打开后把 remoteScreen 拖进「应用程序」 |
| `remoteScreen-macOS.zip` | 压缩包：解压即用 |

官网：[remotescreen-three.vercel.app](https://remotescreen-three.vercel.app)

## 系统要求

- macOS 26.2 及以上（Apple 芯片与 Intel 通用）
- iPad / iPhone：iPadOS / iOS 15 及以上（iPad / iPhone 端 App 即将上架 App Store）

## 首次打开

当前版本尚未经过 Apple 公证，第一次打开时 macOS 会提示「无法验证开发者」。放行一次即可：

1. 打开 .dmg，把 remoteScreen 拖进「应用程序」文件夹
2. 双击打开 remoteScreen，看到提示后点「完成」
3. 打开「系统设置 → 隐私与安全性」，在页面下方找到 remoteScreen，点「仍要打开」并确认

也可以在「终端」里执行：

```bash
xattr -dr com.apple.quarantine /Applications/remoteScreen.app
```

## 校验文件

```bash
shasum -a 256 remoteScreen-macOS.dmg
```

对照 [Releases](https://github.com/ouyongyong/remoteScreen-app/releases/latest) 页面里的 SHA256。

## 隐私

remoteScreen 不收集任何数据，不使用任何服务器：画面、声音和操作只在你自己的设备之间传输。详见[隐私政策](https://remotescreen-three.vercel.app/privacy)。

## 联系

[yongyong.ou@gmail.com](mailto:yongyong.ou@gmail.com)

---

Share your Mac's screen, app windows or an extended display to iPad and iPhone, and control the Mac with touch and keyboard.

**Download**: [Latest release](https://github.com/ouyongyong/remoteScreen-app/releases/latest) · Website: [remotescreen-three.vercel.app/en](https://remotescreen-three.vercel.app/en)

**Requires** macOS 26.2 or later (universal binary). The iPad / iPhone app is coming soon to the App Store.

This build isn't notarized by Apple yet. On first launch, open "System Settings → Privacy & Security" and click "Open Anyway", or run:

```bash
xattr -dr com.apple.quarantine /Applications/remoteScreen.app
```

No data is collected and no servers are used — screen, audio and input travel only between your own devices. [Privacy Policy](https://remotescreen-three.vercel.app/en/privacy)
