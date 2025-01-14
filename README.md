# GenAI-Project

Youtube/Podcast or Text/PDF -> Mindmap -> Flashcard/LLM Question -> Store Data

# Intended tooling:
- python as the programming language
- uv as the package manager
- ruff for linting and formatting

- langgraph for agentic flow orchestrations
- langchain for invocation of LLMs
- fastapi as the web server framework
- networkx as the domain requirement graph generator and traversaller
- pydantic for data validation


# Architecture
1. UI Frontend
2. Backend Server
   - API Gateway
   - Authentication
   - Request Handling
3. LLM Integration
   - Endpoint
   - API Key
   - Request Formatting
   - Response Handling
4. Business Logic
   - Context Management
   - Intent Recognition
   - Response Generation
   - Domain Requirements
   - Agentic Flow
   - Function Calling
   - Error Handling
5. Data Storage
   - Session Data
   - Output Download
6. Security
   - Rate Limiting
