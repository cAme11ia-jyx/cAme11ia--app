# 大医精诚 · 作者版更新源

当前版本：**1.6.3 / versionCode 64**

- `update.json` —— App「检查更新」读取的清单
- `yike-*.apk` —— 安装包归档（根目录留档，清单实际指向 Releases）
- GitHub Releases —— 清单里的 `apkUrl` 指向 `v1.6.3 / yike-1.6.3.apk`

从 1.6.3 起，作者版 App **内置本仓库的 update.json 地址**，不再依赖空间站。
只需手动安装这一次 1.6.3，以后在 App 内点「检查更新」→ 下载 → 安装即可完成升级。

这是一条**公开直链**：不设提取码、不需要登录，任何拿到地址的人都能下载。
清单里不含任何网盘/空间站的分享链接码。

## 维护发版

1. `python3 tools/bump.py --to <版本>`，`./android/build.sh` 打包；
2. 把 APK 传成 `yike-<版本>.apk`（本仓库根目录留档）；
3. 建同名 Release，把 APK 作为资产上传；
4. 改 `update.json`：`versionCode` / `versionName` / `size` / `sha256` / `notes` /
   `publishedAt`，`apkUrl` 指向新 Release 资产直链；
5. **先传 Release 资产、再改清单**，避免用户拿到新清单配旧包。

App 下载后会用清单里的 `sha256` 校验，APK 与清单必须同时更新，否则报「下载不完整」。
