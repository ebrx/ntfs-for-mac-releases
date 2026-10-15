# 第三方组件与对应源码

本项目实现界面、磁盘管理和免费激活；NTFS 读写基于 NTFS-3G 与 macFUSE，不把底层引擎宣传为原创。

- **NTFS-3G 2026.7.7**：源归档 SHA-256 `d67b769025d32860549d35c2147e45024d172f81c540d750390ce3602c059dab`。保留 GPL/LGPL 各文件声明，提供 Darwin FD 补丁及对应构建/重定位材料。
- **gettext 1.0 / libintl**：保留 LGPL 声明，提供同版本源码与已记录的 Homebrew 构建来源。
- **macFUSE 5.4.0**：合并安装包包含官方安装器的 Core 和 PreferencePane 组件，组件载荷、安装脚本、BOM 与 PackageInfo 保持字节一致，完整保留官方 License.rtf。原官方 PKG SHA-256 为 `aff74591d86b2852ee98fb485a6fdc817459425d5efb00f3460fb771524c384b`。这是本项目制作的合并安装包，不是 macFUSE 官方产品，也不表示厂商背书。

[v0.3.0 Release](https://github.com/ebrx/ntfs-for-mac-releases/releases/tag/v0.3.0) 提供 `NTFS-for-Mac-third-party-source-0.3.0.tar.gz`，包含 NTFS-3G/gettext 对应源码、macFUSE libfuse 2（commit `fe59bf43f1a2f249ed8d82c7d28739121ee703a2`）与 libfuse 3（commit `00e9044ac2b6349eab5cd9dc8792e1a0544e9e54`）源码、Darwin FD 适配及空 FinderInfo 读取补丁、构建和重定位脚本、许可证、来源清单与重建说明。FinderInfo 补丁不改写磁盘数据。请核对 Release 的 SHA256SUMS。旧版依赖材料仍随对应历史 Release 保留。

macFUSE 的 FSKit 系统扩展与 MFMount 框架是厂商二进制组件，不声称全部开源或由本项目维护。[macFUSE 许可证](https://github.com/macfuse/macfuse/blob/master/LICENSE.txt) 对商业打包另有要求；此社区预览版免费、无广告、无付费授权，按非商业再分发条款保留原许可。后续如转为商业打包，须重新核对并取得所需许可。

第三方原许可证权利不受本项目免费激活码限制。主项目源码保持私有，依许可需公开的第三方源码与派生构建材料另行提供。

[GNU 对应源码说明](https://www.gnu.org/licenses/gpl-faq.en.html) · [macFUSE 开源状态](https://github.com/macfuse/macfuse/wiki/Open-Source-Status) · [官方组件下载](https://github.com/macfuse/macfuse/releases/tag/macfuse-5.4.0)

## 旧版依赖恢复

旧应用因依赖缺失无法准备更新时，从 [macFUSE 官方 5.4.0 Release](https://github.com/macfuse/macfuse/releases/tag/macfuse-5.4.0) 下载官方 DMG，打开后运行其中的 PKG；不要安装旧版社区应用。安装器原始 PKG 的 SHA-256 为 `aff74591d86b2852ee98fb485a6fdc817459425d5efb00f3460fb771524c384b`。不降级更高版本。正常首次安装仍只用本项目当前 All-in-One。完整顺序见[恢复步骤](FAQ.md#依赖不可用或签名无效无法准备更新)。

For dependency recovery use the official macFUSE 5.4.0 DMG and its original PKG. This project no longer offers old application installers. Normal installation uses the current All-in-One. See the [English recovery steps](FAQ.en.md#dependencies-unavailable-or-invalid-cannot-prepare-an-update).
