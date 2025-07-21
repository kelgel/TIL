# 2025-07-21 TIL – Full Project Architecture & Agent Roles Understood

## What I did today
- Fully understood the overall directory structure of our LangChain-based emotion book bot project
- Studied how MainAgent and functional agents (RecommendAgent, InfoAgent, ClarifyAgent) are organized
- Clarified the roles of prompt templates, tools, and chains in the system
- Successfully connected Docker environment for team collaboration

---

## What I learned

- ### 🧱 Project Architecture
  The project is structured into main_agent/, agents/, tools/, prompt_templates/, and chains/.  
  MainAgent handles user input routing based on intent (e.g. recommend vs. info lookup).  
  Each sub-agent (like recommend_agent.py) wraps a chain that combines prompt + tool.

- ### 🔧 Agent / Tool / Prompt Roles
  - Agent: The interface for triggering a specific function (e.g. book recommendation).  
  - Prompt: The command template that defines how the LLM should behave (e.g. analyze query or generate emotional response).  
  - Tool: Executes real actions such as querying MySQL, searching ChromaDB, or calling an API.   
  - Chain: Binds prompt and tool together; represents one complete unit of execution.

- ### 🧩 System Flow Summary
  MainAgent analyzes the user's intent → routes to a sub-agent → that agent uses prompt + tool(s) → response is returned.  
  Clarification prompts are triggered only if initial input lacks key information (like emotion or genre).  
  The system is modular: more agents, prompts, or tools can be added without breaking the existing flow.

- ### 🐳 Docker Setup Success
  Docker Compose now links shared DB and backend services for the team.   
  This allows us to develop and test the chatbot service in a unified, containerized environment.

---

## Reflections
- Fully understanding the structure (agent–chain–tool–prompt) gives me confidence to begin real implementation this week.
- I now see how LangChain promotes modular design and clean separation of concerns.

---

## Goals for Tomorrow
- Start implementing main agent and recommendation agent
- Write tests for prompt and chain interactions

