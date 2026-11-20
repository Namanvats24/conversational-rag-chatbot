# conversational-rag-chatbot
A conversational RAG chatbot with chat-history memory, built using LangChain, Groq, HuggingFace embeddings and ChromaDB.
About

Normal RAG chatbots treat every question separately, so a follow-up like "Tell me more about it?" fails. This project fixes that by rewriting each follow-up into a standalone question using the chat history, then retrieving the right context to answer it.

How it works
Load a blog post from the web and split it into chunks
Convert the chunks into embeddings and store them in ChromaDB
Rewrite the user's question using the chat history (history-aware retriever)
Retrieve the most relevant chunks and pass them to the LLM
Return a short answer and save it to the chat history
Tech stack

LangChain · Groq (openai/gpt-oss-20b) · HuggingFace all-MiniLM-L6-v2 · ChromaDB · Python

Setup
bash
git clone https://github.com/Namanvats24/conversational-rag-chatbot.git
cd conversational-rag-chatbot

python -m venv venv
source venv/bin/activate        # Windows: venv\Scripts\activate

pip install -r requirements.txt

Create a .env file:

env
GROQ_API_KEY=your_groq_api_key
HF_TOKEN=your_huggingface_token

Then open conversation.ipynb and run the cells from top to bottom.

Author

Naman Vats · @Namanvats24
