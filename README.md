下面是为你的 `bilibili-mcp` 工具生成的 `README.md` 示例：

---

# 📺 bilibili-mcp

一个用于获取 B 站热榜的 MCP 工具，基于 FastMCP 和 B 站公开接口。你可以通过注册到 Cursor 或其他 MCP 客户端，实时调用热门视频数据。

## 🚀 快速开始

### 1. 安装依赖

确保使用 Python ≥ 3.12，并安装以下依赖项：

```bash
pip install httpx "mcp[cli]>=1.6.0"
```

### 2. 项目结构示例

你的主代码文件可以是 `bilibili_mcp.py`，项目结构如下：

```
bilibili_mcp/
├── bilibili_mcp.py
├── pyproject.toml
└── README.md
```

### 3. 启动 MCP Server

使用 [`uv`](https://github.com/astral-sh/uv) 运行工具：

```bash
uv tool run bilibili-mcp
```

或通过配置文件引用：

```jsonc
"bilibili-j": {
  "command": "uv",
  "args": [
    "tool",
    "run",
    "bilibili-mcp"
  ]
}
```

### 4. 注册工具

FastMCP 会自动暴露一个名为 `get_popular` 的工具：

#### 📦 `get_popular(top_k: int = 3)`

获取 B 站热榜视频信息，返回最多 `top_k` 个条目（最大 10 条）。

##### 返回示例：

```json
[
  {
    "title": "“战火啊，能不能在黎明前停歇一次”",
    "link": "https://b23.tv/BV1...z",
    "desc": "喜欢的朋友可以点赞投币关注一下哦，你的支持是我最大的动力！！",
    "view": 1234567,
    "like": 98765
  },
  ...
]
```

## 🛠 技术说明

- 使用 `httpx` 实现异步请求
- 通过 FastMCP 注册为标准 MCP 工具
- 支持通过 `stdio` 与 MCP 客户端通信（例如 Cursor）

## 📌 注意事项

- 仅用于学习与研究，B 站接口为公开接口，使用时请避免过于频繁访问。
- 默认 `User-Agent` 为 `"qwq"`，可根据实际情况更改为更合理的字符串。

## 📄 License

MIT License.