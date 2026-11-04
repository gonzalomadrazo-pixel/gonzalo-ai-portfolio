# AI Projects | Gonzalo

I build software with AI tools and test what it can do in practical settings. These projects cover three different uses of AI: turning a large set of customer reviews into product insights, building a private research assistant, and training a tiny language model from scratch. Each description below explains the project without requiring you to open another README.

## Selected projects

### Spotify Review Insight Pipeline

**The problem:** App reviews are useful, but tens of thousands of comments are too much to read one by one. A product team needs to know what users complain about most and which issues deserve attention.

**What it does:** This project analyzes Google Play reviews of Spotify for Android and produces a ranked recommendation about where product effort should go: access, usability, playback, or billing and support. The final run processed a declared set of 100,063 reviews: 100,050 non-empty reviews were classified and 13 empty ones were set aside.

**How AI is used:** A local language model reads each review and assigns structured labels such as topic, intent, and severity. Separate model stages enrich the review, check the labels, group related complaints, and help draft a recommendation. The code keeps the stages and saved results inspectable, so a reviewer can trace how the summary was produced.

**What I built around the model:** Data checks, caching, resumable runs, cost and runtime tracking, evaluation against human-labeled examples, a second-pass verifier, synthetic tests for planted errors and prompt injection, and a dashboard for exploring the results. The final run used a local Gemma model through Ollama; reported API spend was $0.

- [Source code, methods, and evaluation](https://github.com/gonzalomadrazo-pixel/spotify-review-pipeline)
- [Explore the live dashboard](https://spotify-review-insights-beta.vercel.app)
- **Tools:** Python, Gemma, Ollama, React/TypeScript, Vercel

### Personal Investing Wiki

**The problem:** Notes from books and investor letters are hard to search, and a general chatbot may answer from memory without showing where a claim came from.

**What it does:** This is a local study assistant for notes about five investors. You can search for matching passages, ask a factual question and get an answer with source citations, or chat with a study partner that remembers the conversation. If the notes do not support an answer, ask mode is designed to say that the evidence is insufficient. An ingestion command turns source notes into linked pages for an Obsidian wiki.

**How AI is used:** A local Gemma model helps turn source notes into structured wiki pages and writes answers from passages retrieved from those notes. A local embedding model helps find conceptually related passages, while the answer includes references back to its evidence. The models run on the computer through Ollama, so the core workflow works offline.

**What I built around the model:** The Python command-line app, the separate search/ask/chat modes, citation handling, source ingestion, the Obsidian page structure, and offline checks for answer quality and whether the assistant abstains when it should.

- [Source code, notes, and evaluation](https://github.com/gonzalomadrazo-pixel/personal-wiki)
- **Tools:** Python, Gemma, Ollama, local embeddings, Obsidian

### Custom LLM: nanoGPT experiments

**The problem:** I wanted to see what a small language model actually learns from training data, and how to tell a real improvement from a misleading score.

**What it does:** This project trains a small next-word prediction model using Karpathy's nanoGPT. I ran a baseline on the course corpus, then a second experiment that adds examples for opposites and negation. Both models were compared on the same 48 fixed evaluation questions. The baseline model improved from 9/48 before training to 20/48 after training; the expanded-corpus model reached 27/48.

**How AI is used:** The model learns to predict the next word from examples in its training corpus. It is a small language-model experiment, not a general-purpose chatbot. Control tests show that part of the apparent improvement on negation came from how often words appeared in the training data, rather than the model reliably understanding negation.

**What I built around the model:** The training experiments, corpus changes, evaluation set, control tests, executed notebooks, terminal chat, and an interactive browser dashboard that lets people try the trained models and inspect results.

- [Source code, notebooks, and results](https://github.com/gonzalomadrazo-pixel/custom-llm-project)
- [Try the interactive dashboard](https://gonzalomadrazo-pixel.github.io/custom-llm-project/dashboard.html)
- **Tools:** Python, PyTorch, nanoGPT, HTML/JavaScript

## What these projects show

- Applying AI to different jobs: classification and synthesis, evidence-based question answering, and next-word prediction
- Building the surrounding software that makes model output useful: data processing, retrieval, evaluation, interfaces, and repeatable runs
- Measuring limitations and documenting when a result should not be trusted
