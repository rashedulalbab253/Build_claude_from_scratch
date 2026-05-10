# Project Report: Building a Claude-Like Agentic System on Open-Source Models

## 1. Project Overview
This project is an advanced, end-to-end case study aimed at building a production-grade agentic AI system entirely from scratch. The goal is to create a scaffolding (or "harness") around open-source Large Language Models (such as DeepSeek-V3, Qwen3-32B, or Llama 3.3) to mimic the sophisticated thinking, planning, and task-solving capabilities of frontier proprietary models like Claude Sonnet 4.6. 

The core thesis of the project is that the raw LLM model is only a fraction of a frontier system's power. The majority of an agent's success comes from the surrounding architecture: the agent loop, tool registry, memory tiering, verifiers, constrained decoding, and observability. 

## 2. The Benchmark Task
To prove the capability of this custom-built agent, it is assigned a complex, real-world task: **End-to-End Reproduction of a 2026 Behavioral SEIRD Epidemiology Paper**. 

The agent must autonomously:
1. Read a target epidemiology research paper.
2. Set up a Python environment.
3. Write an original implementation from scratch (~2,000–4,000 lines of code).
4. Fit the mathematical model to real-world outbreak data (e.g., dengue/COVID).
5. Validate the recovered parameters against the paper's reported confidence intervals.
6. Run counterfactual scenarios.
7. Produce a comprehensive reproducibility report.

## 3. System Architecture (The Four Layers)
The project systematically implements 62 distinct "frontier-AI" techniques across four architectural layers:

### Layer 1: Cognition (54 Techniques)
This foundational layer defines how the LLM thinks, plans, and reasons. 
* **Key Features:** Interleaved reasoning (`<think>` blocks), ReAct/Reflexion tool-use patterns, verifier asymmetry, token compaction, sub-agent delegation, and deliberative alignment.

### Layer 2: Orchestration (4 Techniques)
This layer acts as the control system, ensuring the agent can manage complex workflows over long periods.
* **Key Features:** Directed Acyclic Graph (DAG) task planning, SQLite-backed persistent state, retries, rollbacks, and dynamic replanning.

### Layer 3: Grounding (3 Techniques)
This layer grounds the agent's actions in reality, preventing it from merely "guessing" outcomes.
* **Key Features:** Docker-sandboxed code execution, real environment testing, and Git checkpoints to save progress per step.

### Layer 4: Evaluation (1 Technique)
This layer allows the agent to self-assess and understand when a task is truly completed.
* **Key Features:** An executable specification layer encompassing tests, rubrics, and numerical tolerances.

## 4. Hardware and Environment Options
The project is designed to be highly accessible, offering multiple inference paths:
* **Cloud API:** Utilizing affordable endpoints like DeepSeek API ($0.27/M tokens) requiring no local hardware.
* **Local Inference:** Running models natively using vLLM on high-end GPUs (e.g., RTX 4090, A100) for maximum privacy and performance.
* **Laptop-Only:** Using quantized models via Ollama on consumer hardware (e.g., Apple M-series chips).

## 5. Conclusion
By meticulously building out these layers, the project demonstrates how an open-source model can close 70–85% of the performance gap with proprietary frontier models on highly complex, multi-step engineering and research tasks. It serves as both a practical blueprint for building reliable AI agents and a deep dive into the internal mechanics of modern LLM systems.
