![Computational Field Notes — Raihan Mahmud. Machine learning, language and software, illustrated by a geometric graph and an abstract embedding field.](assets/profile-banner.svg)

# Hi, I'm Raihan Mahmud.

I'm an AI/ML enthusiast interested in machine learning, deep learning, and the software that makes models useful. My projects span Bangla language tools, applied machine learning, AI-assisted workflows, and database-backed applications.

[Portfolio Website](https://raihanbuildsvercelapp.vercel.app/) · [GitHub](https://github.com/RaihahMahmud) · [Selected projects](#01--selected-work) · [Research interests](#02--research-questions) · [Toolkit](#03--engineering-toolkit)

> **Computational field notes**<br>
> A record of what I build, how it works, and the questions I want to investigate next.

## In the lab / Currently building

> **EgoRecover-JEPA** · Ongoing research<br>
> Pattern recognition · Neural networks · Deep learning · Video understanding

I'm investigating whether a frozen V-JEPA 2.1 video model can support robust egocentric action anticipation when the frames immediately before an action suffer motion blur, hand–object occlusion, or both. The approach aims to recover semantic information in latent feature space rather than reconstruct video pixels.

- **Implemented & pilot-tested:** a clean-video baseline with a frozen encoder and trainable attentive probe for verb, noun, and action prediction. An end-to-end pilot on one EPIC-KITCHENS video produced saved outputs, a trained probe, and graphs. Single-pass FFmpeg decoding and cached encoder features reduce repeated computation.
- **Scale-up prepared; evaluation pending:** resumable downloads with size/checksum validation and a Kaggle/Colab notebook with video-level splitting to keep videos separate across training and held-out data. Artifact backups support moving between environments; the larger-scale evaluation has not yet completed.
- **Next:** controlled blur and occlusion generators, followed by a reliability estimator, V-JEPA predictor-based latent recovery, and a learned gate combining observed and predicted features. These components and their comparisons with the baseline remain planned.

**Planned evaluation:** EPIC-KITCHENS-100; verb, noun, and action Recall@5 under clean and corrupted conditions, with multiple seeds, context-length ablations, and confidence intervals. Results will be reported after these experiments finish.

<sub>Python · PyTorch · V-JEPA 2.1 · Hugging Face Transformers · FFmpeg · pandas · matplotlib · Kaggle · Google Colab · rclone · Google Drive</sub>

## 01 / Selected work

<!-- To update: keep a small selection, verify claims against source, and link to the most useful artifact. -->

### [FlyRank · Content opportunity scoring](https://github.com/RaihahMahmud/FlyRank-AI--starter-ML-Internship-)

**Applied ML / evaluation**

A capstone notebook exploring how historical search signals can help prioritize pages for human review. It aggregates page-level data with DuckDB and pandas, then compares standardized logistic regression with a rule-based baseline using a client-grouped train/test split.

The target is observed click volume above the training-set median. This is a proxy task; its evaluation does not establish that refreshing a page will improve future traffic.

`Python` `scikit-learn` `pandas` `DuckDB`<br>
[Read the capstone notebook](https://github.com/RaihahMahmud/FlyRank-AI--starter-ML-Internship-/blob/main/work/notebooks/capstone.ipynb)

### [Bangla Grammar Chatbot](https://github.com/RaihahMahmud/Bangla_grammar_Chatbot_299project)

**Language technology / model adaptation**

A Bangla language learning project with training code and local inference diagnostics for idiom explanations and word simplification. The Colab script configures Qwen2.5-1.5B-Instruct with 4-bit loading and LoRA adapters through Unsloth, using instruction/input/output examples for supervised fine-tuning.

This is an experimental workflow; the repository does not establish a benchmarked model release.

`Python` `PyTorch` `Unsloth` `PEFT / LoRA` `TRL`<br>
[Inspect the training script](https://github.com/RaihahMahmud/Bangla_grammar_Chatbot_299project/blob/main/%23%23CollabCodeForModeltrain.txt) · [Inference diagnostics](https://github.com/RaihahMahmud/Bangla_grammar_Chatbot_299project/blob/main/test_model.py)

---

### [TalentFlow · Synapse AI](https://github.com/RaihahMahmud/TalentFlow_synapse_AI_B2B)

**Applied AI / full-stack engineering**

A recruiting application with structured CV extraction and candidate-to-requisition scoring. The Gemini integration uses Zod schemas for structured output; the scoring code computes weighted skill overlap to ground its model prompt. A Next.js application and a Prisma/PostgreSQL data layer connect the AI features to the product.

`TypeScript` `Next.js` `React` `Gemini API` `Prisma` `PostgreSQL`<br>
[CV extraction](https://github.com/RaihahMahmud/TalentFlow_synapse_AI_B2B/blob/main/src/lib/cv-parsing.ts) · [Scoring implementation](https://github.com/RaihahMahmud/TalentFlow_synapse_AI_B2B/blob/main/src/lib/scoring/score-candidate.ts)

### [AetherFlow AI](https://github.com/RaihahMahmud/AetherFlow-AI)

**Generative AI / application prototype**

A React prototype that turns a business-process description into an automation strategy. It requests schema-constrained JSON from Gemini and displays suggested steps and technologies. Generated savings estimates are suggestions from the model, not measured business outcomes.

`TypeScript` `React` `Gemini API`<br>
[Inspect the generation service](https://github.com/RaihahMahmud/AetherFlow-AI/blob/main/services/geminiService.ts)

### [TechWheels · Fleet database](https://github.com/RaihahMahmud/TechWheels_DB_SQL_project_CUNY)

**CS foundations / relational systems**

A vehicle-sharing management project covering members, hubs, vehicles, reservations, and maintenance. Its relational schema uses foreign keys and constraints; the Flask/SQLite application implements CRUD operations and fleet, revenue, and member-activity reports.

`Python` `Flask` `SQLite` `SQL`<br>
[Database schema](https://github.com/RaihahMahmud/TechWheels_DB_SQL_project_CUNY/blob/main/techwheels_project/db/schema.sql) · [Application source](https://github.com/RaihahMahmud/TechWheels_DB_SQL_project_CUNY/blob/main/techwheels_project/app/flask_app.py)

## 02 / Research questions

My developing research interests sit between language, learning, and evaluation:

- **Useful language models:** adapting models for Bangla tasks, and understanding where their answers fail.
- **Evaluation that matches the task:** choosing labels, baselines, and data splits that support meaningful conclusions.
- **Efficient adaptation:** learning more about LoRA and the tradeoffs between model size, memory, and task quality.
- **Reproducible intelligent systems:** connecting experiments to inspectable code, clear limitations, and practical applications.

These are directions I want to develop further through machine learning, deep learning, NLP, and software engineering.

## 03 / Engineering toolkit

Tools represented in the projects above:

| Area | Project experience |
| :--- | :--- |
| Languages | Python · TypeScript · SQL |
| ML & model adaptation | scikit-learn · PyTorch · Unsloth · PEFT / LoRA · TRL |
| Data & experiments | pandas · NumPy · DuckDB · Jupyter / Colab |
| Frontend | React · Next.js |
| Backend & AI integration | Flask · Gemini API · Zod |
| Databases & workflow | SQLite · PostgreSQL · Prisma · Git / GitHub |

## 04 / Current direction

The thread connecting this portfolio is a move from model experiments toward useful applications. My learning priorities are stronger ML/DL fundamentals, clearer evaluation, and better documentation of how a model behaves inside a software system.

## 05 / Connect

Visit my [Portfolio Website](https://raihanbuildsvercelapp.vercel.app/), explore my [public repositories](https://github.com/RaihahMahmud?tab=repositories), or follow my work on [GitHub](https://github.com/RaihahMahmud).

<sub>Computational Field Notes · Raihan Mahmud</sub>
