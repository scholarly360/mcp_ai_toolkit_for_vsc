# MCP Tools Integration with Python

This Python script demonstrates how to integrate AI models (Azure Foundary and Github) with MCP (Model Context Protocol) 
tools to create an intelligent web exploration assistant. Here's what it does:

## Overview

The script creates a chatbot that can interact with web pages using Playwright automation tools through the MCP protocol. It combines Azure OpenAI's GPT-4o-mini model with browser automation capabilities to navigate websites, take screenshots, and provide content summaries.

## Key Components

### MCPClient Class
The main orchestrator that manages connections between the AI model and MCP servers. It handles multiple server connections and maintains a mapping of available tools.

### Connection Methods
Supports both STDIO and SSE (Server-Sent Events) transport protocols for connecting to different types of MCP servers.

### Tool Integration
Automatically discovers and registers tools from connected MCP servers, making them available to the AI model for function calling.

### Conversation Loop
Implements a complete chat cycle where the model can call tools, receive results, and provide responses based on the tool outputs.

## Example Use Case

The script is configured to:
1. Connect to a Playwright MCP server for web automation
2. Navigate to CNN.com or any website
3. Provide a summary of the website content

## Key Features

- **Multi-server support**: Can connect to multiple MCP servers simultaneously
- **Automatic tool discovery**: Dynamically finds and registers available tools
- **Error handling**: Includes proper cleanup and error management
- **Flexible messaging**: Supports various message types including system, user, assistant, and tool messages

## Requirements

- Azure AI credentials for the language model
- MCP protocol support
- Playwright for web automation (installed via npx)

## Architecture Benefits

This architecture enables creating sophisticated AI assistants that can perform real-world tasks beyond text generation, such as:
- Web browsing and navigation
- Data extraction from websites
- Automated interactions with various services through MCP-compatible tools
- Screenshot capture and visual analysis
- Multi-step web automation workflows

## Installation & Usage

```bash
pip install mcp azure-ai-inference
python app.py
```

The script requires setting up an `AZURE_AI_API_KEY` environment variable for authentication with Azure OpenAI services.
