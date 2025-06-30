# 🌦️ Real-Time Weather Tool via MCP-Server for ClaudeAI

This project is a custom **MCP-Server (Model-Context Protocol Server)** built using **Python** that integrates **real-time weather information and alerts** directly into **ClaudeAI** via the `claude_desktop_config` file. By registering this server as a tool, you can allow Claude to fetch weather data and provide contextual responses in a natural language conversation.

---

## 📌 Project Overview

This MCP-Server acts as a bridge between local weather-fetching logic and ClaudeAI's tool system. Once set up, you can interact with the Claude desktop app and trigger the tool by prompts like:

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
```

### 2. Install Python Dependencies

Make sure you have Python 3.10+ installed.

```bash
pip install -r requirements.txt
```

You may need to create a virtual environment first:

```bash
# Linux/macOS
python -m venv venv && source venv/bin/activate

# Windows
.\venv\Scripts\activate
```

---

## 🚀 How to Run

### Step 1: Run the Weather Tool Server

```bash
python weather.py
```

This starts your local MCP weather server.

### Step 2: Register the Tool in `claude_desktop_config`

1. Open the `claude_desktop_config.json` file on your system
2. Find the `arguments` field
3. Set the path to your script like this:

```json
"arguments": [
  "python",
  "C:/full/path/to/weather.py"
]
```

4. Save and restart ClaudeAI

### Step 3: Use the Tool in ClaudeAI

- Launch ClaudeAI Desktop
- A **new tool** will appear
- Prompt Claude with weather-related queries like:
  - *"What's the current weather in Mumbai?"*
  - *"Are there any severe weather alerts near me?"*
- Claude will ask for permission to use the tool. Click **Allow**

---

## 📋 Features

- **Real-time Weather Data**: Get current weather conditions for any location
- **Weather Alerts**: Receive severe weather warnings and advisories
- **Natural Language Interface**: Ask weather questions in plain English
- **Location-based Queries**: Support for city names, coordinates, and regional queries
- **Integration with Claude**: Seamless conversation flow with weather context

---

## 🔧 Configuration

### API Keys

You may need to configure API keys for weather services:

1. Sign up for a weather API service (e.g., OpenWeatherMap, WeatherAPI)
2. Add your API key to the configuration file or environment variables
3. Update the `weather.py` script with your preferred weather service

### Location Settings

- The tool can work with city names, ZIP codes, or coordinates
- Configure default location settings if needed
- Ensure proper geocoding for accurate weather data

---

## 📄 File Structure

```
weather-mcp-server/
├── weather.py           # Main MCP server script
├── requirements.txt     # Python dependencies
├── config.json         # Configuration file (optional)
├── README.md           # This file
└── [logs]/             # Log files (optional)
    └── weather.log
```

---

## 🌍 Supported Weather Data

- **Current Conditions**: Temperature, humidity, wind speed, visibility
- **Weather Alerts**: Storm warnings, heat advisories, flood alerts
- **Extended Information**: UV index, air quality, precipitation
- **Location Services**: City-based and coordinate-based queries

---

## 🤝 Contributing

Feel free to submit issues and pull requests to improve this tool. Make sure to:

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test with different weather scenarios
5. Submit a pull request

---

## 📜 License

This project is open source. Please check the LICENSE file for details.

---

## 🆘 Support

If you encounter any issues:

1. Check that Python 3.10+ is installed
2. Verify your API keys are configured correctly
3. Ensure the path in `claude_desktop_config.json` is correct
4. Confirm ClaudeAI Desktop has been restarted after configuration
5. Check internet connectivity for weather data fetching

For additional help, please open an issue in the repository.

---

## ⚠️ Important Notes

- This tool requires an active internet connection to fetch weather data
- API rate limits may apply depending on your chosen weather service
- Location accuracy depends on the geocoding service used
- Weather alerts may vary by region and service provider
