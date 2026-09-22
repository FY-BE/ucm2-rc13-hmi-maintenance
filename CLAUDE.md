# HMI 项目维护规则

本项目只维护 Orange VisualTFT 工程。

- 只在 `source/` 编辑工程；`build/` 放临时导出；`artifacts/` 放 `.tft/.gwb/.si` 等生成物；`evidence/` 放预览、导出和真屏回读证据。
- VisualTFT GUI 操作和真屏下载由用户执行；维护人员不得把导出文件存在源码目录后宣称已生效。
- 每次可交付变化记录 VisualTFT 版本、工程源文件 full commit、产物 SHA、适用屏型号和真屏验证结果。
