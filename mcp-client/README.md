# MCP Client Guide

## Setting Up Environment

1. Setup and activate python environment
```bash
# Create project directory
uv init mcp-client
cd mcp-client

# Create virtual environment
uv venv

# Activate virtual environment
# On Windows:
.venv\Scripts\activate
# On Unix or macOS:
source .venv/bin/activate

# Install required packages
uv add mcp anthropic python-dotenv

# Remove boilerplate files
# On Windows:
del main.py
# On Unix or macOS:
rm main.py

# Create our main file
touch client.py
```

## Running the Client Along with a stdio Server
```bash
# uv run client.py <server-path> # server both .py and .js server files are supported

uv run client.py C:\\my\\lessions\\mcp\\mcp-official\\weather\\server\\weather.py
```