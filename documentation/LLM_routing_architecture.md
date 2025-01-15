Requirements List:
- Create new mindmap
  - Check URL
  - Ask user to provide name of mindmap
- Generate question from existing mindmap
  - Check if there is existing mindmap
  - Ask which mindmap to sample question from

Agentic Flow - Directed Acyclic Graph (DAG):  
We begin by traversing the node from 'Start', and will only activate the next list of required nodes  once all pre-requisite nodes have been satisfied.
Once the end is reached, then the process is complete.

```mermaid
graph TD;
    Start-->IntentExpert;
    IntentExpert-->MindMap_Path;
    IntentExpert-->Question_Path;
    IntentExpert-->Guardrails;
    MindMap_Path-->Transcript_Extractor;
    Transcript_Extractor-->LLM_Summariser;
    LLM_Summariser-->MindMapper;
    LLM_Summariser-->Question_Path;
    Question_Path-->RAG_LLM;
    MindMapper-->ResponseExpert;
    RAG_LLM-->ResponseExpert;

```
