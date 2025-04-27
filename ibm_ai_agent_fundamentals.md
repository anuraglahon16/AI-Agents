# AI Agent Fundamentals - IBM Research Notes

## Definition of AI Agents

An artificial intelligence (AI) agent refers to a system or program that is capable of autonomously performing tasks on behalf of a user or another system by designing its workflow and utilizing available tools.

AI agents can encompass a wide range of functionalities beyond natural language processing including decision-making, problem-solving, interacting with external environments and executing actions.

These agents can be deployed in various applications to solve complex tasks in various enterprise contexts from software design and IT automation to code-generation tools and conversational assistants. They use the advanced natural language processing techniques of large language models (LLMs) to comprehend and respond to user inputs step-by-step and determine when to call on external tools.

## How AI Agents Work

At the core of AI agents are large language models (LLMs). For this reason, AI agents are often referred to as LLM agents. Traditional LLMs, such as IBM® Granite™ models, produce their responses based on the data used to train them and are bounded by knowledge and reasoning limitations. In contrast, agentic technology uses tool calling on the backend to obtain up-to-date information, optimize workflows and create subtasks autonomously to achieve complex goals.

In this process, the autonomous agent learns to adapt to user expectations over time. The agent's ability to store past interactions in memory and plan future actions encourages a personalized experience and comprehensive responses. This tool calling can be achieved without human intervention and broadens the possibilities for real-world applications of these AI systems.

### Agentic Components

Agents can be defined by these three stages or agentic components:

1. **Goal initialization and planning**: Although AI agents are autonomous in their decision-making processes, they require goals and predefined rules defined by humans. There are three main influences on autonomous agent behavior:
   - The team of developers that design and train the agentic AI system
   - The team that deploys the agent and provides the user with access to it
   - The user that provides the AI agent with specific goals to accomplish and establishes available tools to use

   Given the user's goals and the agent's available tools, the AI agent then performs task decomposition to improve performance. Essentially, the agent creates a plan of specific tasks and subtasks to accomplish the complex goal.

   For simple tasks, planning is not a necessary step. Instead, an agent can iteratively reflect on its responses and improve them without planning its next steps.

2. **Reasoning using available tools**: AI agents base their actions on the information they perceive. Often, AI agents do not have the full knowledge base needed for tackling all subtasks within a complex goal. To remedy this, AI agents use their available tools. These tools can include external data sets, web searches, APIs and even other agents. After the missing information is retrieved from these tools, the agent can update its knowledge base and perform agentic reasoning. This means that each step of the way, the agent reassesses its plan of action and self-corrects, allowing for informed decision-making.

3. **Learning and reflection**: AI agents use feedback mechanisms, such as other AI agents and human-in-the-loop (HITL), to improve the accuracy of their responses. Feedback mechanisms improve the AI agent's reasoning and accuracy, which is commonly referred to as iterative refinement. To avoid repeating the same mistakes, AI agents can also store data about solutions to previous obstacles in a knowledge base.

## Agentic versus Non-agentic AI Chatbots

AI chatbots use conversational AI techniques such as natural language processing (NLP) to understand user questions and automate responses to them. These chatbots are a modality whereas agency is a technological framework.

Non-agentic AI chatbots are ones without available tools, memory and reasoning. They can only reach short-term goals and cannot plan ahead. As we know them, non-agentic chatbots require continuous user input to respond. They can produce responses to common prompts that most likely align with user expectations but perform poorly on questions unique to the user and their data. Since these chatbots do not hold memory, they cannot learn from their mistakes if their responses are unsatisfactory.

In contrast, agentic AI chatbots learn to adapt to user expectations over time, providing a more personalized experience and comprehensive responses. They can complete complex tasks by creating subtasks without human intervention and considering different plans. These plans can also be self-corrected and updated as needed. Agentic AI chatbots, unlike non-agentic ones, assess their tools and use their available resources to fill in information gaps.

## Reasoning Paradigms

There is not one standard architecture for building AI agents. Several paradigms exist for solving multi-step problems:

### ReAct (Reasoning and Action)

With the ReAct paradigm, we can instruct agents to "think" and plan after each action taken and with each tool response to decide which tool to use next. These Think-Act-Observe loops are used to solve problems step by step and iteratively improve upon responses.

Through the prompt structure, agents can be instructed to reason slowly and to display each "thought". The agent's verbal reasoning gives insight into how responses are formulated. In this framework, agents continuously update their context with new reasoning. This can be interpreted as a form of Chain-of-Thought prompting.

### ReWOO (Reasoning WithOut Observation)

The ReWOO method, unlike ReAct, eliminates the dependence on tool outputs for action planning. Instead, agents plan upfront. Redundant tool usage is avoided by anticipating which tools to use upon receiving the initial prompt from the user. This is desirable from a human-centered perspective since the user can confirm the plan before it is executed.

The ReWOO workflow is made up of three modules. In the planning module, the agent anticipates its next steps given a user's prompt. The next stage entails collecting the outputs produced by calling these tools. Lastly, the agent pairs the initial plan with the tool outputs to formulate a response. This planning ahead can greatly reduce token usage and computational complexity as well as the repercussions of intermediate tool failure.

## Types of AI Agents

AI agents can be developed to have varying levels of capabilities. A simple agent may be preferred for straightforward goals to limit unnecessary computational complexity. In order of simplest to most advanced, there are 5 main agent types:

### 1. Simple Reflex Agents

Simple reflex agents are the simplest agent form that grounds actions on perception. This agent does not hold any memory, nor does it interact with other agents if it is missing information. These agents function on a set of so-called reflexes or rules. This means that the agent is preprogrammed to perform actions that correspond to certain conditions being met.

If the agent encounters a situation that it is not prepared for, it cannot respond appropriately. The agents are only effective in environments that are fully observable granting access to all necessary information.

Example: A thermostat that turns on the heating system at a set time every night. The condition-action rule here is, for instance, if it is 8 PM, then the heating is activated.

### 2. Model-based Reflex Agents

Model-based reflex agents use both their current perception and memory to maintain an internal model of the world. As the agent continues to receive new information, the model is updated. The agent's actions depend on its model, reflexes, previous precepts and current state.

These agents, unlike simple reflex agents, can store information in memory and can operate in environments that are partially observable and changing. However, they are still limited by their set of rules.

Example: A robot vacuum cleaner. As it cleans a dirty room, it senses obstacles such as furniture and adjusts around them. The robot also stores a model of the areas it has already cleaned to not get stuck in a loop of repeated cleaning.

### 3. Goal-based Agents

Goal-based agents have an internal model of the world and also a goal or set of goals. These agents search for action sequences that reach their goal and plan these actions before acting on them. This search and planning improve their effectiveness when compared to simple and model-based reflex agents.

Example: A navigation system that recommends the fastest route to your destination. The model considers various routes that reach your destination, or in other words, your goal. In this example, the agent's condition-action rule states that if a quicker route is found, the agent recommends that one instead.

### 4. Utility-based Agents

Utility-based agents select the sequence of actions that reach the goal and also maximize utility or reward. Utility is calculated using a utility function. This function assigns a utility value, a metric measuring the usefulness of an action or how "happy" it will make the agent, to each scenario based on a set of fixed criteria.

The criteria can include factors such as progression toward the goal, time requirements, or computational complexity. The agent then selects the actions that maximize the expected utility. Hence, these agents are useful in cases where multiple scenarios achieve a desired goal and an optimal one must be selected.

Example: A navigation system that recommends the route to your destination that optimizes fuel efficiency and minimizes the time spent in traffic and the cost of tolls. This agent measures utility through this set of criteria to select the most favorable route.

### 5. Learning Agents

Learning agents hold the same capabilities as the other agent types but are unique in their ability to learn. New experiences are added to their initial knowledge base, which occurs autonomously. This learning enhances the agent's ability to operate in unfamiliar environments. Learning agents may be utility or goal-based in their reasoning and are comprised of four main elements:

- **Learning**: This improves the agent's knowledge by learning from the environment through its precepts and sensors.
- **Critic**: This provides feedback to the agent on whether the quality of its responses meets the performance standard.
- **Performance**: This element is responsible for selecting actions upon learning.
- **Problem generator**: This creates various proposals for actions to be taken.

Example: Personalized recommendations on e-commerce sites. These agents track user activity and preferences in their memory. This information is used to recommend certain products and services to the user. The cycle repeats each time new recommendations are made. The user's activity is continuously stored for learning purposes. In doing so, the agent improves its accuracy over time.

## Use Cases of AI Agents

### Customer Experience
AI agents can be integrated into websites and apps to enhance the customer experience by serving as a virtual assistants, providing mental health support, simulating interviews and other related tasks. There are many no-code templates for user implementation, making the process of creating these AI agents even easier.

### Healthcare
AI agents can be used for various real-world healthcare applications. Multi-agent systems can be particularly useful for problem-solving in such settings. From treatment planning for patients in the emergency department to managing drug processes, these systems save the time and effort of medical professionals for more urgent tasks.

### Emergency Response
In case of natural disasters, AI agents can use deep learning algorithms to retrieve the information of users on social media sites that need rescue. The locations of these users can be mapped to assist rescue services in saving more people in less time. Therefore, AI agents can greatly benefit human life in both mundane, repetitive tasks and life-saving situations.

### Finance and Supply Chain
Agents can be designed to analyze real-time financial data, anticipate future market trends and optimize supply chain management. The customizability of autonomous AI agents provides us with outputs personalized to our unique data. When working with financial data, it is important to enforce security measures for data privacy.

## Benefits of AI Agents

### Task Automation
With the ongoing advancements in generative AI and machine learning, there is a growing interest in workflow optimization using AI, or intelligent automation. AI agents are AI tools that can automate complex tasks that would otherwise require human resources. This translates to goals being reached inexpensively, rapidly and at scale. In turn, these advancements mean human agents do not need to provide direction to the AI assistant for creating and navigating its tasks.

### Greater Performance
Multi-agent frameworks tend to outperform singular agents. This is because the more plans of action are available to an agent, the more learning and reflection occur. An AI agent incorporating knowledge and feedback from other AI agents specializing in related areas can be useful for information synthesis. This backend collaboration of AI agents and the ability to fill information gaps are unique to agentic frameworks, making them a powerful tool and a meaningful advancement in artificial intelligence.

### Quality of Responses
AI agents provide responses that are more comprehensive, accurate and personalized to the user than traditional AI models. This is extremely important to us as users since higher-quality responses typically yield a better customer experience. As previously described, this is made possible through exchanging information with other agents, using external tools and updating their memory stream. These behaviors emerge on their own and are not preprogrammed.

## Risks and Limitations

### Multi-agent Dependencies
Certain complex tasks require the knowledge of multiple AI agents. Orchestration of these multi-agent frameworks has a risk of malfunction. Multi-agent systems built on the same foundation models may experience shared pitfalls. Such weaknesses could cause a system-wide failure of all involved agents or expose vulnerability to adverse attacks. This highlights the importance of data governance in building foundation models and thorough training and testing processes.

### Infinite Feedback Loops
The convenience of the hands-off reasoning for human users using AI agents also comes with its risks. Agents that are unable to create a comprehensive plan or reflect on their findings, may find themselves repeatedly calling the same tools, invoking infinite feedback loops. To avoid these redundancies, some level of real-time human monitoring may be used.

### Computational Complexity
Building AI agents from scratch is both time-consuming and can also be very computationally expensive. The resources required for training a high-performance agent can be extensive. Additionally, depending on the complexity of the task, agents can take several days to complete tasks.

### Data Privacy
If mismanaged, the integration of AI agents with business processes and customer management systems can raise some serious security concerns. For example, let's imagine AI agents are leading the software development process, taking coding copilots to the next level, or determining pricing for clients without any human oversight or guardrails. The results of such a scenario could be detrimental due to the experimental and often unpredictable behavior of agentic AI. Hence, it is important that AI providers such as IBM, Microsoft and OpenAI remain proacti
(Content truncated due to size limit. Use line ranges to read in chunks)