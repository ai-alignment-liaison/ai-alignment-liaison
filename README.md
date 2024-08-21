# AI Alignment Liaison

## Overview
The AI Alignment Liaison is a generative AI system designed to advise AI teams on how to align their AI development processes to a set of human values, ethical standards, and compliance requirements. It is a human-in-the-loop platform that guides teams through identifying core values, translating these into potential responsible AI requirements for a given product, strategizing on how to meet each requirement, and strategizing on how to validate that the requirements were indeed met.

```mermaid
%%{init: {'theme': 'default'}}%%
graph TD

%% Nodes
user_prompt["<b>User Prompt</b>"]:::font_increase
rag_process["<b><i class='fa fa-image'></i> <a rel='noopener' href='https://www.mermaidchart.com/raw/70a03a06-cf0f-4efb-af32-0fa6b9f7f08b?theme=light&version=v0.1&format=svg' target='_blank'>RAG Inference\nPipeline</a></b>"]:::font_increase
collect_user_context_process["<b><i class='fa fa-image'></i> <a rel='noopener' href='https://www.mermaidchart.com/raw/385cd106-7ad6-46e6-aad1-0cc96357d321?theme=light&version=v0.1&format=svg' target='_blank'>Collect User Context</a></b>"]:::font_increase

subgraph llm_receiver_pipeline["&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp<b>LLM Receiver Inference Pipeline</b>"]
	llm_receiver_agent{"<b>LLM Receiver\nAgent</b>"}:::font_increase
	document_alternatives["<b>Documentation</b> <br> <span style='text-align:left; display:block;'>Develop one of the following:</b> <br>* principles\n* requirements\n* action strategies\n* testing strategies</span>"]:::font_increase

	process_thoughts["<b>Identify Values</b> <br> <span style='text-align:left; display:block;'>Help user process\nthoughts by asking\ninsightful questions</span>"]:::font_increase
	list_actions["<b>Task Decomposition</b> <br> <span style='text-align:left; display:block;'>Turn an overall\naction strategy into\na list of actions</span>"]:::font_increase
	which_actions_automatable["<b>Identify Automatable Actions</b>"]:::font_increase
	automate_actions["<b><i class='fa fa-image'></i> <a rel='noopener' href='https://www.mermaidchart.com/raw/cac74264-070e-4e12-8a6e-df76286a4367?theme=light&version=v0.1&format=svg' target='_blank'>Automate Actions \n Pipeline</a></b>"]:::font_increase


	llm_receiver_agent --> |"<span style='font-size: 40px;'>Documentation Needed</span>"| document_alternatives
	llm_receiver_agent --> |"<span style='font-size: 40px;'>Brainstorming Needed</span>"| process_thoughts
	llm_receiver_agent --> |"<span style='font-size: 40px;'>Action List Needed</span>"| list_actions
	list_actions --> which_actions_automatable
	which_actions_automatable --> |"<span style='font-size: 40px;'>Get consent from\nuser to automate</span>"| automate_actions

end


%% Edge connections between nodes
user_prompt --> rag_process --> llm_receiver_agent
user_prompt --> collect_user_context_process --> llm_receiver_agent


%% Node styling.
%% classDef title_styling fill:#ffffe0,stroke:#ffffe0,stroke-width:4px,font-size:14px,font-weight:bold,color:#003366;
classDef font_increase font-size: 40px;
classDef font_increase_more font-size: 40px;
class llm_receiver_pipeline font_increase_more
linkStyle default interpolate linear
```
## Key Features

### Context Collection
Generates a comprehensive memory database that includes detailed contextual information about the organization. This database serves as a knowledge base of the user’s organization, project, and existing codebase. The depth and quality of this context collection are crucial for providing accurate and relevant guidance.

### Implicit Value Collection
Implicitly gathers an initial set of core values and priorities of the organization. It implicitly collects the organization’s values, providing a high-quality starting point for collaboration. From there, the system will work with the user to establish exactly what values they would like their product development processes to be align with.

### Traceability Tool
Generates mermaid.js flowcharts that visually map the path from value → responsible AI product requirement → action → test. This tool facilitates transparency and accountability in the alignment process.

### Document Development
Works with the user to:
- Write an AI ethics statement.
- Decide on responsible AI requirements for a given product.
- Develop an action plan to meet each requirement.
- Develop a validation strategy to check that each requirement was indeed met.
- Create user stories designed to integrate with existing project management tools like JIRA, Asana, and ClickUp, enabling smooth workflow integration.

### Agent Tooling
Handles the automation of actions within the AI Alignment Liaison system. After generating the necessary documentation and strategies, Agent Tooling executes specific actions, subject to user approval. The system uses APIs for tools built by others to offload the user’s burden.

### Advanced Evaluation & Feedback Strategies
Includes sophisticated mechanisms for evaluating and refining the outputs:
- **LLM-as-a-Judge Methodology**: Utilizes few-shot prompting to align the evaluation of outputs with human judgment.
- **Feedback Loop and Iteration**: Continuously refines outputs through strategies like reinforcement learning from human feedback (RLHF), flow engineering using LangGraph, and feedback intelligence.

## Current Status
The AI Alignment Liaison is in its early stages, focusing on establishing foundational systems and processes. The current development priorities include building the product’s capabilities, integrating with additional tools and platforms, and exploring strategies of compliance and value alignment processes. The project is actively seeking funding and partnerships to support its vision of making responsible AI development accessible to all teams and organizations.

## Contact
For any inquiries or support, please contact Ari Tal at ArealTal@gmail.com.