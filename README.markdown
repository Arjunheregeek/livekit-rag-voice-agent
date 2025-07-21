# LiveKit RAG Voice Agent: A Toolkit for Conversational AI

## Overview

This repository is a comprehensive toolkit for building advanced, AI-driven conversational voice agents with a focus on Retrieval-Augmented Generation (RAG). The project is built on the [LiveKit Agents](https://docs.livekit.io/agents/) framework and provides a flexible and powerful platform for creating intelligent voice assistants that can interact with users in real-time and provide context-aware responses based on a knowledge base of your documents.

The repository contains multiple implementations of the voice agent, each demonstrating a different approach to the underlying RAG architecture, including the use of various vector databases and frameworks like LangChain and LLaMA Index.

### Key Features

* **Retrieval-Augmented Generation (RAG):** The core of this project is its powerful RAG capabilities, which allow the agent to answer questions and provide information based on a knowledge base of your documents. This enables the agent to provide accurate and detailed responses, even on complex topics.
* **Real-Time Voice Conversations:** Built on the LiveKit real-time communication platform, the agent can engage in natural, low-latency voice conversations.
* **Multiple Vector Database Integrations:** The repository includes implementations for various vector databases, including:
    * **Zilliz Cloud**
    * **Pinecone**
    * **FAISS** (for local development)
* **Framework Flexibility:** The agent has been implemented with different frameworks, including:
    * **LangChain**
    * **LLaMA Index**
    * **Mem0** (for memory management)
* **Selective RAG:** The agent can be configured to only trigger the RAG system when certain keywords are detected, allowing for faster responses to simple queries.
* **Customizable:** The agent's instructions, knowledge base, and RAG trigger words can be easily customized.

## Getting Started

### Prerequisites

* Python 3.8+
* A LiveKit server (you can use [LiveKit Cloud](https://cloud.livekit.io/))
* API keys for the services you want to use (OpenAI, Deepgram, Cartesia, etc.)
* A vector database account (e.g., Zilliz Cloud, Pinecone) if you are not using a local option like FAISS.

### Installation

1.  **Clone the Repository:**
    ```bash
    git clone <your-repository-url>
    cd <your-repository-name>
    ```

2.  **Set Up a Virtual Environment:**
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows: venv\Scripts\activate
    ```

3.  **Install Dependencies:**
    Each branch has its own `requirements.txt` file. Install the dependencies for the branch you want to use. For example, for the LangChain branch:
    ```bash
    pip install -r livekitagent-langchain/requirements.txt
    ```

4.  **Set Environment Variables:**
    Create a `.env` file in the project root and add your API keys. The required keys will vary depending on the branch you are using.
    ```
    LIVEKIT_API_KEY=...
    LIVEKIT_API_SECRET=...
    LIVEKIT_URL=...

    OPENAI_API_KEY=...
    DEEPGRAM_API_KEY=...
    CARTESIA_API_KEY=...
    ELEVENLABS_API_KEY=...

    # For Zilliz Cloud
    ZILLIZ_CLOUD_URI=...
    ZILLIZ_CLOUD_API_KEY=...

    # For Pinecone
    PINECONE_API_KEY=...

    # For Mem0
    MEM0_API_KEY=...
    ```

### Usage

Each branch has a `main.py` or similarly named file that serves as the entry point for the agent. To run the agent, simply execute this file:

```bash
python <branch-folder>/main.py
For example, to run the LangChain version:

Bash

python livekitagent-langchain/voice_lang.py
This will start the LiveKit agent worker, which will connect to your LiveKit server and wait for users to join a room.

Project Structure
The repository is organized into different branches, each containing a separate implementation of the voice agent. The general structure of each branch is as follows:

main.py or voice_lang.py: The main entry point for the agent.

agent.py or zudu_agent.py: The core logic for the voice agent.

requirements.txt: The Python dependencies for the branch.

data/: A directory containing the knowledge base documents (e.g., PDFs).

instructions.txt: A file containing the system prompt for the agent.

Branches
This repository contains several branches, each demonstrating a different approach to building the voice agent:

main: The primary branch, containing the most stable and feature-complete version of the agent.

zilliz-cloud: An implementation that uses Zilliz Cloud as the vector database for the RAG system.

pinecone-assistant: An implementation that uses the Pinecone Assistant API.

pinecone-db: An implementation that uses Pinecone as a standard vector database.

langchain: An implementation that uses the LangChain framework with a FAISS vector store.

llama-index: An implementation that uses the LLaMA Index with a local vector store.

mem0: An implementation that uses Mem0 for memory management.

License
This project is licensed under the MIT License. See the LICENSE file for details.
