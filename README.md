# CPVC for Android

Camera Preview Video Converter 的 Android 版本，当前版本 **1.4.0**。

本公开仓库用于维护版本说明、更新检测清单和下载入口，仅包含 `README.md` 与 `update.json`。应用源码不在此仓库发布。

## 系统要求

- Android 10（API 29）及以上，arm64-v8a 或 x86_64。
- 使用系统 WebView；建议保持系统 WebView 更新。
- 连接相机存储器需兼容的读卡器／USB 存储设备及系统目录访问权限。

## 功能

- DJI OSMO Action 1、Action 2/3/4/5p、DJI goggles 视频／图片批量处理。
- Insta360 Ace Pro 2；新增 Ace Pro 一代（Beta）和 GO 3（Beta），不支持 GO 3S。
- 相机卡索引验证、已有 DCIM 输出文件夹选择、索引备份、写入回读校验及中断恢复。
- 终止、重试、已完成项保留；输入、设备或参数变化后重新开始。
- 在设备和文件管理器提供持久读取权限时，可将媒体拖入应用；也可使用系统文件选择器添加。
- 授权管理、后台转换、公共 Downloads 滚动日志及独立错误诊断导出。
- 启动后在后台检查更新，也可通过“帮助／设置 → 检查更新”手动检查。

Insta360 基础导入需要对应的 Android 许可证；DJI 为独立流程。Android 与桌面许可证不通用。

## 1.4.0 更新

同步桌面 CPVC 5.3.7 中适用于 Android 的设备适配、索引验证、终止／重试、拖放和诊断改进，并加入独立更新检测。

Ace Pro 一代使用 1280×720 H.264 LRV；Ace Pro 2 使用 854×480 H.264 LRV，两者均保留黑色 HEVC 主视频与真实音频策略。GO 3 使用独立 H.264 主视频／LRV 结构，保留原生 1088×1920 / 384×640 尺寸、显示矩阵、预留空间及 AVC 封面，支持完整输入时长和无声输入补静音。

GO 3 需保留原生 1088×1920 / 30fps 主视频与配对 LRV，不设人为 10 分钟或 128 MiB 模板上限。实际能力仍受格式、手机空间和内存约束。导入后请将相机彻底关机再开机，刷新图库。

**Ace Pro 一代和 GO 3 为 Beta。自动测试和电脑上的媒体解码检查不能代替 Android 真机与相机播放验证；新增适配仍需实机回归。** Android 使用自身可用的 MediaCodec／软件编码路径；桌面 NVIDIA、AMD、Intel 编码器及显卡库不适用于 Android。

## 下载与安装

[GitHub 下载页](https://github.com/YCTS-otree/CPVC_for_Android/releases)

安装包发布后会出现在 Releases；本次仅初始化说明和更新清单，尚未向 GitHub 上传 APK。升级请覆盖安装以保留数据及授权；签名身份变化可能改变授权设备标识。

## 更新清单

应用读取 [update.json](https://raw.githubusercontent.com/YCTS-otree/CPVC_for_Android/main/update.json)。字段沿用桌面版：`latest`、`published`、`notes`、`download_pages`、`min_supported`；`app` 固定为 `CPVC_for_Android`，版本独立于桌面版。

新版本显示版本号、日期、说明和下载页按钮，由用户选择是否下载。网络失败不会阻止启动或转换。Gitee 暂未接入，待维护者后续配置。

## 帮助

[使用帮助](https://www.bilibili.com/video/BV1cCuYzvExf/) · [作者主页](https://space.bilibili.com/668497683/) · [许可证购买／试用](https://license.ycts.top/)

相机写入前请备份重要媒体与索引；保留未完成事务和备份，按应用提示恢复。
