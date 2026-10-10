# 第三方组件与对应源码

本项目实现界面、磁盘管理和免费激活；NTFS 读写基于 NTFS-3G 与 macFUSE，不把底层引擎宣传为原创。

- **NTFS-3G 2026.7.7**：源归档 SHA-256 `d67b769025d32860549d35c2147e45024d172f81c540d750390ce3602c059dab`。保留 GPL/LGPL 各文件声明，提供 Darwin FD 补丁及对应构建/重定位材料。
- **gettext 1.0 / libintl**：保留 LGPL 声明，提供同版本源码与已记录的 Homebrew 构建来源。
- **macFUSE 5.4.0**：合并安装包包含官方安装器的 Core 和 PreferencePane 组件，组件载荷、安装脚本、BOM 与 PackageInfo 保持字节一致，完整保留官方 License.rtf。原官方 PKG SHA-256 为 `aff74591d86b2852ee98fb485a6fdc817459425d5efb00f3460fb771524c384b`。这是本项目制作的合并安装包，不是 macFUSE 官方产品，也不表示厂商背书。

[v0.2.1-preview.1 Release](https://github.com/ebrx/ntfs-for-mac-releases/releases/tag/v0.2.1-preview.1) 提供 `NTFS-for-Mac-third-party-source-0.2.1.tar.gz`，包含 NTFS-3G/gettext 对应源码、macFUSE libfuse 2（commit `fe59bf43f1a2f249ed8d82c7d28739121ee703a2`）与 libfuse 3（commit `00e9044ac2b6349eab5cd9dc8792e1a0544e9e54`）源码、Darwin FD 适配补丁、构建和重定位脚本、许可证、来源清单与重建说明。请核对 Release 的 SHA256SUMS。

macFUSE 的 FSKit 系统扩展与 MFMount 框架是厂商二进制组件，不声称全部开源或由本项目维护。[macFUSE 许可证](https://github.com/macfuse/macfuse/blob/master/LICENSE.txt) 对商业打包另有要求；此社区预览版免费、无广告、无付费授权，按非商业再分发条款保留原许可。后续如转为商业打包，须重新核对并取得所需许可。

第三方原许可证权利不受本项目免费激活码限制。主项目源码保持私有，依许可需公开的第三方源码与派生构建材料另行提供。

[GNU 对应源码说明](https://www.gnu.org/licenses/gpl-faq.en.html) · [macFUSE 开源状态](https://github.com/macfuse/macfuse/wiki/Open-Source-Status) · [官方组件下载](https://github.com/macfuse/macfuse/releases/tag/macfuse-5.4.0)
