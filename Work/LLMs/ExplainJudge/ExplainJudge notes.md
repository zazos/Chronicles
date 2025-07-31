---
tags: llm
---

# Fine-Tuning Requirements
Both components require domain-specific adaptation, but with distinct approaches:
	•	**Narrator LLM:**
		•	Requires domain-specific fine-tuning using techniques like LoRA/PEFT
		•	Trained on:
			•	Domain lexicons (e.g., SNOMED-CT for healthcare)
			•	Regulatory phrasing templates
			•	Context-aware templating patterns
		•	Enables accurate translation of xAI outputs into domain-appropriate narratives
	•	**Judge LLM:**
		•	Requires criteria-specific fine-tuning rather than pure domain knowledge
		•	Training focuses on:
			•	Evaluation rubrics (contextual accuracy, safety, actionability)
			•	Bias mitigation techniques (swap augmentation, reference support)
			•	Scoring consistency across edge cases
		•	Can leverage generalized evaluation capabilities with task-specific prompting
	
**Implementation Insight:** Use parameter-efficient methods (LoRA) for Narrator fine-tuning, while Judge benefits more from preference optimization (DPO)

# Judge LLM Architecture

For a multi-use-case system:
•	Deployment Strategy:
	•	Single cloud-based Judge service handling all domains
	•	Communicates via API with domain-specific Narrators
	•	Scales independently of Narrator instances
•	Domain Adaptation Approach:

| Requirement          | Implementation                                                          |
| -------------------- | ----------------------------------------------------------------------- |
| Domain Knowledge     | Not embedded in Judge; sourced from Narrator outputs                    |
| Evaluation Expertise | Fine-tuned on universal pillars (accuracy/safety/actionability)         |
| Domain Nuances       | Handled through dynamic few-shot prompting with domain-specifc examples |
Critical Implementation Considerations
1.	Feedback Loop Optimization:
	•	Failed validations trigger:
		•	Narrator retraining with problematic cases
		•	Rule-set updates for xAI formatting
	•	Enabled by DeepEval’s threshold-based alerts
2.	Bias Mitigation:
	•	Implement JudgeLM techniques:
		•	Position swapping (counteracts ordering bias)
		•	Reference-supported scoring
		•	Rubric-based evaluation
3.	Cost Optimization:
	•	Fine-tuned 7B-13B Judges match GPT-4 performance at lower cost
	•	On-premise deployment avoids API expenses 