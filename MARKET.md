# 本机日历（@eduwork/dsh-calendar）

> 侧栏周/月视图日历，支持拖动新建、提醒与 ICS 导入，数据只存本机。
>
> Sidebar week/month calendar with drag-to-create, reminders and ICS import; local data only.

## 功能

提供日历面板与一组工具（查询、新建、修改、删除日程），支持多来源（个人/课程表）与提醒投递。数据保存在本机 DSH 存储域，不上传。

## 安装

```bash
# 在 DSH 中把本目录作为本地 bundle 安装（绝对路径）
```

安装后由 DSH 插件系统加载，条目 id 为 `calendar`。

## 依赖

- `@deepseek-ai/cordis`
- `@deepseek-ai/dsh-api-remotes`
- `@deepseek-ai/dsh-client-ui-primitives`
- `@deepseek-ai/dsh-client-ui-renderer`
- `@deepseek-ai/dsh-client-ui-layout`
- `@deepseek-ai/dsh-client-ui-sidebar`
- `@deepseek-ai/dsh-storage-domain`
- `@deepseek-ai/dsh-tools`
- `@deepseek-ai/dsh-permission-presets`
- `@deepseek-ai/dsh-typert-protocol`
- `react`
- `zod`

## 兼容性

- `engines.dsh`: `>=0.2.1 <0.3.0`
- 与 EduWork 发行版同源，来源于 ECNU/EduWork 仓库。

## 许可

MulanPSL-2.0 AND MIT（与上游 EduWork 一致）。
