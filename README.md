# 🏆 Clinical Reasoning Language Model Elo Rating

<div align="center">

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)
[![MongoDB](https://img.shields.io/badge/Database-MongoDB-green.svg)](https://www.mongodb.com/)
[![LiteLLM](https://img.shields.io/badge/LLM-LiteLLM-orange.svg)](https://github.com/BerriAI/litellm)
[![arXiv](https://img.shields.io/badge/arXiv-2024.xxxxx-b31b1b.svg)](https://arxiv.org/abs/2024.xxxxx)

*A peer-federated evaluation framework addressing benchmark overfitting and cost-efficiency trade-offs in large language model assessment*

[📈 Results](#-results) • [🚀 Quick Start](#-quick-start) • [🔧 Installation](#-installation)

</div>

## 🔗 Benchmarks by Domain

> ### 🩺 for Clinical Reasoning  
> [**🔗 GitHub Repository**](https://github.com/ayushi-uwc/elo-benchmark)  
> The original UNER implementation focused on diagnostic case evaluation and clinical reasoning.  
> Uses dynamic peer-generated challenges and dual-track Elo to evaluate medical knowledge, logical consistency, and decision-making accuracy.

> ### 💻 for Programming Tasks  
> [**🔗 GitHub Repository**](https://github.com/ayushi-uwc/elo-benchmark-programming)  
> Evaluates LLMs on algorithm design, code efficiency, debugging, and optimization skills.  
> Prompts are adapted to competitive programming-style tasks with multi-provider peer evaluation.

> ### 🧮 for Mathematical Reasoning  
> [**🔗 GitHub Repository**](https://github.com/ayushi-uwc/elo-benchmark-mathematical-reasoning)  
> Focuses on proof construction, logical deduction, and symbolic reasoning.  
> Uses math-focused prompts and peer-reviewed challenge generation to assess core reasoning capabilities.

All benchmarks follow a standardized Swiss-pairing system with full cost-performance analysis.  
Each repo includes open logs, match histories, and leaderboard tracking.

```
DETAILED LEADERBOARD
┌───┬──────────────────────────────┬────────┬────────┬──────────┬──────────┬────────────┬────────┬───────────┬────────┐
│ # │Model                         │Raw ELO │Cost ELO│Raw Avg   │Cost Avg  │W-L-D       │Tokens  │Cost $     │Matches │
├───┼──────────────────────────────┼────────┼────────┼──────────┼──────────┼────────────┼────────┼───────────┼────────┤
│ 1 │Gemini 2.5 Pro               │ 1603.9 │ 1561.9 │   0.6989 │   0.6142 │ 165-69-13  │4717145 │ $37.75128 │     50 │
│ 2 │GPT-4.1                       │ 1601.2 │ 1603.7 │   0.7121 │   0.7183 │ 169-64-13  │1574472 │  $5.58125 │     50 │
│ 3 │GPT-4.1 mini                  │ 1599.6 │ 1605.7 │   0.7336 │   0.7462 │ 160-54-14  │1551438 │  $1.10994 │     46 │
│ 4 │GPT-o4-mini                   │ 1568.2 │ 1569.9 │   0.6024 │   0.6065 │ 139-96-12  │1884003 │  $4.49846 │     50 │
│ 5 │Qwen 3.2 235B                 │ 1555.4 │ 1564.8 │   0.6912 │   0.7115 │ 164-68-15  │1652646 │  $0.05886 │     50 │
│ 6 │Grok 3 Mini Fast              │ 1537.7 │ 1540.9 │   0.5529 │   0.5557 │ 125-101-16 │  986629 │  $0.83581 │     50 │
│ 7 │GPT-o3-mini                   │ 1533.7 │ 1492.4 │   0.5767 │   0.4891 │ 131-102-14 │  792504 │ $16.67280 │     50 │
│ 8 │Claude 3.7 Sonnet             │ 1530.5 │ 1527.1 │   0.5877 │   0.5823 │ 139-92-16  │1339119 │  $8.02990 │     50 │
│ 9 │Grok 3                        │ 1523.4 │ 1523.2 │   0.5663 │   0.5659 │ 128-98-21  │1104597 │  $8.04717 │     50 │
│10 │Qwen 3 32B                    │ 1520.2 │ 1537.7 │   0.5521 │   0.5871 │ 131-104-10 │2052475 │  $0.07149 │     50 │
│11 │Gemini 2.0 Flash             │ 1519.6 │ 1527.6 │   0.5118 │   0.5319 │ 120-114-11 │  170242 │  $0.02618 │     50 │
│12 │Grok 3 Fast                   │ 1519.2 │ 1514.7 │   0.5331 │   0.5271 │ 123-104-19 │1012959 │ $12.38477 │     50 │
│13 │GPT-4o                        │ 1515.3 │ 1510.4 │   0.5497 │   0.5360 │ 134-107-8  │  256291 │  $1.90124 │     50 │
│14 │Claude 3.5 Haiku             │ 1509.8 │ 1515.0 │   0.5550 │   0.5661 │ 128-99-21  │  954069 │  $1.25208 │     50 │
│15 │Claude 3.5 Sonnet            │ 1509.7 │ 1505.6 │   0.5484 │   0.5366 │ 126-102-19 │  207043 │  $1.06406 │     50 │
│16 │GPT-o3                        │ 1508.4 │ 1486.2 │   0.9025 │   0.8481 │ 217-19-11 │1274491 │ $30.49204 │     50 │
│17 │Gemini 2.5 Flash             │ 1505.6 │ 1510.3 │   0.5078 │   0.5204 │ 117-115-16 │  533934 │  $0.22392 │     50 │
│18 │Claude 3 Opus                │ 1501.9 │ 1464.9 │   0.5325 │   0.4507 │ 124-111-10 │   98088 │  $2.32572 │     50 │
│19 │Gemini 2.0 Flash Lite        │ 1497.3 │ 1503.0 │   0.4946 │   0.5081 │ 111-120-11 │   86055 │  $0.00929 │     50 │
│20 │Meta Llama 4 Scout Instruct  │ 1494.6 │ 1500.6 │   0.5234 │   0.5360 │ 125-112-11 │  433948 │  $0.03559 │     50 │
│21 │Grok 3 Mini                   │ 1493.4 │ 1501.6 │   0.4752 │   0.4916 │ 110-119-16 │  336951 │  $0.07963 │     50 │
│22 │Command R 7B                  │ 1491.7 │ 1501.2 │   0.5605 │   0.5819 │ 127-96-19  │  340480 │  $0.01975 │     50 │
│23 │GPT-4.1 nano                 │ 1490.4 │ 1498.6 │   0.4758 │   0.4935 │ 115-125-9  │   82535 │  $0.01248 │     50 │
│24 │DeepSeek R1 Distill Llama 70B│ 1487.9 │ 1499.0 │   0.4588 │   0.4836 │ 107-125-16 │  112325 │  $0.09599 │     50 │
│25 │Meta Llama 4 Maverick Instruct│ 1478.8 │ 1483.8 │   0.4667 │   0.4766 │ 108-128-10 │  171731 │  $0.01476 │     50 │
│26 │Gemma 3 27B                   │ 1477.6 │ 1484.5 │   0.4686 │   0.4845 │ 108-124-14 │  244013 │  $0.02440 │     50 │
│27 │Microsoft Phi 4               │ 1470.6 │ 1472.6 │   0.4646 │   0.4689 │ 108-126-11 │   69972 │  $0.00201 │     50 │
│28 │Claude 3 Sonnet              │ 1470.6 │ 1464.5 │   0.4578 │   0.4481 │ 102-122-23 │  151151 │  $0.72019 │     50 │
│29 │Grok 2                        │ 1468.8 │ 1468.1 │   0.4701 │   0.4681 │ 110-125-13 │  472402 │  $1.80693 │     50 │
│30 │Command A                     │ 1462.8 │ 1465.0 │   0.6298 │   0.6309 │ 145-80-20  │  729942 │  $2.87647 │     50 │
│31 │Command R                     │ 1462.2 │ 1466.3 │   0.5691 │   0.5786 │ 131-95-18  │  432739 │  $0.09936 │     50 │
│32 │Gemini 1.5 Flash             │ 1460.6 │ 1463.4 │   0.4345 │   0.4424 │ 106-134-5  │   68477 │  $0.00809 │     50 │
│33 │Command R+                    │ 1460.5 │ 1459.4 │   0.5190 │   0.5136 │ 120-107-18 │  238925 │  $1.25400 │     50 │
│34 │Gemini 1.5 Pro               │ 1457.3 │ 1460.8 │   0.4503 │   0.4569 │  99-125-19 │  244863 │  $0.41000 │     50 │
│35 │Microsoft Phi 3.5 Mini Instruct│ 1450.4 │ 1457.5 │   0.4333 │   0.4433 │ 103-132-6  │   87912 │  $0.00258 │     50 │
│36 │Gemma 3 12B                   │ 1447.8 │ 1451.3 │   0.4179 │   0.4250 │  92-133-20 │   60966 │  $0.00000 │     50 │
│37 │Mistral 8x7B Instruct        │ 1447.5 │ 1451.1 │   0.4080 │   0.4199 │  97-141-9  │   95290 │  $0.00287 │     50 │
│38 │Llama 3.3 70B                 │ 1444.9 │ 1444.7 │   0.4239 │   0.4244 │  96-134-17 │  116514 │  $0.07293 │     50 │
│39 │Claude 3 Haiku               │ 1434.1 │ 1436.6 │   0.4122 │   0.4173 │  92-139-16 │   81304 │  $0.03100 │     50 │
│40 │Gemini 1.5 Flash 8B          │ 1426.9 │ 1430.3 │   0.3882 │   0.3946 │  90-148-9  │   70439 │  $0.00379 │     50 │
│41 │Gemma 3 4B                    │ 1424.1 │ 1428.0 │   0.3976 │   0.4075 │  97-148-5  │   71491 │  $0.00000 │     50 │
│42 │LLaMA 3.1 8B Instant         │ 1423.9 │ 1426.5 │   0.3859 │   0.3901 │  92-148-6  │   75627 │  $0.00426 │     50 │
│43 │Mistral Saba 24B             │ 1421.0 │ 1422.8 │   0.4101 │   0.4139 │  99-138-10 │  124411 │  $0.09828 │     50 │
│44 │GPT-3.5 Turbo                │ 1413.9 │ 1415.7 │   0.3655 │   0.3761 │  85-146-16 │   78178 │  $0.04828 │     50 │
│45 │Gemma 2 9B                    │ 1411.0 │ 1412.4 │   0.3811 │   0.3875 │  87-146-8 │  106920 │  $0.02138 │     50 │
│46 │Gemma 3 1B                    │ 1387.5 │ 1388.5 │   0.3470 │   0.3477 │  80-156-12 │   84855 │  $0.00000 │     50 │
│47 │Allamanda 2 7B                │ 1353.9 │ 1354.6 │   0.3068 │   0.3076 │  71-167-6  │  121480 │  $0.01286 │     50 │
│48 │Mistral Nemo Instruct 2407   │ 1274.9 │ 1276.0 │   0.1076 │   0.1082 │  17-212-18 │    1558 │  $0.00039 │     50 │
└───┴──────────────────────────────┴────────┴────────┴──────────┴──────────┴────────────┴────────┴───────────┴────────┘
```

# Elo Score Distributions for Participating Models

| Model                              | Cost Adjusted Elo | Adj Elo Rank | Raw Elo | Raw Elo Rank | Rank Difference |
|------------------------------------|-------------------|--------------|---------|--------------|-----------------|
| GPT-4.1 mini                       | 1605.7            | 1            | 1599.6  | 3            | 2               |
| GPT-4.1                            | 1603.7            | 2            | 1601.2  | 2            | 0               |
| GPT-04-mini                        | 1569.9            | 3            | 1568.2  | 4            | 1               |
| Qwen 3.2 235B                      | 1564.8            | 4            | 1555.4  | 5            | 1               |
| Gemini 2.5 Pro                     | 1561.9            | 5            | 1603.9  | 1            | -4              |
| Grok 3 Mini Fast                   | 1540.9            | 6            | 1537.7  | 6            | 0               |
| Qwen 3 32B                         | 1537.7            | 7            | 1529.9  | 10           | 3               |
| Gemini 2.0 Flash                   | 1527.6            | 8            | 1519.6  | 11           | 3               |
| Claude 3.7 Sonnet                  | 1527.1            | 9            | 1530.5  | 8            | -1              |
| Grok 3                             | 1523.2            | 10           | 1523.4  | 9            | -1              |
| Claude 3.5 Haiku                   | 1515.0            | 11           | 1509.8  | 14           | 3               |
| Grok 3 Fast                        | 1514.7            | 12           | 1519.2  | 12           | 0               |
| GPT-4o                             | 1510.4            | 13           | 1515.3  | 13           | 0               |
| Gemini 2.5 Flash                   | 1510.3            | 14           | 1506.6  | 17           | 3               |
| Claude 3.5 Sonnet                  | 1505.6            | 15           | 1509.7  | 15           | 0               |
| Gemini 2.0 Flash Lite              | 1503.0            | 16           | 1497.3  | 19           | 3               |
| Grok 3 Mini                        | 1501.6            | 17           | 1493.4  | 21           | 4               |
| Command R 7B                       | 1501.2            | 18           | 1491.7  | 22           | 4               |
| Meta Llama 4 Scout Instruct 17B    | 1500.6            | 19           | 1494.6  | 20           | 1               |
| DeepSeek R1 Distill Llama 70B      | 1499.0            | 20           | 1487.9  | 24           | 4               |
| GPT-4.1 nano                       | 1498.6            | 21           | 1490.4  | 23           | 2               |
| GPT-03-mini                        | 1492.4            | 22           | 1533.7  | 7            | -15             |
| GPT-03                             | 1486.2            | 23           | 1508.4  | 16           | -7              |
| Gemma 3 27B                        | 1484.5            | 24           | 1477.6  | 26           | 2               |
| Meta Llama 4 Maverick Instruct 17B | 1483.8            | 25           | 1478.8  | 25           | 0               |
| Microsoft Phi 2                    | 1472.6            | 26           | 1470.6  | 27           | 1               |
| Grok 2                             | 1468.1            | 27           | 1468.8  | 29           | 2               |
| Command R                          | 1466.3            | 28           | 1462.2  | 31           | 3               |
| Command A                          | 1465.0            | 29           | 1462.8  | 30           | 1               |
| Claude 3 Opus                      | 1464.9            | 30           | 1501.9  | 18           | -12             |
| Claude 3 Sonnet                    | 1464.5            | 31           | 1470.6  | 28           | -3              |
| Gemini 1.5 Flash                   | 1463.4            | 32           | 1460.6  | 32           | 0               |
| Gemini 1.5 Pro                     | 1460.8            | 33           | 1457.3  | 34           | 1               |
| Command R+                         | 1459.4            | 34           | 1460.5  | 33           | -1              |
| Microsoft Phi 3.5 Mini Instruct    | 1457.5            | 35           | 1450.4  | 35           | 0               |
| Gemma 3 12B                        | 1451.3            | 36           | 1447.8  | 36           | 0               |
| Mistral 8x7B Instruct              | 1451.1            | 37           | 1447.5  | 37           | 0               |
| Llama 3.3 70B                      | 1444.7            | 38           | 1444.9  | 38           | 0               |
| Claude 3 Haiku                     | 1436.6            | 39           | 1434.1  | 39           | 0               |
| Gemini 1.5 Flash 8B                | 1430.3            | 40           | 1426.9  | 40           | 0               |
| Gemma 3 4B                         | 1428.0            | 41           | 1424.1  | 41           | 0               |
| LLAMA 3.1 8B Instant               | 1426.5            | 42           | 1423.9  | 42           | 0               |
| Mistral Saba 24B                   | 1422.8            | 43           | 1421.0  | 43           | 0               |
| GPT-3.5 Turbo                      | 1415.7            | 44           | 1413.9  | 44           | 0               |
| Gemma 2 9B                         | 1412.4            | 45           | 1411.0  | 45           | 0               |
| Gemma 3 1B                         | 1388.5            | 46           | 1387.5  | 46           | 0               |
| Allamanda 2 7B                     | 1354.6            | 47           | 1353.9  | 47           | 0               |
| Mistral Nemo Instruct 2407         | 1276.0            | 48           | 1274.9  | 48           | 0               |

Detailed Logs have been uploaded to google drive

[Detailed Logs](https://drive.google.com/drive/folders/1vZh4me-VpUhWxts7PyF3jnm0NJ-lGL_O?usp=sharing)

## 🚀 Quick Start

### Prerequisites
- Python 3.8+
- MongoDB database
- API keys for LLM providers

### Installation

```bash
# Clone the repository
git clone https://github.com/yourusername/elo-benchmark.git
cd elo-benchmark

# Install dependencies
pip install -r requirements.txt

# Set up environment variables
cp .env.example .env
# Edit .env with your API keys and MongoDB URI
```

### Run Your First Tournament

```bash
# Start a tournament with default settings
python main.py

# Run with custom parameters
python main.py --batch-size 10 --stats

# Check model health
python check_models.py
```

## 🛠️ Installation

### Environment Setup

1. **Clone Repository**
```bash
git clone https://github.com/yourusername/elo-benchmark.git
cd elo-benchmark
```

2. **Install Dependencies**
```bash
pip install -r requirements.txt
```

3. **Configure Environment**
Create a `.env` file:
```env
# LLM Provider API Keys
OPENAI_API_KEY=your_openai_key
ANTHROPIC_API_KEY=your_anthropic_key
GOOGLE_API_KEY=your_google_key
HUGGINGFACE_API_KEY=your_huggingface_key
GROQ_API_KEY=your_groq_key
XAI_API_KEY=your_xai_key

# Database Configuration
MONGODB_URI=your_mongodb_connection_string
```

### Model Configuration

Add new models in `model_definitions.py`:

```python
{
    "name": "GPT-4 Turbo",
    "model_id": "gpt-4-turbo-preview",
    "provider": "openai",
    "input_cost_per_million": 10.0,
    "output_cost_per_million": 30.0,
    "pricing_source": "OpenAI API Pricing"
}
```

## 📊 Usage

### Command Line Interface

```bash
# Basic tournament run
python main.py

# Advanced options
python main.py \
    --max-matches 100 \
    --batch-size 10 \
    --stats \
    --log-level INFO
```

### Programmatic Usage

```python
from models import initialize_models
from tournament import run_tournament_matches
from model_definitions import MODELS

# Initialize models
models = initialize_models(MODELS)

# Run tournament
matches = run_tournament_matches(models, max_matches=50)

# Analyze results
for match in matches:
    print(f"Match: {match.participants}")
    print(f"Scores: {match.judgment['raw_score']}")
```

### Configuration Options

| Parameter | Default | Description |
|-----------|---------|-------------|
| `max_matches` | 50 | Maximum matches per model |
| `batch_size` | 10 | Matches per batch |
| `k_factor` | 32 | Elo update rate |
| `cost_temperature` | 0.05 | Cost sensitivity |
| `judge_temperature` | 300 | Judge weight temperature |

## 📁 Project Structure

```
elo-benchmark/
├── 📄 main.py                    # Main entry point
├── 🏆 tournament.py              # Tournament management and pairing
├── 🤖 models.py                  # LLM model classes and Elo tracking
├── ⚔️ matches.py                 # Match logic and prompt templates
├── 🗄️ database.py                # MongoDB operations and data persistence
├── ⚙️ config.py                  # Configuration and environment variables
├── 📋 model_definitions.py       # Model specifications and pricing
├── 📊 leaderboard.py             # Results display and ranking
├── 🔍 check_models.py            # Model health checks and validation
├── 📈 match_results_table.py     # Results analysis and visualization
├── 🔧 logger_config.py           # Logging configuration
├── 📝 logs/                      # Tournament logs and match history
├── 🧪 tests/                     # Unit tests and integration tests
└── 📚 docs/                      # Additional documentation
```

## 🤝 Contributing

We welcome contributions! Please see our [Contributing Guidelines](CONTRIBUTING.md) for details.

### Development Setup

```bash
# Clone and setup development environment
git clone https://github.com/yourusername/elo-benchmark.git
cd elo-benchmark
pip install -r requirements-dev.txt

# Run tests
python -m pytest tests/ -v

# Check code style
black . && flake8 . && mypy .
```


## 📄 License

This project is licensed under the ([![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)
).

## 🙏 Acknowledgments

- Built with [LiteLLM](https://github.com/BerriAI/litellm) for unified LLM access
- Inspired by chess Elo rating systems and [TrueSkill](https://www.microsoft.com/en-us/research/project/trueskill-ranking-system/)
- Mathematical framework based on [Bradley-Terry models](https://en.wikipedia.org/wiki/Bradley%E2%80%93Terry_model)
- Clinical evaluation methodology inspired by medical education assessment
- Special thanks to the open-source AI research community
---

<div align="center">

</div>
