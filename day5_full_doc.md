Day5 of #Days of AI PM 

Mitigating AI Hallucinations: A Technical & Strategic Overview (2025)
by MuniRajesh Parvathireddy

AI hallucinations refer to confident, yet false outputs from large language models (LLMs). They commonly appear in applications involving search, healthcare, legal, and customer service. Addressing this challenge requires a three-pronged strategy: Prevention, Detection, and Containment.


I. Prevention: Reducing Hallucinations at the Source

1. Improved Training Data

Curated Datasets

Use semantic clustering and Wikidata cross-referencing.

Example: Google's HEALTHVER

Cost: $2-5M per 1B tokens (Anthropic, 2024)


Synthetic Data Augmentation

Generate hallucinated examples and label them "invalid"

Tool: NVIDIA NeMo Curator


Bias Mitigation

Techniques: adversarial filtering and reweighting

IBM reports a 30-60% reduction in stereotype hallucinations



2. Architectural Solutions

Retrieval-Augmented Generation (RAG)

Combines FAISS/ElasticSearch retrieval with LLM grounding

Used in IBM Watson (medical diagnostics)


Tool-Augmented Models

Integrates Wolfram Alpha, Bing, Google Fact Check Tools

Adds 300-800ms latency



3. Training Techniques

Constitutional AI

Enforces rules like “Never invent historical events”

Self-critiquing model: 75% hallucination drop (Anthropic, 2023)


Process Supervision

Reward correct reasoning steps, penalize logical leaps


Reinforcement Learning from Human Feedback (RLHF)

Human ratings guide model fine-tuning

Cost: $50K-$200K per 10K samples



II. Detection: Real-Time Identification

1. Uncertainty Quantification

Confidence Scores

Softmax-based probabilities

Example: "France's capital is Paris [87% confidence]"


Monte Carlo Dropout

Perform 30x inference with dropout

σ > 0.3 flags high hallucination risk

3x slower inference



2. Verification Systems

Self-Verification (Chain-of-Verification)


response = generate("Einstein's birth year")
questions = plan_verification(response)  # → ["Was Einstein born in 1879?"]
answers = independently_answer(questions)
if contradiction: revise_response()

External Verification

APIs: Google FactCheck Tools

Embedding similarity threshold < 0.7 flags risk



III. Containment: Harm Reduction

1. Human-in-the-Loop (HITL)

+----------------+-------------------------------------+--------------------+
|  Risk Level    |       Tech Stack Example            |   Response Time    |
+----------------+-------------------------------------+--------------------+
|  High-Risk     |  Expert platform (e.g., Scale AI)   |     < 2 hours      |
|  Medium-Risk   |  Crowdsourced review (e.g., MTurk)  |     < 24 hours     |
|  Low-Risk      |  No review (auto-log for audit)     |        N/A         |
+----------------+-------------------------------------+--------------------+

2. User-Facing Safeguards

Include citations: "[Claim] [Source: NEJM, 2023]"

Friction mechanisms: pause outputs for legal/medical contexts


3. Post-Hoc Auditing

Red Teaming

Use prompt injections

Tools: LangChain RedTeamGPT

IV. Emerging Approaches

Multimodal Grounding: Cross-verify text with image/audio

Watermarking: Embed undetectable patterns in output

Neuro-Symbolic AI: Use LLMs + logic checkers (e.g., Prolog)


V. Trade-offs & Operational Frameworks

Key Trade-offs

+---------------------+-----------------------------+---------------------------+---------------------------+
|     Mitigation      |         Best For            |        Worst For          |        Cost Factor        |
+---------------------+-----------------------------+---------------------------+---------------------------+
| RAG                 | Domain-specific chatbots     | Open-ended creativity     | $10K–$50K deployment      |
| Confidence Scores   | Technical users              | General public            | <1% inference overhead    |
| HITL                | Medical diagnosis            | Consumer chatbots         | $20–$100/hr per review    |
| Self-Verification   | Simple factual queries       | Multi-hop reasoning       | 2–3x latency              |
+---------------------+-----------------------------+---------------------------+---------------------------+

Operational Principles

Risk-Adaptive Design


if domain in ["medical", "legal"]:
    enforce = [RAG, HITL, Citations]
elif domain == "creative":
    enforce = [Watermarking]

Continuous Monitoring

Track Hallucination Rate (HR)

Trigger alerts if HR > 5%


User Education

Tutorials: "See how this AI invented a fake court case"

Prompt guides for factual grounding



The Reality Check

State-of-the-art models still hallucinate 3–15% (Meta, 2024)

Combined techniques reduce this to <2% in controlled settings

Key goal: Build resilient, not flawless, systems

Linkedin reflection: https://www.linkedin.com/posts/pmrajesh_ai-hallucination-activity-7344439193948835840-KdcX
Thank You!
Presented by MuniRajesh Parvathireddy
Please follow me on LinkedIn → linkedin.com/in/pmrajesh

