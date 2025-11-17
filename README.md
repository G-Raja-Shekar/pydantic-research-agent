# Pydantic Research Agent

An intelligent research assistant built with [Pydantic AI](https://ai.pydantic.dev/) that leverages AI agents to answer questions by performing web research. The agent uses DuckDuckGo's Instant Answer API to gather information and provides comprehensive, well-structured responses.

## Features

- 🤖 **AI-Powered Research**: Uses Gemini 2.5 Flash model to intelligently research topics
- 🔍 **Web Search Integration**: Leverages DuckDuckGo Instant Answer API for real-time information retrieval
- 💬 **Interactive Chat**: Continuous conversation with message history support
- 📊 **Comprehensive Logging**: Integrated with Logfire for detailed observability and monitoring
- 🔧 **Tool-Based Architecture**: Extensible agent system using Pydantic AI's tool framework

## Prerequisites

- Python 3.8 or higher
- Logfire account and API token ([sign up here](https://logfire.pydantic.dev/))
- Gemini API access (configured through Pydantic AI)

## Installation

1. Clone the repository:

```bash
git clone https://github.com/G-Raja-Shekar/pydantic-research-agent.git
cd pydantic-research-agent
```

2. Install dependencies:

```bash
pip install -r requirements.txt
```

3. Create a `.env` file in the project root with the following variables:

```env
LOGFIRE_WRITE_TOKEN=your_logfire_token_here
ENVIRONMENT=development
SERVICE_NAME=pydantic-research-agent
```

## Usage

Run the agent:

```bash
python main.py
```

The agent will start an interactive chat session. You can ask questions on various topics:

```
Chat with the agent (type 'exit', 'quit', or 'bye' to end)
------------------------------------------------------------
You: What is AI?
Agent: Artificial intelligence (AI) is the capacity of computational systems to execute tasks that typically necessitate human intelligence...

You: What is Datascience?
Agent: Data science is an interdisciplinary academic field that combines various disciplines to extract knowledge and insights from data...
```

To exit, type `exit`, `quit`, or `bye`.

## Project Structure

```
pydantic-research-agent/
├── main.py              # Main application file with agent logic
├── requirements.txt     # Python dependencies
├── sample_logs.txt     # Example interaction logs
├── .env                # Environment variables (create this)
└── README.md           # This file
```

## How It Works

1. **Agent Initialization**: The agent is configured with the Gemini 2.5 Flash model and equipped with a research tool
2. **User Input**: Users ask questions through the interactive chat interface
3. **Tool Invocation**: When research is needed, the agent calls the `research_topic` tool
4. **Web Search**: The tool queries DuckDuckGo's Instant Answer API for relevant information
5. **Response Generation**: The agent synthesizes the research findings into a comprehensive answer
6. **Logging**: All interactions are logged to Logfire for monitoring and analysis

## Key Components

### Research Tool

The `research_topic` function integrates with DuckDuckGo's Instant Answer API to gather information:

- Fetches abstracts, definitions, and related topics
- Handles API errors and edge cases gracefully
- Provides detailed logging for debugging

### Agent Configuration

- **Model**: Gemini 2.5 Flash
- **Tools**: `research_topic` for web search
- **System Prompt**: Configured as a helpful research assistant

### Logging & Monitoring

Integrated with Logfire for:

- User input tracking
- Agent output monitoring
- Research operation tracing
- Error logging and debugging

## Dependencies

- `pydantic-ai`: AI agent framework
- `python-dotenv`: Environment variable management
- `logfire`: Observability and logging
- `httpx`: HTTP client for API requests

## Environment Variables

| Variable              | Description                                            | Required |
| --------------------- | ------------------------------------------------------ | -------- |
| `LOGFIRE_WRITE_TOKEN` | Your Logfire API token                                 | Yes      |
| `ENVIRONMENT`         | Deployment environment (e.g., development, production) | Yes      |
| `SERVICE_NAME`        | Name of the service for Logfire tracking               | Yes      |

## Example Interactions

See `sample_logs.txt` for detailed examples of agent interactions, including:

- AI and machine learning queries
- Data science definitions
- Timestamp and logging information

## Limitations

- The DuckDuckGo Instant Answer API may not have detailed information for all topics
- Redirects (301/302) typically indicate no instant answer is available
- Best results for well-known topics and general queries

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is open source and available under the MIT License.

## Acknowledgments

- Built with [Pydantic AI](https://ai.pydantic.dev/)
- Powered by [Gemini 2.5 Flash](https://deepmind.google/technologies/gemini/)
- Monitoring by [Logfire](https://logfire.pydantic.dev/)
- Search powered by [DuckDuckGo Instant Answer API](https://duckduckgo.com/api)

## Support

For issues and questions:

- Open an issue on GitHub
- Check the [Pydantic AI documentation](https://ai.pydantic.dev/)
- Review the Logfire project URL printed when running the application
