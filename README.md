# Native Withdraw Unlock — v1.1.2

**Official stable release / 正式版（已由作者实机验证）**  
**Game:** Total War: WARHAMMER III · **Platform:** Windows x64  
**Required dependency:** Cpecific's **Memreader (win64)**, which provides `_G.memreader`.

[Download v1.1.2 (ZIP)](dist/native_withdraw_unlock_v1.1.2.zip) · [中文安装说明](docs/INSTALL_zh-CN.md) · [English installation](docs/INSTALL_en-US.md) · [Changelog](CHANGELOG.md)

## 中文简介

本 MOD 解锁游戏在部分战斗中禁用的**原版单位撤退（Withdraw）命令**，例如部分防御战或特殊战斗。它并不模拟撤退，而是解除原生战斗联盟的撤退许可限制，使玩家能使用 CA 原版撤退按钮，让单位按游戏的原生逻辑离场。

**v1.1.2 是作者确认已实机验证的正式版本。** 压缩包内部某些早期技术记录仍含 “candidate / unverified” 字样，这是旧的开发记录，**不是本次正式发行状态**；本仓库 README 和 CHANGELOG 为当前发行说明。

### 安装速览

1. 安装并启用 Cpecific's **Memreader (win64)**： [Steam Workshop 原作者页面](https://steamcommunity.com/sharedfiles/filedetails/?id=2789863945)。如果 Steam 页面无法访问，可使用你已有的 `twwh3-memreader.pack`。
2. 下载本仓库的 [v1.1.2 ZIP](dist/native_withdraw_unlock_v1.1.2.zip)，解压得到 `native_withdraw_unlock.pack`。
3. 将 `native_withdraw_unlock.pack`（以及手动安装时的 `twwh3-memreader.pack`）放入战锤3安装目录下的 `data` 文件夹。
4. 使用支持本地 .pack 的 MOD 管理器启用 **两个 MOD**，再启动游戏。进入正式战斗阶段后即可尝试原版撤退按钮。

如需处理本地 MOD 不显示、手工启用、移除和冲突问题，请阅读 [完整中文安装说明](docs/INSTALL_zh-CN.md)。

## English

This mod restores the game's **native per-unit Withdraw command** in battles where it is normally disabled. It allows the original CA Withdraw button and native order path rather than simulating retreat or moving units with custom scripts.

**v1.1.2 is the official, in-game-tested release, as confirmed by the author.** Some internal archival development notes may still call it a candidate; that statement is outdated.

1. Install and enable **Cpecific's Memreader (win64)** ([original Steam Workshop listing](https://steamcommunity.com/sharedfiles/filedetails/?id=2789863945)), or use an existing `twwh3-memreader.pack`.
2. Download [v1.1.2 ZIP](dist/native_withdraw_unlock_v1.1.2.zip) and extract `native_withdraw_unlock.pack`.
3. Put the pack in the game's `data` directory (and the Memreader pack too if installed manually).
4. Enable both mods in a mod manager that supports local .pack files, then launch the game.

For detailed instructions and troubleshooting, read [INSTALL_en-US.md](docs/INSTALL_en-US.md).

## Technical summary / 技术概要

- Uses Memreader to check and set `BATTLE_SETUP_ALLIANCE.can_withdraw` at native offset `+0x248`.
- Validates battle-unit identity and army pointer before writing; uses an explicit **one-byte** `mr.uint8(1)` write.
- Waits until the `Deployed` battle phase; initialization does not take over the exclusive unit-selection handler.
- Restores visibility of the original Withdraw UI and leaves movement and withdrawal behavior to the game.
- Does **not** modify `Warhammer3.exe` on disk; does **not** affect campaign-map strategic retreat.
- Native structure offsets are game-build sensitive; review compatibility after game updates.

**Dependency author:** Cpecific. The Memreader package is third-party software, not developed in this repository. This repository distributes the Native Withdraw Unlock package, and links to the original dependency rather than republishing its binaries.

**Checksum:** See [SHA256SUMS.txt](SHA256SUMS.txt).
