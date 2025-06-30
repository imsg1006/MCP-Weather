# 🌦️ Real-Time Weather Tool via MCP-Server for ClaudeAI

This project is a custom **MCP-Server (Model-Context Protocol Server)** built using **Python** that integrates **real-time weather information and alerts** directly into **ClaudeAI** via the `claude_desktop_config` file. By registering this server as a tool, you can allow Claude to fetch weather data and provide contextual responses in a natural language conversation.

---

## 📌 Project Overview

This MCP-Server acts as a bridge between local weather-fetching logic and ClaudeAI’s tool system. Once set up, you can interact with the Claude desktop app and trigger the tool by prompts like:

> "What's the current weather in Delhi?"  
> "Are there any weather alerts for my area?"

Claude will ask for permission to use the tool, and upon granting it, fetches and responds using your locally-run weather script.

---

## ⚙️ Tech Stack

- **Python** – core backend for the MCP server and weather logic  
- **MCP Server Protocol** – to register tools with ClaudeAI  
- **Command-line Interface** – for running the tool locally  
- **ClaudeAI Desktop Configuration** – for tool registration via the config file  

---

## 🛠️ Setup Instructions

### 1. Clone this Repository

```bash
git clone https://github.com/your-username/weather-mcp-server.git
cd weather-mcp-server
