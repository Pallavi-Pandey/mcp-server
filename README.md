# MCP Server Example: Documentation Search Tool

This project demonstrates how to build a simple MCP (Model Control Protocol) server that allows AI assistants to search through documentation for popular AI/ML libraries including LangChain, LlamaIndex, and OpenAI.

## Features

- Search documentation for multiple libraries (LangChain, LlamaIndex, OpenAI)
- Uses Google Search API via Serper to find relevant documentation pages
- Extracts and returns text content from documentation pages
- Built with FastMCP for easy integration with AI assistants

## Prerequisites

- Python 3.10 or higher
- Serper API key (for Google Search functionality)

## Installation

1. Clone this repository
2. Create a virtual environment:
   ```bash
   python3 -m venv .venv
   source .venv/bin/activate
   ```
3. Install dependencies:
   ```bash
   pip install -e .
   ```
4. Create a `.env` file with your Serper API key:
   ```
   SERPER_API_KEY=your_api_key_here
   ```

## Usage

Run the MCP server:

```bash
source .venv/bin/activate
python3 main.py
```

The server will start and listen for requests on the standard input/output (stdio) transport.

## How It Works

The server exposes a single tool called `get_docs` that takes two parameters:
- `query`: The search query (e.g., "Chroma DB")
- `library`: The library to search in (e.g., "langchain")

When called, the tool:
1. Constructs a site-specific search query
2. Sends the query to Google via the Serper API
3. Fetches the content of the top search results
4. Returns the extracted text content

## Supported Libraries

- LangChain: `langchain`
- LlamaIndex: `llama-index`
- OpenAI: `openai`

## License

MIT