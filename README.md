# AI Projects | Gonzalo

This portfolio highlights practical projects built around AI: local language models, retrieval with source citations, model evaluation, and data products. The linked repositories include code, design notes, results, and limitations.

## Selected projects

### Spotify Review Insight Pipeline

An end-to-end pipeline that turns Google Play reviews of Spotify for Android into a ranked product recommendation. The final run classified 100,050 non-empty reviews from a declared 100,063-row analysis set; 13 empty reviews were quarantined. Four inspectable model stages handle enrichment, verification, grouping, and memo writing. The project includes human-labeled evaluation, independent verification, synthetic error checks, and a live dashboard.

- [Source code and project write-up](https://github.com/gonzalomadrazo-pixel/spotify-review-pipeline)
- [Live dashboard](https://spotify-review-insights-beta.vercel.app)
- **Focus:** Python, local Gemma via Ollama, evaluation, React/TypeScript, Vercel

### Personal Investing Wiki

A local-first study assistant grounded in notes on five investors. Its Python CLI supports passage search, citation-backed answers that abstain when evidence is missing, chat with conversation memory, and ingestion into an Obsidian wiki. The model and embeddings run locally with Ollama.

- [Source code, notes, and evaluation](https://github.com/gonzalomadrazo-pixel/personal-wiki)
- **Focus:** Python, local Gemma, retrieval-augmented generation, embeddings, Obsidian

### Custom LLM: nanoGPT experiments

A small next-token model trained on two corpora and compared on 48 fixed evaluations. The trained starter model improves from 9/48 to 20/48; adding two teaching files brings the score to 27/48. The project includes control tests, executed notebooks, a terminal chat, and an interactive model dashboard. It documents why this tiny model is an experiment, not a general-purpose assistant.

- [Source code, notebooks, and results](https://github.com/gonzalomadrazo-pixel/custom-llm-project)
- [Interactive dashboard](https://gonzalomadrazo-pixel.github.io/custom-llm-project/dashboard.html)
- **Focus:** Python, PyTorch, nanoGPT, training data, evaluation, browser visualization

## What these projects explore

- Building useful workflows around language models, including local and source-grounded systems
- Making model behavior inspectable through evaluation, verification, and documented limitations
- Connecting data processing to clear, usable dashboards

