# Orange HMI 可编辑工程

入口：`DC48854M050_1N_COF_orange_highfx_dynamic_20260609.tftprj`。
本包包含该工程引用的 8 个活动 `.tft` 页面、9 个图片资源和 `Font/` 目录，
另保留控件映射。旧页面、旧归档说明、历史编译目录和烧录输出未纳入。

原工程目录：
`99_临时工作区/orange_hmi_8page_20260908/orange_highfx_dynamic_20260617 (3)`。
原始输入附件 `orange_highfx_dynamic_20260617 (3).zip` 的 SHA-256 为
`38b2bca544f9e79ae2a58de8ae0cc6a1e7dffa418db22f8bffffa14886ffed19`。
原归档记录的重新导出工具为 VisualTFT `3.0.0.1253`。

`Font/normal/GB2312_64_64.bin` 未被当前 8 页直接引用，但仍登记在
`Font/fonts.xml` 中；因本轮无法运行 VisualTFT 重编，暂予保留。

该目录原有 `output/*.si` 与 `output/*.gwb` 的 SHA-256 分别为
`007e626ba67d066f4e9ee77c5da65e8cc97379f52bd6863b5e3c08e390472b8c` 和
`6875fb9a3ec3d5a8476dd8bee7887b319a8bb1b8f724d4603827dc82939de37e`，
与当前持久化烧录包完全一致。本轮未在 VisualTFT 中重新打开或编译工程。

`.si` 是屏幕程序、`.gwb` 是图像/资源包，均不是可编辑工程文件；
烧录时使用烧录包内的对应文件，不要把本源码包直接写入屏幕。
