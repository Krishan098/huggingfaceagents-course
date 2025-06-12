# SmolAgents

- CodeAgents are the primary type of agent in smolagents. Instead of JSON or text, these agents produce Python code to perform actions. 

- ToolCallingAgents are the second type of agent supported by smolagents. These rely on JSON/text blobs that the system must parse and interpret to execute actions.

- Tools are the functions that the LLM can use with an agentic system and they act as the essential building blocks for agent behaviour. 

- Retrieval agents allow models access to knowledge bases, making it possible to search, synthesize and to retrieve information from multiple sources. They leverage vector stores for efficient retrieval and implement Retrieval-Augmented Generation patterns. These are particularly used for integrating web search with custom knowledge bases while maintaing conversation context through memory systems. 

- Multi-Agent systems involves orchestrating multiple agents effectively. By combining agents with different capabilities- such as a web search agent with a code execution agent - you can create more sophisticated solutions. 

- Vision and Browser agents incorporate (VLMs), enabling them to process and interpret visual information.

## Links

- [smolagents documentation](https://huggingface.co/docs/smolagents/index)

- [Building effective agents- Anthropic](https://www.anthropic.com/engineering/building-effective-agents)

- [Agent Guidelines](https://huggingface.co/docs/smolagents/tutorials/building_good_agents)

- [LangGraph Agents](https://langchain-ai.github.io/langgraph/#core-benefits)

- [Function Calling guide](https://platform.openai.com/docs/guides/function-calling)

- [RAG best practices](https://www.pinecone.io/learn/retrieval-augmented-generation/)