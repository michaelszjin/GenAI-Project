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
    Start-->IntentExpert_LLM;
    IntentExpert_LLM-->A{MindMap_Path};
    IntentExpert_LLM-->B{Question_Path};
    IntentExpert_LLM-->Guardrails;
    A{MindMap_Path}-->Transcript_Extractor_Fn;
    Transcript_Extractor_Fn-->Summariser_LLM;
    Summariser_LLM-->MindMapper_Fn;
    Summariser_LLM-->B{Question_Path};
    B{Question_Path}-->RAG_LLM;
    MindMapper_Fn-->ResponseExpert_LLM;
    RAG_LLM-->ResponseExpert_LLM;

```
