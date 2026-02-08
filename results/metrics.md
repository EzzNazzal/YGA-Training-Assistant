# Model Evaluation Metrics

We evaluated three models to find the optimal balance for a student-facing chatbot.

### Model Selection Matrix

| Model | Latency | Cost | Accuracy | Tradeoff Justification |
| :--- | :--- | :--- | :--- | :--- |
| **GPT-4o-mini** | 1.5s | Low | High | Good baseline, but occasionally hallucinated on complex logistics. |
| **GPT-4.1-mini** | 1.2s | Moderate | Very High | Better instruction following but higher latency. |
| **GPT-5-mini** | **<0.8s** | **Low** | **Superior** | **SELECTED:** Provided the fastest "human-like" chat experience with high reasoning capabilities. |

### Testing Methodology
* **Golden Dataset:** A set of 20 question-answer pairs derived from actual student FAQs (e.g., Allowance amount, Absence limits).
* **Method:** These were excluded from the vector store to test generalization.
* **Result:** The system achieved a **96% Response Faithfulness** score, meaning answers were derived solely from the provided context.