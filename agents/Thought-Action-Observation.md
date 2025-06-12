# Understanding AI agents through the Thought-Action-Observation Cycle

## The core components:
- Agents work in a continuous cycle of: *thinking(Thought)-> acting(Act) and observing(Observe).*

1. Thought: The LLM part of the Agrnt decides what the next step should be.

2. Action: the agent takes an action, by calling the tools with the associated arguments.

3. Observation: The model reflects on the response from the tool.

## The Thought-Action-Observation Cycle

- the three components work together in a continuous loop. The agent uses a while loop: the loop continues until the objective of the agent has been fulfilled.
![alt text](images/image-5.png)

- In many Agent frameworks, the rules and guidelines are embedded directly into the system prompt, ensuring thtat every cycle adheres to a defined logic.
![alt text](images/image-6.png)

- The system message has:
    * The Agent's behaviour
    * The tools our agent has access to, as we described in the previous section.
    * The Thought-Action-Observation Cycle, that we bake into the LLM instructions.

- Agents iterate through  loop until the objective is fulfilled:

    - Alfred's process is cyclical.
        - It starts with a thought,then acts by calling a tool and finally oserves the outcome. If the observation had indicated an error or incomplete data, the agent could have re-entered the cycle to its approach.
    - Tool integration:
        - The ability to call a tool enables the agent to go beyond the static knowledge and retrieve real-time data, an essential aspect of many AI agents.

    - Dynamic Adaptation:
        - Each cycle allows the agent to incorporate fresh information into its reasoning, ensuring that the final answer is well-informed and accurate.

* ReAct cycle: interplay of thought,action and observation empowers AI agents to solve complex tasks iteratively.

* By applying these principles, we can design agents that not only reaon about their tasks but also effectively utilize external tools to complete them, all while continuously refining their output based on environmental feedback.

# Thought: Internal Reasoning and the ReAct approach

- Thoughts represent the Agent's internal reasoning and planning processes to solve the task.

- This utilizes the agent's LLM capacity to analye information when presented in its prompt.

- The Agent's thoughts are responsible for accessing current observations and decide what the next action(s)should be. 
- Through this process, the agent can break down comolex problems into smaller, more manageable steps, reflect on past experiences and continuously adjust its plans based on new information.

![alt text](images/image-7.png)
## The ReAct approach
- concatenationn of reaoning with acting
- Simple prompting technique that appends "let's think step by step" before letting the LLM decode the nexr tokens.

# Actions
- Actions are the concrete steps an AI agent takes to interact with its environment.

- Wheter it's browsing the web for information or controlling a physical device, each action is a deliberate operation executed by the agent.

- ![alt text](images/image-8.png)

- ![alt text](images/image-9.png)

- For an agent to work properly, the LLM must STOP generating new tokens after emitting all the tokens to define a complete action. 

## The Stop and Parse Approach

1. Generation in a Structured Format:
    - The agent outputs its intended action in a clear, predetermined format.
2. Halting further Generation:
    - Once the text defining the action has been emitted, the LLM stops generating additional tokens. This prevents extra or erroneous output.
3. Parsing th output:
    - An external parser reads the formatted action, determines which Tool to call and extracts the required parameters.

## Code agents
- An alternative approach is using Code Agents.
- The idea is: instead of outputting a simpple JSON object, a Code Agent generares ab executable code block- typically in a high-level language like python.

![alt text](images/image-10.png)

- Advantages offered :
    * Expressiveness: Code can naturally represent complex logic, including loops, conditionals and nested functions, providing greater flexibility.
    * Modularity and reusability: Generated code can unclude functions and modules that are reusable across different actions or tasks.
    * Enhanced debuggability: With a well-defined programming syntax, code errors are often easier to detect and correct.
    * Direct Integration: Code Agents can integrate directly with external libraries and APIs enabling more complex operations such as data processing or real-time decision making.
# Observe: Integrating Feedback to reflect and adapt

- Observations are how an Agent percieves the consequences of its actions.

- They provide crucial information that fuels the Agent's thought process and guides future actions.

- They are signals from the environment.

- In this phase, the agent:

    * Collects Feedback: Recieves data or confirmation that its action was successful.
    * Appends Results: Integrates the new information into its existing context, effectively updating its memory.
    * Adapts its strategy: Uses thi updated context to refine subseqyent thoughts and actions.

- This iterative incorporation of feedback ensures the agent remains dynamically aligned with its goals, constantly learning and adjusting based on real-world outcomes.

![Observations](images/image-11.png)

## How are the results appended

1. Parse the action to identify the functions to call and the arguments to use.
2. Execute the action.
3. Append the result as an Observation.