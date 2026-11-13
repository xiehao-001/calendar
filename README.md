# Calendar

`@eduwork/dsh-calendar` · v0.1.0-dev · MulanPSL-2.0 AND MIT

A sidebar calendar for DSH: week and month views over one local event set, drag-to-create, recurrence, per-occurrence notes, ICS import and export, reminders, and a group of Agent tools that read and edit the same records. Everything is stored in local DSH storage domains and never leaves the machine.

It is aimed at people who plan their week inside DSH and want the agent to look up, create or reschedule events under the normal session permission policy, with reminders arriving in the inbox instead of a separate app.

## Highlights

- Week view on an hourly axis with overlapping entries split into columns, plus all-day and multi-day rows; month view for overview, and drag or double-click on empty time to create an entry.
- Recurrence of none, daily, weekly or selected weekdays, with an optional end date and a week interval for selected weekdays.
- Move or cancel a single occurrence without touching the rest of the series, undo a move, and restore cancelled dates.
- ICS import by file selection, drag-and-drop or pasted text, with several calendars coexisting and a matching UID updating the existing entry.
- Eight Host tools: `calendar_list_events`, `calendar_create_event`, `calendar_update_event`, `calendar_delete_event`, `calendar_occurrence`, `calendar_read_personal`, `calendar_personal_settings` and `calendar_import_source`.
- Personal settings per series and occurrence: defaults, overrides, notes, private remarks, visibility and relative or fixed reminders.
- A bundled `calendar-management` skill, and a Host `calendar` service that the panel, tools, importers and reminder scheduler all share.

## Install

Install this directory as a local DSH plugin bundle. From a shell:

```bash
dsh plugin --profile web add /absolute/path/to/calendar
```

Or add the directory through the **Plugins** panel in DSH (local bundle). Restart the DSH app after installation; plugins are activated from the bundle patch (`cordis.patch.yml`).

## Configuration

No configuration keys: the bundle patch inserts the plugin with defaults.

Calendar choices (series defaults, per-occurrence overrides, reminder rules and visibility) are stored per user in the `calendar` and `calendar_personal` storage domains, not in the plugin configuration.

## Requirements

- DeepSeek Harness >=0.2.1 <0.3.0
- Peer packages: @deepseek-ai/cordis, @deepseek-ai/dsh-api-remotes, @deepseek-ai/dsh-client-ui-primitives, @deepseek-ai/dsh-client-ui-renderer, @deepseek-ai/dsh-client-ui-layout, @deepseek-ai/dsh-client-ui-sidebar, @deepseek-ai/dsh-storage-domain, @deepseek-ai/dsh-tools, @deepseek-ai/dsh-permission-presets, @deepseek-ai/dsh-typert-protocol, react, zod

## Notes and limits

- Development-stage build: the version is `0.1.0-dev`, and the bundled notes describe the plugin as still in development.
- Reminders only fire while the app runs. A restart catches up at most 24 hours of missed reminders, receipts are kept for 30 days, and system popups respect the notification master switch, foreground policy and quiet hours.
- The Host service only stores and validates records; the panel lives in the client half and the tools in `lib/tools.js`.
- Institution-managed sources belong to their plugins and cannot be overwritten by an ICS import; real school APIs and academic-calendar feeds are not integrated.

## 中文文档

[README.zh-CN.md](./README.zh-CN.md)

## License

MulanPSL-2.0 AND MIT — see [LICENSE](./LICENSE) and, where present, [LICENSE-MIT](./LICENSE-MIT). Extracted from the ECNU EduWork distribution (https://github.com/ECNU/EduWork); upstream copyright and license notices are preserved.
