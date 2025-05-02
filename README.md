# 🎵 Music Content Generator – Transformer-based Blogging Agent

## 📌 Project Overview

This project implements an **intelligent agent-based system for generating music-themed content**, developed using [LangGraph](https://github.com/langchain-ai/langgraph), a library that enables dynamic flow definition between coordinated agents. The system is designed to **automatically write informative, engaging, and well-structured blog posts** on music topics, while keeping the user in the loop for review and feedback.

## 🧠 Key Features

The notebook provides a complete interface to generate content based on user input through a series of agentic nodes:

- 🔍 **Request classification** (event, tutorial, review)
- 🎯 **Automatic suggestion of music-related topics**
- 🌐 **Retrieval of reliable sources via [Tavily](https://app.tavily.com)**
- ✅ **Evaluation of source quality and relevance**
- 📝 **Automatic draft generation**
- 🔁 **Human-in-the-loop review (approve, rewrite, change source)**
- 🧠 **Short- and long-term memory**
- 🗓 **Automated planning of future posts**

---

## ▶️ How to Run the Notebook

### 1. Requirements

Make sure you have:
- Python 3.9+
- OpenAI and Tavily API keys (see below)

### 2. Set the API Keys

The system requires two API keys:

#### 🔑 OpenAI API Key
Used to generate text with LLMs:
- Get your key from: [https://platform.openai.com/account/api-keys](https://platform.openai.com/account/api-keys)

#### 🔑 Tavily API Key
Used to retrieve high-quality sources:
- Register and get a key from: [https://app.tavily.com](https://app.tavily.com)

Insert the keys into the notebook where indicated.

> ⚠️ If Tavily credits are exhausted, you can replace the key in the notebook to continue using semantic search.

---

## 💬 Suggested Input Examples

- `Show me the posts` – Displays previously approved posts.
- `I’d like to write a post about music` – Triggers the topic suggestion module.
- `Write a guide on how to play funk bass` – Immediately generates a post.

---

## 🛠 Flow Structure

The system is organized as a dynamic graph, with the following main nodes:

| Node              | Function                                                                 |
|-------------------|--------------------------------------------------------------------------|
| `router`          | Analyzes the user input                                                  |
| `topic_suggester` | Proposes a relevant music-related topic                                  |
| `input_classifier`| Classifies the input (event, tutorial, review)                           |
| `resource_finder` | Searches for relevant sources using Tavily                               |
| `evaluator`       | Evaluates sources based on clarity, trustworthiness, relevance           |
| `assistant`       | Generates or edits the draft based on topic and source                   |
| `human_review`    | Allows user review of the generated content                              |
| `planner`         | Automatically plans the next topic                                       |
| `show_memories`   | Retrieves previously published posts                                     |
