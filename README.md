# 大医精诚 · 作者版更新源

这个仓库只放两样东西：

- `update.json` —— 作者版 App 的更新清单
- `yike-1.6.2.apk` —— 对应的安装包（v1.6.2 / versionCode 63）

App 里「检查更新」读取的就是本仓库的 `update.json`，
清单里的 `apkUrl` 指向本仓库的 APK 直链（GitHub raw）。

这是一条**公开直链**：不设提取码、不需要登录，任何拿到地址的人都能下载。
清单里不含任何网盘/空间站的分享链接码。

## 维护

发新版时：

1. 用最新源码打包作者版 APK；
2. 把 APK 传成 `yike-<version>.apk`；
3. 重算 `size` 与 `sha256`，写进 `update.json`，`apkUrl` 指向新 APK 的 raw 地址；
4. 把 `versionCode` / `versionName` / `publishedAt` / `notes` 一并更新。

App 下载后会用清单里的 `sha256` 校验，APK 与清单必须同时更新，否则报「下载不完整」。

> 注意：App 内置的是**清单地址**。旧版 App 里写死的空间站地址改不了，
> 要让所有已装用户改从本仓库取更新，需要发一版把内置清单地址改过来的包。
