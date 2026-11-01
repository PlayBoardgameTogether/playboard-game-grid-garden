# PlayBoard · Grid Garden

游戏规则、React 棋桌、AI 策略、资源契约、测试与独立版本的维护仓库。平台：[PlayBoardgameTogether/PlayBoardgameTogether](https://github.com/PlayBoardgameTogether/PlayBoardgameTogether)。

## 开发与验证

Node.js 22，pnpm@11.15.1。

```sh
pnpm install --frozen-lockfile
pnpm typecheck
pnpm test
pnpm build
pnpm verify
```

游戏位于 `games/grid-garden`，兼容 SDK 0.1.0；`packages/game-sdk` 是来自平台 0.17.0 的固定兼容性快照，只用于独立开发和测试。不要把平台账号、房间、数据库或秘密加入本仓库。初始来源提交、原始摘要见 SOURCE.json，原文件保持不变，不代表完整 Git 历史迁移。

## 发布

游戏版本来自 `games/grid-garden/package.json`，必须与 manifest 一致。推送 `grid-garden-vMAJOR.MINOR.PATCH` 标签，在检查通过后创建独立 GitHub Release，附件为编译后的 npm 游戏包、SHA256SUMS 与 release.json。普通推送只产生验证产物。已发布版本不可覆盖。

这是可信内置扩展，发布包 **不是在线安装 ZIP**。平台通过审查 PR 更新锁定的源码集成副本并构建部署；账号、动作、恢复和隐私仍由平台原链路负责。保留旧精确版本，禁止将旧对局静默切换到新规则。本仓库的发布不表示平台已经部署。

后续修改只在本游戏仓库提交；平台的集成副本由锁文件记录本仓库完整提交 SHA。相关游戏说明见 docs/games（如有）；其中原平台联机验收命令仍在平台运行。

## 许可证

Copyright (C) 2026 TheTopBoardgameAssociation

除另有声明的文件外，本项目采用 [GNU GPL v3.0](LICENSE)（`GPL-3.0-only`）开源协议，允许按协议使用、修改和分发。本软件不提供任何担保，具体条款见 LICENSE。

已有单独许可声明的素材、第三方代码和依赖继续遵循各自的许可与署名要求；例如标明 CC0-1.0 的资源仍按原许可分发。

## 玩家名称（2026-11-01，客户端包 1.0.1）

棋桌、等待提示和公开结果使用平台提供的 playerNames 昵称映射，本人附加“（你）”，匿名教程保持回退。仅客户端包升级到 1.0.1；规则 manifest、资源版本与规则摘要保持 1.0.0，旧局继续精确恢复。发布标签按包版本，release.json 同时记录 version（包）和 gameVersion（规则）。平台 1.1.1 完成客户端参数装配。官方目录已核对，无需改动；内置游戏随平台构建，不通过 ZIP 安装。

本轮实际验证与发布边界见 [昵称修复验证](docs/player-names-validation.md)。
