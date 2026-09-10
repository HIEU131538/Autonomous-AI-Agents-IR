# Autonomous AI Agents for Incident Response (SOC)

![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![AI/LLM](https://img.shields.io/badge/AI%2FLLM-Llama_3.1-orange)
![Framework](https://img.shields.io/badge/Framework-LangGraph-green)
![Database](https://img.shields.io/badge/Vector_DB-ChromaDB-purple)

## Overview
This repository contains the core architecture for an Autonomous Multi-Agent System designed to automate Incident Response (IR) and Security Operations Center (SOC) workflows. By leveraging Large Language Models (LLMs) and Retrieval-Augmented Generation (RAG), the system analyzes security logs, maps threats to the MITRE ATT&CK framework, and executes automated defensive actions.

## Key Features
- Multi-Agent Workflow: Utilizes LangGraph to orchestrate distinct AI agents for log parsing, threat intelligence retrieval, and decision-making.
- RAG-Powered Analysis: Integrates ChromaDB as a vector store to efficiently retrieve past incident knowledge and cybersecurity frameworks.
- Local LLM Deployment: Runs Llama 3.1 (via Ollama) locally to ensure data privacy and prevent sensitive log leakage.
- API Integration: Exposes model functionalities and automated alerts via FastAPI.

## Tech Stack
- Core Language: Python 3.1x
- AI/ML Frameworks: LangGraph, Llama 3.1 (Ollama), LangChain
- Vector Database: ChromaDB
- Backend API: FastAPI, Uvicorn

## Installation & Execution

To set up and run the system locally, execute the following sequential commands in your terminal:

```bash
# 1. Clone the repository
git clone [https://github.com/HIEU131538/Autonomous-AI-Agents-IR.git](https://github.com/HIEU131538/Autonomous-AI-Agents-IR.git)
cd Autonomous-AI-Agents-IR

# 2. Initialize and activate a virtual environment
python -m venv venv
source venv/bin/activate  # For Windows use: venv\Scripts\activate

# 3. Install required dependencies
pip install -r requirements.txt

# 4. Generate local environment configuration
echo "OLLAMA_BASE_URL=[http://127.0.0.1:11434](http://127.0.0.1:11434)" > .env
echo "TELEGRAM_BOT_TOKEN=your_telegram_bot_token" >> .env
echo "TELEGRAM_CHAT_ID=your_telegram_chat_id" >> .env

# 5. Start the FastAPI server
uvicorn main:app --reload

System Workflow
Once the server is operational, the system automatically monitors incoming logs from designated system endpoints. Anomalies are processed by the orchestrator agent and cross-referenced with ChromaDB. Security alerts and mitigation recommendations are subsequently pushed via the Telegram bot and accessible through API endpoints.

Developer
Duong Ngoc Hieu (Information Security Student @ Academy of Cryptography Techniques)

Contact: hieubeo1538@gmail.com
