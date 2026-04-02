# 变更日志

本项目遵循 [Keep a Changelog](https://keepachangelog.com/) 格式。

## [2.1.2] - 2026-04-02

### 变更

- **登录后配置刷新：** 每次微信登录成功后，在 `openclaw.json` 中更新 `channels.openclaw-weixin.channelConfigUpdatedAt`（ISO 8601），让网关从磁盘重新加载配置；不再写入空的 `accounts: {}` 占位。
- **扫码登录：** `get_bot_qrcode` 客户端超时由 5s 调整为 10s。
- **文档：** 卸载说明改为使用 `openclaw plugins uninstall @tencent-weixin/openclaw-weixin`，与插件 CLI 一致。
- **日志：** `debug-check` 日志不再输出 `stateDir` / `OPENCLAW_STATE_DIR`。

### 移除

- **`openclaw-weixin` 子命令**（删除 `src/weixin-cli.ts` 及 `index.ts` 中的注册）。请使用宿主自带的 `openclaw plugins uninstall …` 卸载流程。

### 修复

- 解决在 **OpenClaw 2026.3.31 及更新版本**上安装插件时出现的 **dangerous code pattern** 提示（宿主插件安装 / 静态检查）。
