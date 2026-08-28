# batchask

Run a JSONL of prompts through an LLM, results to JSONL

## Usage

```bash
python batch.py prompts.jsonl -o answers.jsonl --workers 4
```

## Installation

```bash
pip install -r requirements.txt
export OPENAI_API_KEY=sk-...
```

## What it does

- Retries failed items with backoff, logs them aside
- Idempotent: skips ids already present in the output
- Concurrent workers with a rate ceiling
- JSONL in, JSONL out: stream-safe for huge inputs

## Project structure

```text
├── .github/
│   ├── ISSUE_TEMPLATE/
│   │   └── bug_report.md
│   └── dependabot.yml
├── docs/
│   ├── configuration.md
│   ├── development.md
│   └── faq.md
├── examples/
│   └── quickstart.md
├── .gitattributes
├── .gitignore
├── CHANGELOG.md
├── CODE_OF_CONDUCT.md
├── CONTRIBUTING.md
├── batch.py
├── prompts.sample.jsonl
└── requirements.txt
```

## Development

```bash
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
python -m pytest -q
```

## License

MIT licensed, see LICENSE.
