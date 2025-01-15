Dialogue State Tracking

1. Architecture Overview
The architecture consists of three main layers:

A. User Interaction Layer
Frontend (Client Side):
User interface to input queries, visualize mind maps, and interact with the chatbot.
Components for:
Input forms for video links, revision queries, and chatbot interactions.
Graphical mind map visualization.
Quiz and feedback display.
Backend API Gateway:
Receives user queries and routes them to the appropriate service.
Acts as a mediator between the frontend and the core logic.
B. Core Processing Layer
LLM Router & Guardrails:
Central component for intent detection, input/output validation, and query routing.
Uses predefined prompts and fine-tuned logic for:
Parsing user intent.
Enforcing rules (guardrails) on inputs/outputs.
Modules:
Transcript Processing: Extracts and processes transcripts using YouTube API or Whisper.
Mind Map Generation: Parses transcripts into structured text/markdown and converts it into graphical nodes.
Question Generation: Uses RAG to generate revision questions based on the mind map content.
Chatbot: Handles quiz interactions, provides feedback, and evaluates user answers.
C. Data and Storage Layer
Databases:
Stores:
Video transcripts.
Mind map structures.
Questions and answers.
User interaction history.
Vector Store:
Manages embeddings for RAG to efficiently retrieve and generate contextually relevant questions.


Step 2: LLM Query Routing and Guardrails
Intent Detection:
The LLM identifies the intent (e.g., mind map generation, question answering, or quiz interaction).
Output: Task type and any extracted parameters (e.g., video URL, specific concept).
Guardrails Enforcement:
Validates input:
Is the video URL valid?
Does the query meet format and length requirements?
Reformulates or rejects invalid queries.
Routing:
Directs the query to the appropriate backend module based on intent.


Step 3: Core Processing
Transcript Processing Module:
For mind map generation queries, extracts and processes the video transcript.
Mind Map Module:
Converts the transcript into structured text or markdown.
Passes the structured output to the visualization component.
Question Generation Module:
Uses RAG to retrieve relevant content and generate questions for each mind map node.
Chatbot Module:
Handles interactive Q&A with the user, leveraging the LLM to provide context, evaluate answers, and give feedback.


Step 4: Validation and Output Formatting
Validation Layer:
Ensures:
Output adheres to expected formats and data types (e.g., JSON for mind maps, text for chatbot replies).
Generated content aligns with user intent and project goals (e.g., no offensive or irrelevant content).
Output Formatting:
Formats validated data for frontend rendering.


3. Enhancements and Optimizations
Feedback Loop for Guardrails:
Logs invalid queries and errors to refine LLM prompts and guardrail rules.
Caching Mechanisms:
Caches frequently requested content (e.g., transcripts, mind maps) to reduce processing overhead.
Preprocessing User Input:
Apply lightweight preprocessing (e.g., regex validation for URLs) before invoking the LLM to reduce token usage.
