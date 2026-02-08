# Prompt Engineering Strategies

[cite_start]To ensure the "Zero-Hallucination" policy, we applied three distinct prompt engineering techniques[cite: 81].

## 1. Role Prompting (Persona)
**Objective:** Maintain the university's brand voice.
[cite_start]**Prompt:** > "You are EzzEdden, a professional assistant for HTU. Tone: Warm, Helpful, Formal." [cite: 83]

## 2. Logic Tree (Chain of Thought)
**Objective:** Prevent hallucination and searching for irrelevant topics.
**Structure:**
1.  **Step 1:** Classify Intent.
2.  **Step 2:** Check Scope.
3.  [cite_start]**Step 3:** Only if valid, use the Retrieval Tool. [cite: 85]

## 3. Negative Constraints (Hard Guardrails)
**Objective:** Strictly define what the bot cannot do.
[cite_start]**Constraint:** > "PROHIBITED: Do not answer coding questions even if asked." [cite: 87]