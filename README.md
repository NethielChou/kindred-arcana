# 灵契秘仪 / Kindred Arcana

面向 MaiBot「塔罗工坊」插件的原创塔罗牌组资源仓库。

- **deckId**: `kindred-arcana`
- **中文名**: 灵契秘仪
- **英文名**: Kindred Arcana
- **内容版本**: `1.0.0-rc.5`
- **接口版本**: `schemaVersion=1`
- **结构**: RWS-78（大阿卡纳 22 + 圣杯/星币/宝剑/权杖各 14）
- **图片**: 78 张 800×1200 PNG，固定 ASCII cardId，正逆位共用正位图（逆位旋转 180°）

## 目录

```
manifest.json          # 牌组清单（78 张、cardId、图片摘要、许可状态）
resources.lock.json    # 发布锁：版本、manifest/资源包 SHA-256、下载地址
schema/deck.schema.json
RIGHTS.md              # 权利与使用说明
ATTRIBUTION.md         # 角色参考来源登记
LICENSE-ARTWORK.md     # 牌面使用许可
CHANGELOG.md
```

图片资源不直接放在 Git 历史中，只作为固定版本的 Release 附件发布：

- Release: v1.0.0-rc.5
- 资源包: `kindred-arcana-1.0.0-rc.5-public.zip`

插件按 `resources.lock.json` 中固定的版本、manifest SHA 与 ZIP SHA 校验后安装，禁止追随 latest。

## 在 MaiBot 插件中使用

1. 将「塔罗工坊」插件更新到支持本源仓库的版本；
2. 在聊天中发送 `/tarots switch kindred-arcana`（管理员可 `/tarots allow kindred-arcana`）；
3. 首次启用时插件下载固定版本资源包，校验 manifest 与 78 张图片摘要后安装到本地；
4. 之后抽牌与重启均从本地读取，支持离线使用；
5. 网络不可用时，可由管理员用 `/tarots import <本地zip路径>` 导入同一版本资源包。

## 校验

资源包 SHA-256：见 `resources.lock.json` 与 Release 说明。
任何 manifest/图片摘要不匹配、ZIP 越界条目、重复条目、损坏图片都会被拒绝安装；升级失败保留旧版本。

## 许可

- 图片：见 `LICENSE-ARTWORK.md`（仅授权插件内使用；禁止单独转售/再分发/商用）。
- 角色参考来源：见 `ATTRIBUTION.md`；第三方角色权利归原权利人。
- 本仓库的脚本/元数据如无另行声明按 MIT 使用。

## 版本策略

- 版本固定，插件不自动追 latest；新版本需插件侧的锁同步更新。
- 图面更新必须提升 `contentVersion`，不得原地替换同版本资源。
