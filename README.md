# TermBuddy Android

TermBuddy 的安卓客户端安装包发布仓库：在手机上接管电脑终端里正在运行的 Claude Code 和 Codex 对话。本仓库只发布 APK，不包含源码。

## 安装

1. 在 [Releases](https://github.com/fgozxy/termbuddy-android/releases/latest) 下载 `TermBuddy-vX.Y.Z.apk`
2. 安装时如提示「未知来源」，在系统设置里允许浏览器（或文件管理器）安装应用
3. 在电脑上运行 `tb pair <你的地址>`，用 App 扫码连接；开启了两步验证时再输入验证器里的 6 位码

已安装的 App 会每天检查一次新版本，也可以在「设备 → 软件更新」里手动检查，下载完成并校验通过后直接调起系统安装，登录状态保留。

## 校验

每个版本都附带 `SHA256SUMS.txt`：

```bash
sha256sum -c SHA256SUMS.txt
```

所有版本使用同一个签名证书，SHA-256 指纹：

```
69:CD:FE:EA:E6:AA:63:9C:F8:B5:C2:93:2D:6E:BC:D8:AA:41:B2:97:48:02:2C:1A:56:E7:6E:C0:F5:A8:FA:6D
```

可用 `apksigner verify --print-certs TermBuddy-vX.Y.Z.apk` 核对。App 内更新会自动检查 SHA-256、包名、版本号和签名证书，任何一项不一致都不会安装。
