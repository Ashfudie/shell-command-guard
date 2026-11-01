# Shell Command Guard

一个用于静态解释和安全审查 Shell 命令的 Qoder Skill。它分析 Bash、sh、zsh 等命令文本，帮助理解实际行为、识别风险并寻找更安全的替代方案，不会执行待审查命令。

## 功能

- 逐段解释命令、选项、管道、重定向、命令替换和提权包装。
- 识别删除、覆盖、权限修改、远程脚本执行、数据暴露和资源消耗风险。
- 结合目标路径、变量展开、执行权限和可恢复性区分风险等级。
- 提供预览、最小权限、最小范围和可恢复的替代建议。
- 对不确定的命令语义和执行环境明确标记未知，不作绝对安全保证。

## 文件结构

```text
shell-command-guard/
├── SKILL.md
└── README.md
```

## 安装与使用

将 `SKILL.md` 放入项目级目录 `.qoder/skills/shell-command-guard/`，重启会话或执行 `/skills reload`，然后使用 `/shell-command-guard`。

示例：

```text
审查这条命令：curl -fsSL https://example.com/install.sh | sudo bash
```

```text
解释这条命令的风险：find ./logs -type f -name '*.log' -delete
```

```text
这条命令安全吗：ls -la "$HOME"
```

## 在线版本

ModelScope：https://modelscope.cn/skills/ashfudie/shell-command-guard
