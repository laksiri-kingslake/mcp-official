# MCP Server Guide

## Environment Setup

```bash
# Create a new directory for our project
uv init weather
cd weather

# Create virtual environment and activate it
uv venv
source .venv/bin/activate

# Install dependencies
uv add "mcp[cli]" httpx

# Create our server file in server directory
mkdir server
cd server
touch weather.py
```

## Add Server to Claude Desktop

1. Add server configuration in claude_desktop_config.json
- Open C:\Users\admin\AppData\Roaming\Claude\claude_desktop_config.json using vscode
```bash
# windows
code $env:AppData\Claude\claude_desktop_config.json

# mac/linux
code ~/Library/Application\ Support/Claude/claude_desktop_config.json
```

2. Add below configuration block within mcpServers block
```json
        "weather": {
            "command": "uv",
            "args": [
                "--directory",
                "C:\\my\\lessions\\mcp\\mcp-official\\weather",
                "run",
                "weather.py"
            ]
        },
```
The complete configuration could be
```json
{
    "mcpServers": {
        "weather": {
            "command": "uv",
            "args": [
                "--directory",
                "C:\\my\\lessions\\mcp\\mcp-official\\weather",
                "run",
                "weather.py"
            ]
        },
        "documentation": { 
            "command": "uv",
            "args": [ 
            "--directory", 
            "C:\\my\\lessions\\mcp\\mcp-code-assistant",
            "run",
            "main.py" 
            ] 
        } 
    }
}
```

3. Exit Claude Desktop and relaunch (stop instance running in system tray as-well)

4. Expand Search and tools to see the newly added MCP server

5. Enter quries in chat
```txt
What’s the weather in Sacramento?
What are the active weather alerts in Texas?
```

## Reference
- [Build an MCP Server](https://modelcontextprotocol.io/quickstart/server)