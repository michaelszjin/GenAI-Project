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
1. Requirement Analysis
Key Features:
- Transcript extraction from YouTube videos.
- LLM for parsing and creating mind maps.
- Graphical visualization of mind maps.
- RAG (Retrieval-Augmented Generation) for question generation.
- Chatbot for user interaction and answer evaluation.

Tools and Technologies:
- Backend: Python with Flask/Django or Node.js.
- Frontend: React.js/Vue.js for user interface and mind map visualization.
- LLM Integration: OpenAI API or Hugging Face Transformers.
- Transcript Extraction: YouTube API or third-party libraries like yt-dlp + whisper for transcript generation.
- Database: PostgreSQL/MySQL for storing video data, mind maps, and user activity.
- Visualization: D3.js or libraries like react-flow for mind map rendering.


2. Workflow Design
Transcript Extraction:
- Use YouTube API to fetch the video ID and details.
- Extract or generate transcripts using the YouTube API or tools like Whisper for better accuracy.

Text Parsing and Mind Map Generation:
- Use an LLM to analyze the transcript and generate a structured mind map in text/markdown format.
- Text structure: Main Concept -> Subconcept -> Detail
- Convert the text/markdown structure to a graphical mind map using libraries like D3.js or React Flow.

Question Generation (RAG):
-Use a vector database (e.g., Pinecone, Weaviate) to store node embeddings.
-Implement RAG to create questions for each node using a prompt to the LLM.

Chatbot for Revision and Feedback:
-Integrate a chatbot that fetches questions from RAG and evaluates user responses.
-Provide hints, explanations, or corrections using the LLM.
