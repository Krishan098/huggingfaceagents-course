# LangGraph

- manages the control flow of applications that integrate an LLM.

- Langchain provides a standard interface to interact with models and other components, useful for retrieval, LLM calls and tools calls. The classes from LangChain might be used in LangGraph but do not HAVE to be used.

## When to use 

### Control vs freedom 

- When designing AI applications, you face a fundamental trade-off between control and freedom.

    - *Freedom* gives your LLM more room to be creative and tackle unexpected problems.

    - *Control* allows you to ensure predictable behaviour and maintain guardrails.

- LangGraph is useful when we need "Control" on the execution of our agent.

- It gives us the tools to build an application that follows a predictable process while still leveraging the power of LLMs.

## Excels at

-  *Multi-step reasoning processes* that need explicit control on the flow.

- *Applications requiring persistence of state* between steps

- *Systems that combine deterministic logic with AI capabilities*

- *Workflows that need human-in-the-loop interventions*

- *Complex agent architectures* with multiple components working together

## Working

- *Nodes* represent individual processing steps(like calling an LLM, using a tool, or making a decision).

- *Edges* define the possible transitions between steps.

- *State* is user defined and maintained and passed between nodes during execution. 