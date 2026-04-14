# 📋 Policy Compliance Checker

![Python 3.11+](https://img.shields.io/badge/Python-3.11+-blue?style=flat-square&logo=python&logoColor=white)
![MIT License](https://img.shields.io/badge/License-MIT-yellow?style=flat-square)
![Gemma 4](https://img.shields.io/badge/Gemma_4-LLM-orange?style=flat-square&logo=google&logoColor=white)
![Privacy-First](https://img.shields.io/badge/Privacy-100%25_Local-brightgreen?style=flat-square)
![Ollama](https://img.shields.io/badge/Ollama-Inference-blueviolet?style=flat-square)

> AI-powered document compliance analysis with scoring, violation detection, and remediation — running 100% locally through Ollama.

## Architecture

```
┌─────────────────────────────────────────────────┐
│               User Interface Layer               │
│  ┌───────────┐  ┌────────────┐  ┌────────────┐  │
│  │  Click CLI │  │ Streamlit  │  │  FastAPI    │  │
│  │  (Rich UI) │  │  Web UI    │  │  REST API   │  │
│  └─────┬─────┘  └─────┬──────┘  └─────┬──────┘  │
│        └───────────────┼───────────────┘         │
│                  ┌─────▼─────┐                   │
│                  │   Core     │                   │
│                  │  Engine    │                   │
│                  └─────┬─────┘                   │
│        ┌───────────────┼───────────────┐         │
│  ┌─────▼─────┐   ┌────▼────┐   ┌──────▽─────┐  │
│  │  Policy    │   │ Scoring │   │  Export     │  │
│  │  Parser    │   │ Engine  │   │ JSON/MD/CSV │  │
│  └───────────┘   └────┬────┘   └────────────┘  │
│                  ┌─────▼─────┐                   │
│                  │  Ollama   │                   │
│                  │ (Gemma 4) │                   │
│                  └───────────┘                   │
└─────────────────────────────────────────────────┘
```

## Features

1. **Compliance Scoring** — Generates a 0–100 compliance score for any document against policy rules
2. **Violation Detection** — Identifies specific policy violations with severity levels (high, medium, low)
3. **Remediation Suggestions** — Provides actionable fix recommendations for each violation found
4. **Rich CLI Interface** — Beautiful terminal output with color-coded scores, tables, and progress bars
5. **Streamlit Web UI** — Interactive browser-based dashboard for uploading documents and viewing reports
6. **FastAPI REST Endpoint** — Programmatic access for integrating compliance checks into CI/CD pipelines
7. **Multi-Format Export** — Export reports to JSON, Markdown, or CSV for downstream processing
8. **Configurable Thresholds** — Customize pass/warning score thresholds and severity filters via YAML
9. **Docker Ready** — Full Docker and Docker Compose support for one-command deployment
10. **100% Local & Private** — All inference runs through Ollama locally; no data ever leaves your machine

## Quick Start

### Prerequisites

- Python 3.11 or higher
- [Ollama](https://ollama.com/) installed and running
- Gemma 4 model pulled: `ollama pull gemma4`

### Installation

```bash
git clone https://github.com/kennedyraju55/policy-compliance-checker.git
cd policy-compliance-checker
pip install -r requirements.txt
```

### Running the Application

**CLI:**
```bash
python -m src.compliance_checker.cli check --document doc.txt --policy policy.txt
```

**Web UI:**
```bash
streamlit run src/compliance_checker/web_ui.py
```

**Docker:**
```bash
docker-compose up
```

## Tech Stack

| Technology | Purpose |
|-----------|---------|
| Gemma 4 + Ollama | Local LLM inference for compliance analysis |
| Click + Rich | CLI framework with beautiful terminal rendering |
| Streamlit | Interactive web dashboard for document uploads |

## Project Structure

- `src/compliance_checker/` — Core application: engine, CLI, web UI, API, and config
- `common/` — Shared LLM client utilities for Ollama integration
- `tests/` — Unit and integration test suite
- `docs/` — Documentation and architecture diagrams
- `examples/` — Sample documents and policy files

## Author

**Nrk Raju Guthikonda** — [GitHub: kennedyraju55](https://github.com/kennedyraju55) · [Dev.to](https://dev.to/kennedyraju55) · [LinkedIn](https://www.linkedin.com/in/nrk-raju-guthikonda-504066a8/)
