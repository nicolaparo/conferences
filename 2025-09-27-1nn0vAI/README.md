# Ollama: Local AI for Raspberry Pi
## Conference Presentation by Nicola Paro

Welcome to the repository for my conference presentation on bringing local AI capabilities to Raspberry Pi devices using Ollama. Here, you'll find resources and insights from my talk, aimed at demystifying the process of running Large Language Models (LLMs) locally, and exploring the practicalities, benefits, and challenges involved.
## Slide Deck

You can view the full presentation slides below:

<embed src="./presentation.pdf" type="application/pdf" width="100%" height="600px" />

## Overview

In this presentation, I share my journey and findings on deploying LLMs directly on Raspberry Pi hardware. The motivation stems from a desire to enhance privacy, reduce costs, and enable offline AI functionality—making advanced language models accessible even in disconnected or resource-constrained environments.

## Key Topics Covered

### Why Use Local LLMs?

Running LLMs locally offers several compelling advantages. First and foremost is privacy: your data remains on your own devices, never leaving your internal network. This is especially important for sensitive applications or when working in environments without reliable internet access. Throughout the presentation, I also address the hype surrounding AI and help distinguish genuine needs from trends.

### Hardware Requirements

To achieve meaningful performance, I recommend using a Raspberry Pi 5 equipped with a 64-bit ARM CPU and at least 16GB of RAM. Storage is also important—a 64GB or larger microSD card is ideal. Active cooling, such as a heat sink, is essential to maintain stability during intensive workloads.

### Software Stack

The software setup is straightforward but powerful. Raspberry Pi OS serves as the foundation, with the .NET runtime providing a robust environment for development. Ollama acts as the LLM runner, supporting a wide range of open-source models. This combination allows for flexibility and experimentation with different AI capabilities.

### Available Models

One of the highlights is the sheer variety of models you can run locally. From Llama 3.1/3.2 and Gemma 2/3 to Qwen 2.5 and Mistral, the options are extensive—over 100 models are available for exploration. Each model brings unique strengths, and the presentation discusses how to select the best fit for your use case.

### Cost Analysis

A key consideration is cost. Running models locally is surprisingly affordable, with execution costs around 0.13€ per million tokens. I compare this to popular cloud services like GPT-4 and GPT-3.5, and also touch on energy consumption, which is a critical factor for always-on deployments.

### Technical Implementation

The technical section dives into the details of LLM runners, comparing Ollama, LM Studio, and Foundry Local. I discuss how to choose models based on their parameters and capabilities, integrate tools and function calling, and manage memory effectively to avoid bottlenecks.

### Orchestration Frameworks

Orchestration is vital for building practical applications. I compare Semantic Kernel and LangChain, and introduce my own "Coleman Method"—a lightweight approach tailored for Raspberry Pi. Various patterns for tool integration are explored, showing how to combine multiple models and functionalities.

### Demo Application Features

To illustrate the concepts, I present a demo application featuring weather information retrieval, Wikipedia search, light control integration, and multi-model orchestration. These examples demonstrate the real-world potential of local AI on Raspberry Pi.

## Installation Steps

Getting started is simple. Begin by flashing Raspberry Pi OS using the official Imager tool. Enable SSH for remote access, then install the .NET runtime with a few shell commands:

```bash
curl -sSL https://dot.net/v1/dotnet-install.sh | bash /dev/stdin --channel STS
echo 'export DOTNET_ROOT=$HOME/.dotnet' >> ~/.bashrc
echo 'export PATH=$PATH:$HOME/.dotnet' >> ~/.bashrc
source ~/.bashrc
```

Next, install Ollama and configure your chosen models. With these steps, your Raspberry Pi is ready to run local LLMs.

## Remote Access Options

Managing your device remotely is easy. SSH is enabled by default, but you can also use Raspberry Pi Connect for browser-based access or Tailscale VPN for secure networking across devices.

## Model Recommendations

Based on my experiments, I recommend:
- **Qwen2.5:3b** – Lightweight, precise, and excellent at invoking tools.
- **Llama3.1/3.2** – High quality, though sometimes prone to over-invoking tools.
- **Gemma 3** – Delivers good responses, but lacks tool support.

## Key Findings

Building your own local AI solution is a rewarding learning experience. However, resource limitations mean optimization is crucial, especially regarding hardware cooling and power management. While there are practical constraints, the educational value and insights gained are significant.

## Conclusions

Running LLMs on Raspberry Pi is not without its challenges, but it’s an excellent way to understand the intricacies of local AI deployment. You’ll gain hands-on experience with resource management, privacy trade-offs, and the technical details that underpin modern AI systems.

## Author

**Nicola Paro**
- Solutions Architect @ beanTech
- .NET & Azure Meetup Štajerska Community Lead
- [LinkedIn](https://www.linkedin.com/in/nicolaparo/)

## Files in this Repository

- `output.md` – Full presentation content
- `presentation.pdf` – Slide deck
- `README.txt` – This file

---

Conference: 1nn0vAI 2025  
Date: September 27, 2025
