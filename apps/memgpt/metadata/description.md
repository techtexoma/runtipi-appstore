MemGPT allows you to build LLM agents with long term memory & custom tools

Discord Twitter Follow arxiv 2310.08560 Documentation

MemGPT makes it easy to build and deploy stateful LLM agents with support for:

Long term memory/state management
Connections to external data sources (e.g. PDF files) for RAG
Defining and calling custom tools (e.g. google search)

Quickstart (CLI)
You can create and chat with a MemGPT agent by running memgpt run in your CLI. The run command supports the following optional flags (see the CLI documentation for the full list of flags):

--agent: (str) Name of agent to create or to resume chatting with.
--first: (str) Allow user to sent the first message.
--debug: (bool) Show debug logs (default=False)
--no-verify: (bool) Bypass message verification (default=False)
--yes/-y: (bool) Skip confirmation prompt and use defaults (default=False)
You can view the list of available in-chat commands (e.g. /memory, /exit) in the CLI documentation.

Dev portal (alpha build)
MemGPT provides a developer portal that enables you to easily create, edit, monitor, and chat with your MemGPT agents. The easiest way to use the dev portal is to install MemGPT via docker (see instructions below).

image
Quickstart (Server)
Option 1 (Recommended): Run with docker compose

Install docker on your system
Clone the repo: git clone https://github.com/cpacker/MemGPT.git
Copy-paste .env.example to .env and optionally modify
Run docker compose up
Go to memgpt.localhost in the browser to view the developer portal
Option 2: Run with the CLI:

Run memgpt server
Go to localhost:8283 in the browser to view the developer portal
Once the server is running, you can use the Python client or REST API to connect to memgpt.localhost (if you're running with docker compose) or localhost:8283 (if you're running with the CLI) to create users, agents, and more. The service requires authentication with a MemGPT admin password; it is the value of MEMGPT_SERVER_PASS in .env.

Supported Endpoints & Backends
MemGPT is designed to be model and provider agnostic. The following LLM and embedding endpoints are supported:

Provider	LLM Endpoint	Embedding Endpoint
OpenAI	✅	✅
Azure OpenAI	✅	✅
Google AI (Gemini)	✅	❌
Anthropic (Claude)	✅	❌
Groq	✅ (alpha release)	❌
Cohere API	✅	❌
vLLM	✅	❌
Ollama	✅	✅
LM Studio	✅	❌
koboldcpp	✅	❌
oobabooga web UI	✅	❌
llama.cpp	✅	❌
HuggingFace TEI	❌	✅
When using MemGPT with open LLMs (such as those downloaded from HuggingFace), the performance of MemGPT will be highly dependent on the LLM's function calling ability. You can find a list of LLMs/models that are known to work well with MemGPT on the #model-chat channel on Discord, as well as on this spreadsheet.