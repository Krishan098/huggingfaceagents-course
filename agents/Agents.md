# huggingfaceagents-course

# Agent

- An AI model capable of reasoning, planning and interacting with its environment.
- We call it agent because it has agency, aka it has the ability to interact with the environment.
* An agent is a system that leverages an AI model to interact with its environment in order to achieve a user-defined objective. It combines reasoning, planning and the execution of actions to fulfill tasks.

- Agent has 2 main parts:

## The Brain(AI Model):
- This is where all the thinking happens. The AI model handles reasoning and planning.

## The Body(Capabilities and Tools):
- This part represents everything the Agent is equipped to do.
- The scope of possible actions depends on what the agent has been equipped with.

## SPECTRUM OF AGENCY

- simple processor: agent has no impact on program flow; process_llm_output(llm_response)

- router: agent output determines basic control flow; if llm_decision(): path_a() else: path_b()

- Tool caller: Agent output determines function execution

- Multi-step agent: agent output controls iteration and program continuation

- Multi-Agent: One agentic workflow can start another agentic workflow.