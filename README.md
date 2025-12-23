# TaskfileTemplate

一个用于 Claude Code 模型配置切换的 Taskfile 模板项目。

## 功能

通过 Taskfile 轻松在不同 LLM 模型配置之间切换：

- **GLM** - 智谱 AI 模型
- **MiniMax** - MiniMax 模型
- **DeepSeek** - DeepSeek 模型

## 使用方法

### 1. 安装 Task

确保已安装 [Task](https://taskfile.dev/)：

```bash
# macOS
brew install go-task/tap/go-task

# 其他系统
curl -sL https://taskfile.dev/install.sh | sh
```

### 2. 配置环境变量

在运行任务前，需要设置相应的 API Token：

```bash
export GLM_TOKEN="your-glm-token"      # 智谱 AI Token
export MINIMAX_TOKEN="your-minimax-token" # MiniMax Token
export DEEPSEEK_TOKEN="your-deepseek-token" # DeepSeek Token
```

### 3. 切换模型配置

```bash
# 切换到 GLM 模型
task claude:model-glm

# 切换到 MiniMax 模型
task claude:model-minimax

# 切换到 DeepSeek 模型
task claude:model-deepseek

# 查看当前配置
task claude:model-show
```

## 项目结构

```
.
├── Taskfile.yml              # 主配置文件
└── Taskfiles/
    └── Taskfile_claude.yml   # Claude 模型配置任务
```

## 配置说明

每个模型配置包含以下环境变量：

- `ANTHROPIC_AUTH_TOKEN` - API 认证令牌
- `ANTHROPIC_BASE_URL` - API 基础 URL
- `ANTHROPIC_MODEL` - 默认主模型
- `ANTHROPIC_SMALL_FAST_MODEL` - 快速小模型
- `ANTHROPIC_DEFAULT_OPUS_MODEL` - 最强模型（复杂任务）
- `ANTHROPIC_DEFAULT_SONNET_MODEL` - 平衡模型（日常使用）
- `ANTHROPIC_DEFAULT_HAIKU_MODEL` - 最快模型（简单任务）
- `CLAUDE_CODE_DISABLE_NONESSENTIAL_TRAFFIC` - 禁用非必要网络请求
- `API_TIMEOUT_MS` - API 超时时间（毫秒）
