# Chat-bot-
Chat bot 
Multimodal AI Chat Agent with Gemini (using n8n)
This repository contains the JSON export for an automated workflow built on the n8n platform. This workflow sets up a powerful, functional AI Agent capable of natural conversation, remembering context, performing calculations, and accessing the internet via Google Search (SerpAPI).

🚀 Project Overview
This project demonstrates a multi-tool AI Agent configuration, ideal for deploying a smart conversational interface for customer support, internal knowledge querying, or advanced digital assistance.

Key Capabilities
Real-time Conversation: Maintains chat history using Simple Memory for context-aware responses.

External Knowledge: Leverages SerpAPI (Google Search) to answer questions requiring up-to-date, real-time information.

Complex Calculations: Uses the Calculator tool to solve mathematical queries that the LLM may struggle with.

Core Intelligence: Powered by the Google Gemini Chat Model for high-quality, reasoned responses.

⚙️ Architecture and Workflow Breakdown
The core of the system is the AI Agent node, which intelligently decides which tool (SerpAPI or Calculator) to use before generating a final response via the Gemini Chat Model.

Workflow Structure (Nodes)
This section outlines the function of each node within the n8n workflow:

When chat message received (Chat Trigger): Starts the workflow whenever a message is sent to the Chatbot endpoint.

Google Gemini Chat Model (Language Model): Provides the core intelligence for response generation. Connects to the ai_languageModel input of the AI Agent.

Simple Memory (Chat Memory): Stores conversation history, enabling follow-up questions and context retention. Connects to the ai_memory input of the AI Agent.

AI Agent (Agent): The central orchestrator that receives the message, assesses the intent, and decides which tool or model to call. This is the main processing node.

SerpAPI (Tool): Provides real-time internet search capabilities (Google Search) for current events or external knowledge. Connects to the ai_tool input of the AI Agent.

Calculator (Tool): Executes mathematical operations, delegated by the AI Agent. Connects to the ai_tool input of the AI Agent.

🛠️ Prerequisites
To deploy and run this workflow, you need the following:

n8n Instance: A running instance of n8n (either self-hosted or cloud).

API Keys/Accounts:

Google Gemini API Key: For connecting the Google Gemini Chat Model (referenced as Google Gemini(PaLM) Api account in the JSON).

SerpAPI Key: For the SerpAPI tool to perform real-time searches.

🚀 Deployment Instructions
1. Import the Workflow
Open your n8n instance and navigate to the Workflows section.

Click "New" or the "Import from JSON" button.

Copy the entire content of the uploaded Chat bot.json file.

Paste the JSON content into the import box and click "Import."

2. Configure Credentials
The imported workflow will show that the existing credentials are not linked. You must replace them with your own.

Update Gemini Credential:

Double-click the "Google Gemini Chat Model" node.

Under the Credentials section, click "Create New Credential."

Enter your Google Gemini API Key and save the credential (Ensure the name matches the expected type, typically googlePalmApi).

Update SerpAPI Credential:

Double-click the "SerpAPI" node.

Under the Credentials section, click "Create New Credential."

Enter your SerpAPI Key and save the credential.

3. Activate the Chatbot
Ensure all nodes are connected correctly (as shown in the connections section of the JSON).

Click the "Activate" toggle switch (top right of the n8n interface) to turn the workflow ON.

The "When chat message received" node will now have an active webhook endpoint URL that you can use to interact with your new AI Agent.

🧪 Testing the Chatbot
Here are examples of queries to test the Agent's ability to utilize its tools:

General Query (Direct LLM): "What is the capital of Canada?"

Real-Time Query (SerpAPI): "What is the latest news about the current stock market?"

Mathematical Query (Calculator): "What is the result of 456 times 789 divided by 3?"

Contextual Query (Simple Memory): "Who did I ask about first, the prime minister or the president?"

👤 Maintainers
Project Lead: Abhishek Awasthi

Contact: Abhishekawasthi232@gmail.com  / www.linkedin.com/in/abhishek-awas
