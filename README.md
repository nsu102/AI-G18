# Read the Room: Context-Aware and Personalized Emoticon Recommendation from Chat History

> **ITE351 AI & Applications — Group Project Proposal (Option B)**

## Team Members

| Name       | Organization | Email               |
| ---------- | ------------ | ------------------- |
| Shin Yunsu | infosys HYU  | ynsu102@gmail.com   |
| Yeo Dakyum | infosys HYU  | yeodakyum@gmail.com |


## Research Idea

**Title:** Read the Room: Context-Aware and Personalized Emoticon Recommendation from Chat History

**Proposal:**

Existing emoticon (sticker) recommenders in messaging apps match keywords or sentence similarity, so they miss sarcasm, jokes, and the reaction a situation actually calls for. They also depend on creators manually tagging every PNG, and a single tag rarely captures how an emoticon is really used.

We propose a context-aware and personalized emoticon recommender that maps both sides into a shared semantic space: a conversation becomes _"what reaction is needed,"_ and each image becomes _"when it can be used."_ Offline, Qwen2.5-VL interprets each emoticon (expression, embedded text, emotion, tone, intent) as JSON and generates 5–10 Korean dialogues where it fits, with no human-written data. Duplicates and unsuitable samples are filtered automatically, and scenarios are indexed in FAISS using Qwen3-Embedding-0.6B. Online, an LLM extracts emotion, intent, and tone from recent messages; the system retrieves the Top-50 candidates and reranks them to return the Top-5. For personalization, each user's explicit preferences and selection history become ranking features, and a LightGBM ranker is trained once enough logs are collected. We will evaluate retrieval quality (Recall@5, MRR) on a separate set of real conversations.

