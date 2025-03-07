# Praison AI

<iframe width="560" height="315" src="https://www.youtube.com/embed/Fn1lQjC0GO0" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

<img alt="PraisonAI Logo" src="overrides/images/praisonai-logo-light.png" style="display: block; margin: auto;" />

<p align="center">
<a href="https://github.com/MervinPraison/PraisonAI"><img src="https://static.pepy.tech/badge/PraisonAI" alt="Total Downloads" /></a>
<a href="https://github.com/MervinPraison/PraisonAI"><img src="https://img.shields.io/github/v/release/MervinPraison/PraisonAI" alt="Latest Stable Version" /></a>
<a href="https://github.com/MervinPraison/PraisonAI"><img src="https://img.shields.io/badge/License-MIT-yellow.svg" alt="License" /></a>
</p>

PraisonAI is an AI Agents Framework with Self Reflection. PraisonAI application combines PraisonAI Agents, AutoGen, and CrewAI into a low-code solution for building and managing multi-agent LLM systems, focusing on simplicity, customisation, and efficient human–agent collaboration.

## Key Features

- 🤖 Automated AI Agents Creation
- 🔄 Use CrewAI or AutoGen Framework
- 💯 100+ LLM Support
- 💻 Chat with ENTIRE Codebase
- 🖥️ Interactive UIs
- 📄 YAML-based Configuration
- 🛠️ Custom Tool Integration
- 🔍 Internet Search Capability (using Crawl4AI and Tavily)
- 👁️ Vision Language Model (VLM) Support
- 🎙️ Real-time Voice Interaction

## Using No Code

### Auto Mode:
```bash
pip install praisonai python-dotenv instructor
export OPENAI_API_KEY=xxxxxxxxxxxxxxxxxxxxxx
praisonai --auto create a movie script about Robots in Mars
```

### Initialise Mode:
```bash
pip install praisonai python-dotenv instructor
export OPENAI_API_KEY=xxxxxxxxxxxxxxxxxxxxxx
praisonai --init create a movie script about Robots in Mars
praisonai
```

## Using Coding

Light weight package dedicated for coding:
```bash
pip install praisonaiagents
```

```bash
export OPENAI_API_KEY=xxxxxxxxxxxxxxxxxxxxxx
```

Create app.py file and add the code below:
```python
from praisonaiagents import Agent, Task, PraisonAIAgents

# 1. Create agents
researcher = Agent(
    name="Researcher",
    role="Senior Research Analyst",
    goal="Uncover cutting-edge developments in AI and data science",
    backstory="""You are an expert at a technology research group, 
    skilled in identifying trends and analyzing complex data.""",
    verbose=True,
    llm="gpt-4o",
    markdown=True
)
writer = Agent(
    name="Writer",
    role="Tech Content Strategist",
    goal="Craft compelling content on tech advancements",
    backstory="""You are a content strategist known for 
    making complex tech topics interesting and easy to understand.""",
    llm="gpt-4o",
    markdown=True
)

# 2. Define Tasks
task1 = Task(
    name="research_task",
    description="""Analyze 2024's AI advancements. 
    Find major trends, new technologies, and their effects.""",
    expected_output="""A detailed report on 2024 AI advancements""",
    agent=researcher
)

task2 = Task(
    name="writing_task",
    description="""Create a blog post about major AI advancements using the insights you have.
    Make it interesting, clear, and suited for tech enthusiasts. 
    It should be at least 4 paragraphs long.""",
    expected_output="A blog post of at least 4 paragraphs",
    agent=writer,
)

agents = PraisonAIAgents(
    agents=[researcher, writer],
    tasks=[task1, task2],
    verbose=False,
    process="hierarchical",
    manager_llm="gpt-4o"
)

result = agents.start()
```

Run:
```bash
python app.py
```

## Ollama Integration
```bash
export OPENAI_BASE_URL=http://localhost:11434/v1
```

## Groq Integration
Replace xxxx with Groq API KEY:
```bash
export OPENAI_API_KEY=xxxxxxxxxxx
export OPENAI_BASE_URL=https://api.groq.com/openai/v1
```

## Logging
```bash
export LOGLEVEL=info
```

Advanced logging:
```bash
export LOGLEVEL=debug
```

<div align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="images/architecture-dark.png" />
    <source media="(prefers-color-scheme: light)" srcset="images/architecture-light.png" />
    <img alt="PraisonAI Architecture" src="images/architecture-light.png" />
  </picture>
</div>

## Different User Interfaces:

| Interface | Description | URL |
|---|---|---|
| **UI** | Multi Agents such as CrewAI or AutoGen | [https://docs.praison.ai/ui/ui](https://docs.praison.ai/ui/ui) |
| **Chat** | Chat with 100+ LLMs, single AI Agent | [https://docs.praison.ai/ui/chat](https://docs.praison.ai/ui/chat) |
| **Code** | Chat with entire Codebase, single AI Agent | [https://docs.praison.ai/ui/code](https://docs.praison.ai/ui/code) |

## Google Colab Multi Agents

|               | Cookbook        | Open in Colab                                                                                                                                                                                                                                  |
| ------------- | --------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Basic         | PraisonAI       | <a target="_blank" href="https://colab.research.google.com/github/MervinPraison/PraisonAI/blob/main/cookbooks/praisonai-googlecolab.ipynb"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab" /></a>       |
| Include Tools | PraisonAI Tools | <a target="_blank" href="https://colab.research.google.com/github/MervinPraison/PraisonAI/blob/main/cookbooks/praisonai-tools-googlecolab.ipynb"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab" /></a> |

## Install

| PraisonAI | PraisonAI Code | PraisonAI Chat |
| --- | --- | --- |
| `pip install praisonai` | `pip install "praisonai[code]"` | `pip install "praisonai[chat]"` |

## TL;DR Multi Agents

```bash
pip install praisonai
export OPENAI_API_KEY="Enter your API key"
praisonai --init create a movie script about dog in moon
praisonai
```

## Prerequisite:
### Export API KEY

```bash
export OPENAI_API_KEY="Enter your API key"
```

## Installation

```bash
pip install praisonai
```

## Automatically Create Agents to Perform a Task

```bash
praisonai --init create a movie script about dog in moon
```
## Run
```bash
praisonai
```
