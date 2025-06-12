# Smolagents
- provides LLMs with the agency to interact with the real world.

- agents operate as multi-step agents.

- Code agents are the default agent type in smolagents. They generate Python tool calls to perform actions, achieving action representations that are efficient, epressive and accurate.

- Their streamlined approach reduces the number of required actions, simplifies complex operations and enables reuse of existing code functions. Smolagents provide a lightweight framework for building code agents, implanted in approximately 1000 lines of code.

- In a multiple-step agent process, the LLM writes and executes actions, typically involving external tool calls. Traditional approaches use a JSON format to specify tool names and arguments as strings, which the system must parse to determine which tool to execute.

![alt text](image.png)

- The system prompt is stored in a SystemPromptStep and the user query is logged in a TaskStep.

- The following loop is executed:
    - Method agent.write_memory_to_messages() writes the agent's logs into a list of LLM-readable chat messages.
    - These messages are sent to a Model, which generates a completion.
    - The completion is parsed to extract the action, which in our case should be a code snippet we're working with a CodeAgent.
    - The action is executed.
    - The results are logged into memory in ActionStep.

- At the end of each step, if the agent includes any function calls(in agent.step_callback) they are executed.

