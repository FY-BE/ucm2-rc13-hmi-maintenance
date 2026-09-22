# Orange HMI 八页控件契约 R1

生成日期：2026-09-08。权威来源：本目录 `output/DefineID.h`。

## 页面

| ID | 页面 | 说明 |
|---:|---|---|
| 0 | `startup` | 启动进度 |
| 1 | `home` | 正常测量主页 |
| 2 | `about` | 正常设备信息 |
| 3 | `home_signal_error` | 信号异常主页 |
| 4 | `about_signal_error` | 信号异常设备信息 |
| 5 | `mode_select` | 自动/手动模式选择 |
| 6 | `maintenance` | 维护菜单、进度和结果 |
| 7 | `device_model_select` | 内置设备型号选择 |

## ARM 动态控件

| 页面 | ID | 控件 | ARM 写入内容 |
|---|---:|---|---|
| `startup` | 1 | `startup_progress1` | 启动进度值 |
| `startup` | 2 | `startup_progress_percent` | 启动百分比文本 |
| `home` / `home_signal_error` | 0 | `*_error_message` | 异常原因，仅异常页显示 |
| `home` / `home_signal_error` | 1 | `*_status` | 当前运行状态 |
| `home` / `home_signal_error` | 2 | `*_force_value` | 总力或四杆平均应变 |
| `home` / `home_signal_error` | 3 | `*_deviation` | ARM 正式偏差值 |
| `home` / `home_signal_error` | 4 | `*_distribution` | ARM 分布结论 |
| `home` / `home_signal_error` | 5..8 | `*_rod_1..4` | 四杆力或四杆应变 |
| `home` / `home_signal_error` | 9..13 | 单杆及主单位 | `kN`、`T`、`με` |
| `home` / `home_signal_error` | 14 | `*_primary_label` | `锁模力` 或 `平均应变` |
| `about` / `about_signal_error` | 0 | `about_error_message` | 异常原因，仅异常页显示 |
| `about` / `about_signal_error` | 1 | `about_status` | 当前运行状态 |
| `about` / `about_signal_error` | 2 | `about_serial1` | 设备名称 |
| `about` / `about_signal_error` | 3 | `about_memory2` | 检测精度 |
| `about` / `about_signal_error` | 4 | `about_serial` | 设备序列号 |
| `about` / `about_signal_error` | 5 | `about_memory1` | 通道数 |
| `about` / `about_signal_error` | 6 | `about_hardware_version` | 硬件版本 |
| `about` / `about_signal_error` | 7 | `about_memory` | ARM 实时内存占用 |
| `about` / `about_signal_error` | 8 | `about_software_version` | ARM 应用版本 |
| `about` / `about_signal_error` | 9 | `about_storage` | ARM 实时存储占用 |
| `mode_select` | 1..2 | 选择框 | 自动/手动高亮 |
| `mode_select` | 5 | `mode_countdown` | 5 秒自动确认提示 |
| `maintenance` | 1..3 | 选择框 | 三项维护功能高亮 |
| `maintenance` | 10 | `maint_title` | 维护标题 |
| `maintenance` | 11 | `maint_status` | 当前维护项说明 |
| `maintenance` | 100 | `logpopup` | 操作进度/结果弹层 |
| `maintenance` | 101..103 | 状态、进度文本和进度条 | ARM 操作结果 |
| `device_model_select` | 1 | `model_status` | 当前型号/应用结果 |
| `device_model_select` | 2..7 | `model_row_1..6` | ARM 内置型号列表；当前仅 `DE168` |
| `device_model_select` | 8 | `model_position` | 当前序号/总数；当前 `1/1` |
| `device_model_select` | 9 | `model_confirm_label` | `确认并下发` |
| `device_model_select` | 10 | `model_title` | `选择型号` |
| `device_model_select` | 20..25 | 选择框 | 六行型号高亮 |
| `device_model_select` | 30 | `model_scroll` | 列表位置 |

## 冻结行为

- 触摸面板和控件通知关闭；屏幕不处理触摸，不运行计算。
- 两个实体键由 ARM 读取：确认键、下一项键；不实现返回键和长按。
- 主页确认键按 `kN → T → με → kN` 循环。吨、微应变换算均在 ARM 完成。
- 信号异常时所有测量值显示 `--`，不保留旧值。
- 型号页目前唯一内置项为 `DE168`，进入后默认高亮，必须按确认键应用并保存。
