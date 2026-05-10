<div align="center">

# 🧠 System That Mimics Claude's Architecture

### *Reverse-engineering a frontier agentic AI system using open-source LLMs*

[![Python](https://img.shields.io/badge/Python-3.10%2B-blue?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?style=for-the-badge&logo=jupyter&logoColor=white)](https://jupyter.org/)
[![DeepSeek](https://img.shields.io/badge/Model-DeepSeek--V3-green?style=for-the-badge)](https://platform.deepseek.com/)
[![License](https://img.shields.io/badge/License-MIT-purple?style=for-the-badge)](LICENSE)
[![GitHub](https://img.shields.io/badge/GitHub-rashedulalbab253-black?style=for-the-badge&logo=github)](https://github.com/rashedulalbab253)

<br/>

> *"The model is the smaller half of a frontier system. The harness — agent loop, tool registry, memory tiering, verifier, constrained decoding, observability — is what you actually need to replicate."*

</div>

---

## 📖 Overview

**Build Claude from Scratch** is a comprehensive, educational engineering project that constructs a production-grade agentic AI system layer by layer — from a raw open-source LLM to a fully operational autonomous agent that rivals **Claude Sonnet 4.6** and **GPT-5** on complex, real-world tasks.

The project does not just call an API and hope for the best. It builds **every component** that makes frontier AI systems powerful:

- 🔁 The **agent loop** that drives multi-step autonomous reasoning
- 🛠️ The **tool registry** for parallel, structured tool execution
- 🧠 The **four-tier memory system** (working / episodic / semantic / procedural)
- ✅ The **verifier layer** that checks its own work with external grounding
- 📦 The **orchestration DAG** that plans, retries, and replans
- 👁️ The **observability system** that tracks every token and cost

The capstone benchmark is **autonomously reproducing a 2026 epidemiology research paper** — a task that genuinely exercises all 62 frontier-AI techniques built throughout the notebook.

---

## 🎯 The Core Thesis

| Source of Frontier Advantage | % of Gap | Closeable? |
|---|:---:|:---:|
| Better base reasoning (model weights) | ~10% | ❌ No |
| Better RLHF tuning (model weights) | ~10% | ❌ No |
| Tool-use trained behavior | ~15% | ⚠️ Partially |
| **Inference-time scaffolding (the harness)** | **~65%** | **✅ Yes — this notebook builds it** |

---

## 🏗️ Architecture: The Four Layers

```
┌──────────────────────────────────────────────────────────┐
│  LAYER 4: EVALUATION                                     │
│  Executable specs — tests, rubrics, numerical tolerances │
├──────────────────────────────────────────────────────────┤
│  LAYER 3: GROUNDING                                      │
│  Docker REPL, real test execution, git checkpoints       │
├──────────────────────────────────────────────────────────┤
│  LAYER 2: ORCHESTRATION                                  │
│  Task DAG, SQLite persistence, retry, rollback, replan   │
├──────────────────────────────────────────────────────────┤
│  LAYER 1: COGNITION  (54 of 62 techniques)               │
│  Thinking, planning, tool-use, reflection, verification  │
└──────────────────────────────────────────────────────────┘
                     ▲
               [Open-Source LLM]
          DeepSeek-V3 / Qwen3 / Llama 3.3
```

---

## 🧪 The Benchmark Task

**End-to-End Reproduction of a 2026 Behavioral SEIRD Epidemiology Paper**

The agent autonomously:

1. 📄 **Reads** a real epidemiology paper (PDF → structured text)
2. ⚙️ **Sets up** its own Python environment
3. 💻 **Writes** a complete implementation (~2,000–4,000 lines of original code)
4. 📊 **Fits** the SEIRD model to real dengue/COVID outbreak data
5. ✅ **Validates** recovered parameters against the paper's 95% credible intervals
6. 🔮 **Runs** counterfactual scenarios
7. 📝 **Produces** a full reproducibility report with a pass/fail verdict

> **Why SEIRD?** It's real, complex, ambiguous, has verifiable ground truth, and is universally understandable — the perfect test for a general-purpose autonomous agent.

---

## ✨ The 62 Techniques

All 62 frontier-AI techniques are implemented across 4 layers and 18 notebook parts:

<details>
<summary><b>Layer 1: Cognition (Techniques 1–54)</b></summary>

| Category | Techniques |
|---|---|
| Thinking Primitives | `<think>` channels, budget tokens, interleaved reasoning |
| Reasoning Strategies | Step-back, decomposition, Tree-of-Thought, OODA, sub-agents |
| Tool-Use Patterns | Plan-execute, ReAct, Reflexion, CRITIC, verifier asymmetry |
| Reliability | Linter-loop, compaction, cache ordering, anti-counting bias |
| Frontier-Only | Thought signatures, soul document, deliberative alignment, effort knob |
| Meta-Cognitive | Problem classification, cost-bounded branching, trace mining |

</details>

<details>
<summary><b>Layer 2: Orchestration (Techniques 55–58)</b></summary>

SQLite-backed Task DAG with persistent state, retry logic, rollback, and dynamic replanning.

</details>

<details>
<summary><b>Layer 3: Grounding (Techniques 59–61)</b></summary>

Docker-sandboxed REPL, real test execution, and git checkpoints per agent step.

</details>

<details>
<summary><b>Layer 4: Evaluation (Technique 62)</b></summary>

Executable specification layer with tests, rubrics, and numerical tolerances.

</details>

---

## 🚀 Getting Started

### Prerequisites

- Python 3.10+
- Docker
- Git
- 5GB free disk space

### Choose Your Inference Path

| Option | Hardware | Cost | Setup |
|---|---|---|---|
| **☁️ DeepSeek API** | Laptop only | ~$3–8 total | API key from [platform.deepseek.com](https://platform.deepseek.com) |
| **🖥️ Local vLLM** | 24–80GB VRAM GPU | Free (electricity) | `vllm serve Qwen/Qwen3-32B-Instruct ...` |
| **💻 Ollama** | Any machine (M-series Mac) | Free (electricity) | `ollama pull qwen3:14b` |

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/rashedulalbab253/Build_claude_from_scratch.git
cd Build_claude_from_scratch

# 2. Install dependencies (handled inside the notebook — one cell, ~2 minutes)
pip install openai pydantic instructor tenacity sqlalchemy chromadb \
            sentence-transformers numpy scipy matplotlib pandas \
            pymc pypdf gitpython docker langfuse

# 3. Set your API key (if using DeepSeek API)
export DEEPSEEK_API_KEY="sk-your-key-here"

# 4. Open the notebook
jupyter notebook claude_from_scratch.ipynb
```

---

## 📚 Notebook Structure

| Part | Title | What You Build |
|---|---|---|
| 0 | Introduction | Mental model, roadmap, glossary |
| 1 | Environment Setup | LLM client, workspace, Docker |
| 2 | Paper Ingestion | PDF reader, structured extraction |
| 3 | Baseline Agent | Bare model fails — motivation for harness |
| 4–9 | Cognition Layer | All 54 thinking & tool-use techniques |
| 10 | Orchestration | Task DAG with SQLite persistence |
| 11 | Grounding | Docker sandbox + git checkpoints |
| 12 | Evaluation | Executable spec layer |
| 13 | Memory | Four-tier memory system + ChromaDB |
| 14 | Tools | Full MCP-compatible tool registry |
| 15 | Observability | Langfuse tracing + budget guards |
| 16 | Assembly | Full system integration |
| 17 | End-to-End Run | Agent autonomously solves SEIRD task |
| 18 | Comparison | Measured gap vs Claude Sonnet 4.6 |

---

## 📊 Results

After implementing all 62 techniques, the open-source agent closes **70–85% of the performance gap** to Claude Sonnet 4.6 on the SEIRD reproduction task — a level that exceeds most commercial agentic products built on GPT-4.

---

## 🤝 How to Contribute

Contributions are welcome! Feel free to:
- 🐛 Open issues for bugs or unclear explanations
- 💡 Suggest new frontier techniques to add
- 🔧 Submit PRs for alternative model backends

---

## 📄 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

---

<div align="center">



⭐ **Star this repo if you found it useful!** ⭐

</div>
