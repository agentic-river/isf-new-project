# 🏗️ ISF-Core Project Scaffold

<p align="center">
  <strong>Your 2-Minute Gateway to a Self-Hosted AI Software Factory.</strong><br>
  🚀 Spin up a concurrent team of specialized AI workers locally in Docker Compose.<br>
  💬 Unified Outlook-style Inbox workspace mapped directly to your local IDE.<br>
  🔒 Built for 100% data sovereignty, air-gapped local LLMs, and micro-token cost efficiency.
</p>

<p align="center">
  <a href="https://github.com/agentic-river/isf-new-project/generate"><img src="https://img.shields.io/badge/Use_This_Template-Click_Here-brightgreen?style=for-the-badge&logo=github" alt="Use This Template" /></a>
  <a href="https://github.com/agentic-river/isf-core"><img src="https://img.shields.io/badge/Core_Engine-isf--core-blue?style=for-the-badge" alt="Core Engine" /></a>
  <a href="https://github.com/agentic-river/isf-core/issues"><img src="https://img.shields.io/badge/Feedback-Welcome-blue?style=for-the-badge" alt="Feedback" /></a>
</p>

---

## 🌟 What is this Repository?

This is the **official project starter template** for the [Infinite Software Factory (ISF)](https://github.com/agentic-river/isf-core). 

Instead of downloading the entire ISF source code, this template contains **only the configuration and orchestration layers** you need to manage your own projects. The actual core engine executes inside pre-compiled, secure Docker images (`donalldoo/isf-factory` and `donalldoo/ai-proxy-server`) pulled automatically from Docker Hub.

### Why use this template?
1. **Isolated Projects:** Create a brand new, clean repository for every separate application you build.
2. **Local Volume Mapping:** Your code, specifications, and databases stay 100% local on your disk.
3. **Frictionless Onboarding:** Just click **"Use this template"**, run the setup script, and start coding with AI in minutes.

---

## 🚀 Quick Start

Ensure you have [Docker Desktop](https://docs.docker.com/get-docker/) installed and running, then spin up your local factory in seconds:

### Step 1: Click "Use this template" or Clone
Click the green **"Use this template"** button at the top of this repository on GitHub to create your own private repository, or clone it directly:

```bash
git clone https://github.com/agentic-river/isf-new-project.git my-ai-project
cd my-ai-project
```

### Step 2: Configure Your API Keys
Set up your AI Proxy credentials to route requests securely to your chosen LLM models (Gemini, DeepSeek, Claude, OpenAI, etc.):

```bash
# Copy the environment example file
cp .env.ai_proxy.example .env.ai_proxy

# Open and add your API keys (e.g., GOOGLE_API_KEY, DEEPSEEK_API_KEY)
nano .env.ai_proxy
# or use VS Code
code .env.ai_proxy
```

### Step 3: Run Setup & Launch
Execute the setup script to initialize your SQLite database, volumes, and base configurations:

```bash
# Initialize SQLite schemas and local configs
python setup.py

# 🚀 Start the ISF Engine + Secure AI-Proxy Docker containers
python start_isf_core.py
```

🎉 Open **`http://localhost:3006`** in your browser! Your personal software department is live.

---

## 🗺️ What's Inside Your Project Workspace

Your cloned repository contains the following architecture, completely mapped to the host directory:

| Folder / File | Purpose |
| :--- | :--- |
| `docs/` | **System Specifications.** The AI writer agent updates these specs live so documentation never decays. |
| `rules/` | **Operational Guidelines.** The AI writes post-mortem rules here to learn from mistakes and optimize itself. |
| `backend/tasks/` | Python background cron scripts (e.g., auto-healing tests, Sonar scans, test coverage boosts). |
| `browser-agents/` | Playwright automation scripts allowing agents to navigate third-party portals. |
| `supabase-docker/` | Optional self-hosted Supabase compose stack for enterprise vector scaling. |
| `data/` | Isolated local SQLite database (`chat_history.db`) — completely private to your host machine. |
| `system_prompt.md` | Core behavioral guidelines, tool protocols, and visual rendering specifications for your AI team. |
| `models.yaml` | Router configuration mapped with current per-token costs. Routes micro-tasks to cheap models automatically. |
| `start_isf_core.py` | One-command launcher script that automatically maps Docker volume paths for Windows/WSL2/macOS. |
| `shutdown_isf_core.py` | Graceful shutdown script that stops container processes while preserving your SQLite databases. |

---

## 📦 Troubleshooting & Support

*   **Port Conflicts:** If `3006` or `8080` is in use, modify the host port bindings in the `ports:` section of `compose.yml`.
*   **Docker RAM Issues:** We recommend allocating at least **4 CPU Cores and 8GB RAM** in Docker Desktop settings for optimal concurrent multi-agent speeds.
*   **Model Routing Failures:** Double-check your keys in `.env.ai_proxy` and run `docker compose logs ai-proxy` to check raw provider response logs.

For detailed custom upgrades (Supabase integration, Telegram mobile center, SonarQube quality gates, Tavily web search), read the files inside the `options_setup/` directory.

### 🤝 Joining the Community
If you encounter bugs or want to request new features for the underlying core engine, please open an issue in the [Main ISF-Core Repository](https://github.com/agentic-river/isf-core).

If this tool has saved you time, **please give this repository and [isf-core](https://github.com/agentic-river/isf-core) a Star 🌟!**
