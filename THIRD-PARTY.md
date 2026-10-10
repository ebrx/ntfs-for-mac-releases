# 第三方组件与对应源码

界面、磁盘管理和免费授权功能由本项目实现，NTFS 读写基于 NTFS-3G 与 macFUSE，不把底层引擎宣传为原创。

- NTFS-3G 2026.7.7：源归档 SHA-256 `d67b769025d32860549d35c2147e45024d172f81c540d750390ce3602c059dab`，保留 GPL/LGPL 各文件声明。Darwin FD 适配补丁和构建/重定位脚本应和同版本源码一同提供。
- gettext 1.0 的 libintl：保留对应 LGPL 声明，提供同版本源码与 Homebrew 构建来源。
- macFUSE 5.4.0 的 libfuse 与组件许可证：保留厂商随包的 License.rtf。系统 FSKit 模块和 MFMount 由用户从官方安装器安装；本项目不声称它们都是开源或由本项目维护。

[v0.2.0-preview.1 Release](https://github.com/ebrx/ntfs-for-mac-releases/releases/tag/v0.2.0-preview.1) 同时提供 `NTFS-for-Mac-third-party-source-0.2.0.tar.gz`：包含 NTFS-3G 与 gettext 的对应源码归档、macFUSE libfuse 源码（commit `fe59bf43f1a2f249ed8d82c7d28739121ee703a2`）、Darwin FD 适配补丁、构建与重定位脚本、许可证、来源清单和重建说明。不是仅给上游下载链接。请校验随 Release 发布的 SHA256SUMS。

系统 FSKit 扩展与 MFMount 框架由官方 macFUSE 安装器提供，不包含在本应用的重新分发载荷中。macFUSE 相关许可对商业打包有额外要求；此社区版免费、无广告、无付费授权，保留各组件原有声明。

原许可证权利不受免费授权码限制。本项目私有源码仓库保持私有，依法或依许可需要公开的第三方及派生构建材料另行提供。

参考：[GNU GPL 分发与对应源码说明](https://www.gnu.org/licenses/gpl-faq.en.html)、[macFUSE 开源状态](https://github.com/macfuse/macfuse/wiki/Open-Source-Status)、[macFUSE 官方下载](https://macfuse.github.io/)。
