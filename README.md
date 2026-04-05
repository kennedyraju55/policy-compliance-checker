<div align="center">
<img src="https://img.shields.io/badge/📜_Policy_Compliance_Checker-Local_LLM_Powered-blue?style=for-the-badge&labelColor=1a1a2e&color=16213e" alt="Project Banner" width="600"/>

<br/>

<img src="https://img.shields.io/badge/Gemma_4-Ollama-orange?style=flat-square&logo=google&logoColor=white" alt="Gemma 4"/>
<img src="https://img.shields.io/badge/Python-3.9+-blue?style=flat-square&logo=python&logoColor=white" alt="Python"/>
<img src="https://img.shields.io/badge/Streamlit-Web_UI-red?style=flat-square&logo=streamlit&logoColor=white" alt="Streamlit"/>
<img src="https://img.shields.io/badge/Click-CLI-green?style=flat-square&logo=gnu-bash&logoColor=white" alt="Click CLI"/>
<img src="https://img.shields.io/badge/License-MIT-yellow?style=flat-square" alt="License"/>

<br/><br/>

<strong>Part of <a href="https://github.com/kennedyraju55/90-local-llm-projects">90 Local LLM Projects</a> collection</strong>

</div>

<br/>
# ✅ Policy Compliance Checker

![Python](https://img.shields.io/badge/python-3.10%2B-blue)
![LLM](https://img.shields.io/badge/LLM-Ollama%2FGemma4-green)
![CLI](https://img.shields.io/badge/CLI-Click-orange)
![Web](https://img.shields.io/badge/Web-Streamlit-red)
![Tests](https://img.shields.io/badge/tests-pytest-yellow)

AI-powered policy compliance checker with 0-100 scoring, severity-graded violations, remediation suggestions, and multi-format report export. Includes both CLI and Streamlit dashboard interfaces.

## Features

- **Compliance Scoring (0-100)** — Visual score with PASS/WARNING/FAIL labels
- **Issue Severity Levels** — High, Medium, Low with color-coded display
- **Remediation Suggestions** — Actionable fix for each violation
- **Report Export** — JSON, Markdown, and CSV export formats
- **Severity Filtering** — Focus on specific severity levels
- **Streamlit Dashboard** — Upload documents, view score meter, issue list, and recommendations
- **YAML Configuration** — Customizable thresholds and settings

## Installation

```bash
cd 18-policy-compliance-checker
pip install -r requirements.txt
ollama serve && ollama pull gemma4
```

## Usage

### CLI

```bash
# Basic compliance check
python -m src.compliance_checker.cli --document doc.txt --policy policy.txt

# Filter by severity
python -m src.compliance_checker.cli --document doc.txt --policy policy.txt --severity high

# Export report
python -m src.compliance_checker.cli --document doc.txt --policy policy.txt --export report.json --export-format json
```

### Web UI

```bash
streamlit run src/compliance_checker/web_ui.py
```

### CLI Options

| Option            | Required | Default | Description                              |
|-------------------|----------|---------|------------------------------------------|
| `--document`      | Yes      | —       | Path to the document to check            |
| `--policy`        | Yes      | —       | Path to the policy rules file            |
| `--severity`      | No       | `all`   | Filter: all / high / medium / low        |
| `--export`        | No       | —       | Export report to file                    |
| `--export-format` | No       | `json`  | Export format: json / markdown / csv     |
| `--config`        | No       | —       | Path to config.yaml                      |
| `--verbose`       | No       | —       | Enable debug logging                     |

## Testing

```bash
python -m pytest tests/ -v
```

## Project Structure

```
18-policy-compliance-checker/
├── src/compliance_checker/
│   ├── __init__.py
│   ├── core.py              # Compliance analysis logic
│   ├── cli.py               # Click CLI interface
│   ├── web_ui.py            # Streamlit dashboard
│   ├── config.py            # Configuration management
│   └── utils.py             # Export helpers
├── tests/
│   ├── __init__.py
│   ├── test_core.py
│   └── test_cli.py
├── config.yaml
├── setup.py
├── requirements.txt
├── Makefile
├── .env.example
└── README.md
```

## 📸 Screenshots

<div align="center">
<table>
<tr>
<td><img src="https://via.placeholder.com/400x250/1a1a2e/e94560?text=CLI+Interface" alt="CLI Interface"/></td>
<td><img src="https://via.placeholder.com/400x250/16213e/e94560?text=Web+UI" alt="Web UI"/></td>
</tr>
<tr>
<td align="center"><em>CLI Interface</em></td>
<td align="center"><em>Streamlit Web UI</em></td>
</tr>
</table>
</div>
