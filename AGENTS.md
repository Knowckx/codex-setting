# 全局规则

- 回答要精炼。
只回答问的内容，默认不铺垫、不总结、不扩展。
能一句话说清就一句话。
除非我要求详细解释，否则不要展开背景知识。

- 本机开发环境是 Windows10 + pwsh(Powershell 7) 
默认禁止使用 Bash 语法， 除非是处在 Linux 环境

- 执行多行 Python 禁止使用 Bash heredoc；改用 PowerShell here-string | python -，或写入临时 .py 文件后运行。

### MCP工具
- 用 Context7 去查各类文档

#### 使用 dc(desktop-commander MCP)
- 调用 dc 的 start_process 时:
  - 固定使用的shell为 pwsh.exe 禁止使用 powershell.exe
  - 注意启动shell后默认的工作目录是 C:\Windows\System32 , 所以需要使用 Set-Location 切到合适的路径后再执行命令
- 读取普通文本文件时优先使用 read_multiple_files
- 禁用 list_processes 命令。必须改用 start_process 调用 pwsh Get-Process

