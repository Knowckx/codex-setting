# 全局规则

- 在查询各种技术资料时，不要靠记忆，优先用 Context7；如果已知库名或版本，就直接带上库 ID 和版本。
- 如果 Context7 覆盖不足，再回退到官方文档、更新日志或官方仓库。



### 使用 dc(desktop-commander MCP) 注意点
- 使用dc执行命令时，使用的shell为 `pwsh.exe`。禁止使用`powershell.exe`。
- 读取普通文本文件时优先使用 read_multiple_files；仅在需要分页、负偏移或读取 PDF、图片、URL、Excel 等特殊格式时使用 read_file 工具。若 read_file 仅返回元信息、空正文或异常结果，立即改用 read_multiple_files 重新读取。
- 禁用 `list_processes`命令。必须改用 `start_process` 调用 pwsh `Get-Process` 或其他可验证原生命令。