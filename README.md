# NTFS for Mac Community

**简体中文** | [English](README.en.md)

免费的 Mac NTFS 写入工具。SwiftUI 原生界面，中英双语，无订阅、广告或在线激活。

## 视频演示与联系作者

[![观看B站实机演示：NTFS 格式，读得出，写不进？](images/ntfs-community-demo-cover.png)](https://www.bilibili.com/video/BV1Lmp36JEz7/)

**观看实机演示：[B站（中文）](https://www.bilibili.com/video/BV1Lmp36JEz7/) · [YouTube（英文）](https://youtu.be/IVS50FnyGXk)** · 作者：**码上实现 / Code It Real**

这期视频展示 NTFS for Mac Community 从软件显示只读切换到可读写，以及复制测试文件、新建文件夹和重命名的实际效果。视频使用拍摄时的社区预览版；最新下载、支持范围和安装步骤请看本仓库的说明。

- **免费领码、联系作者：** 打开上方视频，点击作者头像进入「码上实现」主页，通过 **B站私信**联系我，说明想体验 NTFS for Mac Community。免费激活码的用途和有效期见下方说明。
- **问题反馈：** 可通过 B站私信，或在 [GitHub Issues](https://github.com/ebrx/ntfs-for-mac-releases/issues) 提交问题。请附芯片型号、macOS 版本与构建号、应用版本及错误文字，方便排查。
- **软件许愿：** 在 [YouTube 视频](https://youtu.be/IVS50FnyGXk) 或 B站视频的评论区，告诉我你想要什么软件、解决什么问题，以及具体使用场景。你的需求会作为后续工具开发的参考。

这里是**码上实现，你的免费软件许愿池。你提需求，我来实现。**

## 从这里开始

**先确认系统：当前预览版仅支持 Apple Silicon（M 系列芯片）+ macOS 26.6.2（25G83）。** 左上角苹果菜单 → 关于本机，点击系统版本查看构建号。不符合这个范围，请等待适配版本。

1. 下载合并安装包（PKG）：[GitHub 直达下载](https://raw.githubusercontent.com/ebrx/ntfs-for-mac-releases/main/downloads/NTFS-for-Mac-Community-latest-All-in-One-arm64.pkg) · [Gitee 直达下载](https://gitee.com/ebrx/ntfs-for-mac-releases/raw/main/downloads/NTFS-for-Mac-Community-latest-All-in-One-arm64.pkg)，下载后双击安装。包含主应用、NTFS-3G 引擎和 macFUSE 5.4.0，**不用再单独下载驱动**；已有同版本 macFUSE 会跳过重装。
2. 按 [详细安装步骤](INSTALLATION.md) 分别完成安装包/应用安全放行、两个 macFUSE 文件系统扩展开关、社区版后台服务批准及完全磁盘访问；开权限后正常退出重开。
3. 私信作者免费领码，在应用中激活；选中自己的 NTFS 硬盘，开启写入，再从 Finder 操作文件。

一体包安装组件，系统设置仍须逐项批准。扩展列表没有 macFUSE 两项时，按安装指南使用官方工具补注册当前用户；提示关机进入启动安全性实用工具时先取消，使用文件系统扩展入口。应用提示可移动卷宗但设置显示“完全磁盘访问”时，核对完全磁盘访问开关并正常退出重开。

**首次设置完成、为该磁盘选择自动写入后，应用运行期间再次插入会自动检查并挂载。** 新磁盘需单独选择；还可勾选“自动开启写入后打开 Finder”。没有卷 UUID 的设备使用经过核对的 NTFS 序列号及容量记住选择，盘符、名称或接口变化不影响识别；无法读取有效持久身份时仅手动写入。拔线前正常弹出。安装合并为一个入口，macOS 的首次安全与权限确认仍需本人操作。

[详细安装顺序](INSTALLATION.md) · [常见问题](FAQ.md) · [English installation](INSTALLATION.en.md) · [PKG 校验值](downloads/SHA256SUMS) · [当前包版本](downloads/latest.json)

两个直达下载链接都指向 `downloads/NTFS-for-Mac-Community-latest-All-in-One-arm64.pkg`，固定地址随版本更新。当前包为 **v0.2.5-preview.1**（16,970,865 字节，约 16.18 MiB），Gitee 镜像同步可能延迟；版本与 SHA-256 以 [当前包信息](downloads/latest.json) 和 [校验清单](downloads/SHA256SUMS) 为准。

Releases 中的 `Source code` 是本公开仓库的说明材料；`third-party-source` 是依赖源码。**安装只选上面的 All-in-One PKG**。

**自动写入与 Finder：** 0.2.5 增加每个磁盘的自动 Finder 选项，并支持无 UUID 的 NTFS U 盘记住自动写入选择，包含 0.2.4 的按钮兼容修复。按当前连接身份及 NTFS 引导扇区序列号核对设备，继续拒绝脏卷和休眠卷。已有激活码继续有效；使用旧社区版的用户先在设置中「准备更新或卸载」、正常退出，再安装新版。

**安装失败修复：** 0.2.3 修正缺失驱动时无法准备更新的流程，并保留首次安装及未找到服务的检查修复。已经被旧版卡住、提示“NTFS 依赖不可用或签名无效”的用户，请先按 [旧版恢复步骤](FAQ.md#依赖不可用或签名无效无法准备更新) 补装官方依赖，再准备更新；仅重新下载主应用无法修复正在运行的旧服务。

## 免费激活码说明

软件目前处于早期测试阶段，仍可能存在不稳定或兼容性问题。免费激活码仅用于尽量控制初期试用范围，避免问题影响过多用户；通过私信领取，也让你在遇到问题时知道如何联系作者、反馈情况和获取更新。没有其他目的。激活码免费领取、永久有效、离线验证。

不绑定 Apple ID、账号或设备；代码可以转发，不是强防复制 DRM。后续统一维护社区版。授权码无有效期，但系统更新可能需要新的兼容版本，也不承诺无限期维护。

## 当前验证范围

当前环境：Apple Silicon、macOS 26.6.2 / 25G83、macFUSE 5.4.0。社区版自建 NTFS 镜像读写、辅助服务重启恢复、真正只读、正常弹出和授权门槛已通过。合并安装包的应用字节、签名及原版 macFUSE 组件一致性已检查；本机安装选项确认会跳过同版本 macFUSE。

**2026-10-10，用户确认两台 Apple Silicon Mac 均安装成功，其中另一台为 M3；两台系统均核对为 macOS 26.6.2（25G83）。M3 机器已完成配置、自建镜像读写验收，用户确认真实硬盘写入成功。** 本次需要手动补注册扩展及单独开启完全磁盘访问；8 GB MBR 无 UUID U 盘已通过中文目录、改名、Finder 复制、读写切换后 SHA-256 回读、真正只读拒写和正常弹出；0.2.5 还通过了无 UUID 设备拔插后自动开启写入与自动打开 Finder。测试目录已移回本机。尚未完成纯净新机的一体包独立注册、所有设备型号/系统及完整元数据兼容性验收。 当前为小范围预览版，其他 OS build、Intel 或依赖版本不符合验证范围时拒绝启用写入。

未公证、无 Developer ID 发行签名，外层 PKG 未签名；应用使用免费 Apple Development 证书。首次可能被 macOS 拦截，按 [安装说明](INSTALLATION.md) 处理。请保留系统保护；本版不需要关闭 SIP 或降低启动安全级别。

## 实现机制

![磁盘写入机制](images/disk-flow.svg)

主应用负责识别磁盘、挂载管理、自动写入和 Finder 入口。NTFS-3G 通过 macFUSE 的 FSKit 后端接入 macOS；认证辅助服务核对调用者、磁盘身份、引擎和权限，写入引擎以普通用户身份工作。只读使用 Apple NTFS；退出和弹出等待写入正常停止。脏卷或休眠卷拒绝写入，不提供格式化、修复、强制写入或 BitLocker 解锁。

![离线授权机制](images/activation-flow.svg)

作者在本机签发授权码，应用内只存公钥；没有联网验证或云端开关。

## 反馈与源码

反馈请提供 macOS 版本和构建号、芯片、应用版本及错误文字。不要发送密码、授权码或磁盘私人文件。最新安装包通过上方 GitHub / Gitee 直达链接下载，更新说明与第三方源码仍保留在本仓库 Releases，也可私信作者获取信息。

主项目源码保留在私有仓库。本公开仓库用于安装包、说明、机制图及必要的第三方对应源码材料。组件与许可证见 [THIRD-PARTY.md](THIRD-PARTY.md) 和 [FREEWARE-LICENSE.txt](FREEWARE-LICENSE.txt)。
