Requirements List:
- Create new mindmap
  - Check URL
  - Ask user to provide name of mindmap
- Generate question from existing mindmap
  - Check if there is existing mindmap
  - Ask which mindmap to sample question from

Flow Chart:

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

```
