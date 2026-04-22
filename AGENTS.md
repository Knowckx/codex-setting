# 全局规则

- 查询各类技术文档时，优先尝试用 Context7 去查

- 本机环境是 Windows10 + powershell7.6, 除非明确是远程 Linux，否则禁止使用 Bash 语法
- 多行 Python 不要写成 heredoc；请使用 PowerShell here-string 再通过管道传给 `python -`，或先写入临时 `.py` 文件再执行。

### 使用 dc(desktop-commander MCP) 注意点
- 通过 dc 的`start_process`来执行命令时，
  - 固定使用的shell为 `pwsh.exe`，禁止使用`powershell.exe`。
  - 启动的shell默认工作目录是`C:\Windows\System32`, 所以当执行python脚本时，需要通过`Set-Location`把目录切换到python仓库的根目录
- 读取普通文本文件时优先使用 read_multiple_files。仅在需要分页、负偏移或读取 PDF、图片、URL、Excel 等特殊格式时使用 read_file 工具。
- 禁用 `list_processes`命令。必须改用 `start_process` 调用 pwsh `Get-Process` 或其他可验证原生命令。

