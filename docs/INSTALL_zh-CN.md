# Native Withdraw Unlock v1.1.2 — 中文安装说明

**发行状态：正式版，作者已实机验证可用。** 适用平台为《全面战争：战锤3》Windows x64。依赖 Cpecific 的 Memreader (win64)，不是独立运行的 Lua 脚本。

## 需要的文件

- 本 MOD：`native_withdraw_unlock.pack`（下载本仓库 `dist/native_withdraw_unlock_v1.1.2.zip` 并解压）。
- 必要依赖：`twwh3-memreader.pack`（作者 Cpecific 的 Memreader (win64)）。你提供的 `twwh3-memreader.zip` 内包含这个 pack。
- Memreader 原作者 Steam 页面：https://steamcommunity.com/sharedfiles/filedetails/?id=2789863945 。如果 Steam 页面无法访问，可使用你已有的依赖 pack。

**重要：不能只安装 Native Withdraw Unlock，必须确保 Memreader 也已加载。** `memreader Plus` 是另一个 MOD，不要未经兼容性确认就将它当作这里要求的 Cpecific Memreader 的替代品。

## 推荐方法：使用 MOD 管理器

1. 在 Steam 中右键《Total War: WARHAMMER III》→ 管理 → 浏览本地文件，找到游戏目录。
2. 下载 Native Withdraw Unlock v1.1.2 ZIP，解压出 `native_withdraw_unlock.pack`。不要直接将 ZIP 放进 `data`。
3. 如果 Memreader 来自 Steam 创意工坊，请先订阅并确认它在管理器中已启用。若采用手工安装，解压你已有的 `twwh3-memreader.zip`，得到 `twwh3-memreader.pack`。
4. 把本 MOD 的 `.pack` 放进 `<游戏安装目录>\data\`。手工安装依赖时，也把 Memreader 的 `.pack` 放在同一目录。
5. 用能识别本地 `.pack` 的 MOD 管理器启用 `native_withdraw_unlock.pack` 与 Memreader。如果使用的是 Steam 订阅版 Memreader，不要再启用一份重复的手工依赖包。
6. 启动游戏，进入战斗并**开始战斗（Deployed 阶段）**，选中单位，在原版战斗命令栏尝试使用「撤退 / Withdraw」按钮。

游戏安装路径示例：`C:\Program Files (x86)\Steam\steamapps\common\Total War WARHAMMER III\data\`。实际路径可能不同，以 Steam 浏览本地文件显示的位置为准。

## 本地 MOD 没有显示怎么办？

本地 `.pack` 是否出现在官方 CA 管理器中，可能受管理器版本和安装方式影响。可以改用支持导入/启用本地 `.pack` 的管理器。高级用户也可以在游戏的 `user.script.txt` 中指定 pack，但**不要同时通过两套机制重复加载同一文件**，并先备份原有脚本配置。

常见用户脚本位置：`%APPDATA%\The Creative Assembly\Warhammer3\scripts\user.script.txt`。

仅在完全手动管理两个 pack 时，示例配置为：

```txt
mod "twwh3-memreader.pack";
mod "native_withdraw_unlock.pack";
```

如果已经由 Steam 创意工坊或 MOD 管理器启用了 Memreader，不要在配置中重复启用它。

## 功能与排查

- 本 MOD 解锁**战斗中单个/多个单位的原生撤退**，不是战役地图上的整军战略撤退，也不是士气溃逃、瞬间传送或自动寻路替代。
- 检查两份 MOD 是否都已加载；依赖脚本必须提供全局 `_G.memreader`。
- 如果战斗仍无撤退按钮，先排除没有开始战斗、UI 冲突、重复依赖以及版本不匹配。
- v1.1.2 默认关闭诊断日志；没有日志不代表已成功初始化。
- 本 MOD 写入游戏进程内存中的一个原生许可字段，不修改磁盘上的 EXE。游戏更新可能改变底层结构，必要时请等待适配，不要自行猜测并修改内存偏移。
- 如要卸载：关闭游戏后停用/移除本 MOD 的 pack；如果 Memreader 被其他 MOD 使用，应保留 Memreader。

## 发行状态备注

v1.1.2 **已由作者确认实机验证可行，属于正式版本**。原始 pack 内早期技术 README 标题中的 `EVENT-SAFE CANDIDATE` 和 `unverified` 属于未同步更新的历史说明，不代表当前发行状态。本仓库外部 README / CHANGELOG 为准。

依赖版权归 Cpecific 及其权利人；本仓库不重新分发其第三方二进制文件。
