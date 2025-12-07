# GPT4All Local Generation and Chatbot Suite

This repository contains a complete set of experiments and interfaces built with GPT4All using the Mistral 7B instruct model. The project demonstrates text generation, style experiments, poetry generation, multi parameter output exploration, and an interactive Gradio based local chatbot. All generation runs fully offline using a locally stored GGUF model.

This repository is designed for developers, researchers, and students who want to understand local LLM workflows, controlled text generation, and practical real world chatbot implementation without relying on cloud APIs.

## Features

1. Local inference with GPT4All using the Mistral 7B instruct model in GGUF format
2. Text generation with multiple prompts and adjustable parameters
3. Poetry generation in various formats including sonnet, haiku, limerick, acrostic, free verse
4. Multi parameter test runs that simulate iterative generation similar to epochs
5. Full Gradio chatbot with context management, adjustable settings, examples, and quick actions
6. Custom generation functions for stories, poems, and structured outputs
7. Clean architecture with reusable generation utilities

## Installation

Install all dependencies using pip. The environment must support Python 3.10 or later.

```
pip install gpt4all gradio
```

Make sure your system has enough storage for the Mistral model file. GPT4All will automatically download the GGUF model when loaded.

## Model Used

Model name
mistral-7b-instruct-v0.1.Q4_0.gguf
This is a four bit quantized version of Mistral 7B, optimized for CPU inference and local generation.

## Text Generation Examples

The repository includes a script that generates text samples from multiple prompts.
Each generation uses configurable temperature, top-k, and top-p values. This allows you to explore how sampling parameters influence creativity, randomness, and coherence.

Prompts include
Once upon a time in a distant galaxy
The future of artificial intelligence will
In a small village near the mountains
The secret to happiness is
When the clock struck midnight

The script prints five generations along with separators for readability.

## Parameter Testing (Epoch Simulation)

A separate script demonstrates how varying generation parameters affects model output across multiple runs. While GPT4All does not support fine tuning, adjusting temperature and sampling diversity can act as a soft simulation for iterative refinement.

For each generation
Temperature increases from 0.5 to 0.75 across five runs
Top-k and top-p remain fixed
Repeat penalty is applied for better diversity control

This helps users understand how controlled parameter variation affects output stability and creativity.

## Poetry Generation

The repository includes a dedicated poetry generation pipeline that covers multiple forms
Romantic poems
Nature poems
Haiku
Style based poems such as
Sonnet
Limerick
Free verse
Acrostic

Each poem uses separate sampling values to maintain stylistic consistency.

## Gradio Chatbot Interface

A full interactive chatbot interface is provided using Gradio.
Key components include

Conversation memory with the last three interactions
Custom generation handler
Adjustable maximum tokens
Temperature control
Top-p tuning
Random poem generation
Quick action buttons for predefined prompts
Example prompts for fast testing
Chat cleanup and full interface refresh

The interface uses the Gradio Blocks API with a clean layout containing a chat window, user input, action buttons, sliders, and markdown documentation.

To launch the interface, run the script containing the Gradio block. At the end of execution, the app will start locally and can optionally be shared publicly.

## Usage

Text generation

```
from gpt4all import GPT4All

model = GPT4All("mistral-7b-instruct-v0.1.Q4_0.gguf")
response = model.generate("Your prompt here", max_tokens=150)
print(response)
```

Running the Gradio chatbot

```
python your_file_name.py
```

The interface will open in your browser.

## Notes on Model Behavior

GPT4All does not support traditional fine tuning.
However, output quality can be improved through
Prompt engineering
Temperature control
Top-p sampling
Repeat penalty
Context management
Structured prompt templates

These techniques are demonstrated throughout the scripts in this repository.

## Recommended Hardware

At least 8 GB RAM for smooth generation
Faster CPUs improve throughput
GPU is not required since GPT4All runs on CPU
SSD is recommended for model loading speed

## Project Goals

Provide a complete playground for local LLM experimentation
Enable students and developers to learn practical text generation without cloud cost
Showcase Mistral 7B capabilities in offline mode
Deliver a production ready chatbot framework using Gradio
Provide modular code that can be extended for
Tutors
Assistants
Poetry bots
Story generators
Local knowledge assistants


