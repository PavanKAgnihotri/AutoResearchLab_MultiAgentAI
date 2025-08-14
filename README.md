# AutoResearchLab_MultiAgentAI
This project implements a multi-agent research and reporting system using LangGraph. The system is designed to take a user query, perform a web search, extract and validate facts, generate a summary, and suggest next steps for further research.

Agents
The system consists of the following agents:
    1. Critic Agent: Evaluates the reliability of factual statements using a scoring mechanism.
    2. Research Agent: Performs web searches using SerpAPI and extracts relevant factual statements from the results.
    3. Writer Agent: Generates an executive summary and key takeaways from the validated facts. It also creates a visualization of fact reliability scores.
    4. Planner Agent: Analyzes the research results and summary to identify gaps, open questions, and suggest prioritized next research steps.

Workflow
The agents are orchestrated using LangGraph in the following sequence:
    1. Research: The Research Agent performs a web search based on the user query.
    2. Persist and Retrieve: Extracted facts are optionally persisted to a FAISS vector store for later retrieval, and similar facts are retrieved as context.
    3. Write: The Writer Agent generates a summary and visualization based on the validated facts.
    4. Plan: The Planner Agent suggests next research steps based on the research output.

Prerequisites
    Python 3.7+
    Google Generative AI API Key
    SerpAPI Key
    Install necessary libraries: langchain-google-genai, google-search-results, langchain, langchain_community, langgraph, faiss-cpu

Setup and Running
    1. Install the required libraries using pip (as shown in the first code cell of the notebook).
    2. Obtain your Google Generative AI API Key and SerpAPI Key.
    3. Replace the placeholder API keys in the Runner section of the code with your actual keys.
    4. Define your research query in the initial_state dictionary.
    5. Run the notebook cells sequentially.

The output will include the executive summary, key takeaways, the research plan, and a base64 encoded image data URI for the fact reliability visualization.
