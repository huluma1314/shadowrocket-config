# Shadowrocket 懒人配置 — AI 优先版

> 导入后无需再打开 Shadowrocket，专门解决 ChatGPT / Gemini / Claude 移动 App 的节点封锁问题。

## 设计理念

| 流量类型 | 走哪个节点 | 原因 |
|---|---|---|
| **ChatGPT / Gemini / Claude / Copilot** | 🇺🇸 **美国**（硬绑定） | 三家 AI App 对 HK/亚洲节点封锁率高，美国覆盖最广 |
| 其他国外服务（流媒体/社交/开发/游戏） | Proxy（默认香港） | 速度快 |
| 国内服务（微信/B站/百度/知乎等） | DIRECT 直连 | 不走代理 |

## 一键导入

**Shadowrocket → 配置 → 右上角 ＋ → 粘贴以下 URL：**

```
https://raw.githubusercontent.com/huluma1314/shadowrocket-config/main/lazy_group_slim.conf
```

导入后连接 VPN 即可。无需再打开 Shadowrocket。

## 推荐：安装 GMOogway 广告拦截模块（一次操作，永久生效）

> 打开 Shadowrocket → 配置 → 本文件后的 ⓘ → 模块 → 右上角 ＋ → 粘贴：

```
https://raw.githubusercontent.com/GMOogway/shadowrocket-rules/master/sr_reject_list.module
```

这条模块包含 **17 万+ 条广告拦截规则**，安装后所有 App 内广告、网页广告自动屏蔽。

## 策略组（5 组）

| 策略组 | 类型 | 说明 |
|---|---|---|
| 香港 | url-test | 自动选延迟最低的香港节点 |
| 美国 | url-test | 自动选延迟最低的美国节点（AI 专用） |
| 其他 | url-test | 台日新韩英德等其余节点 |
| Proxy | select | 手动拨选 香港/美国/其他（默认香港） |
| Final | select | 兜底（默认 Proxy） |

## 规则集来源

- [blackmatrix7/ios_rule_script](https://github.com/blackmatrix7/ios_rule_script) — 远程 RULE-SET，Shadowrocket 每次连接自动拉取最新版本
- 覆盖 50+ 常用服务，按类别直连/代理分流
- 配置文件每日自动同步更新 👇

## 自动同步

本仓库通过 GitHub Actions 每日自动检查规则集更新并同步。

[![Sync Rules](https://github.com/huluma1314/shadowrocket-config/workflows/sync-config/badge.svg)](https://github.com/huluma1314/shadowrocket-config/actions)