### Core Concept

Two interacting **Federated Learning** models that run continuously across the fleet:
1. **Real-time Performance Degradation Model (The Green PdM)**:
	- **Input**: High-frequency sensor data (fuel flow, RPM, speed through water, power output, exhaust temperature, etc.) from across the fleet.
	- **Function**: Instead of just predicting a "failure," this FL model will calculate a real-time value (*"Efficiency Delta"*) for each vessel compared to its ideal performance benchmark (e.g., from sea trials). It learns the subtle patterns of performance loss long before a critical alarm.
	- **Output**: A live efficiency score for every vessel (e.g., Vessel A is at 98% efficiency, Vessel B is at 93%).
		- PdM per ship's mechanical component. 
	- **Model**: Probably an LSTM type of model. It captures best the task of time-series.
2. **AI Co-sailor & Decarbonization Engine (Contextual & Recommendation Engine)**:
	- **Input**: The *"Efficiency Delta"* scores from Model 1, fused with *unstructured text data* (engineer logs, reports, port documents) and *voyage data.*
	- **Function**: This engine is powered by a Federated Maritime Language Model (FM-LLM). It interprets the unstructured text to understand the context behind the efficiency score. It then uses this holistic understanding to generate intelligent, fleet-wide recommendations.
	- **Output**: Actionable recommendations that are not just data points, but complete, explainable narratives. These results directly lead to reduced emissions and improved environmental performance.
	- **Model**: The fine-tuned LLM.

### Federated Maritime Large Language Model (FM-LLM)

- **Federated Fine-Tuning:** A central LLM is pre-trained on general maritime knowledge. A smaller version is deployed to each vessel and is continuously fine-tuned using the ship's own private logs and reports.
	- Existing open-source models (Llama3, Gemma, etc) using specialised maritime data. 
- **Privacy-Preserving Learning:** Using Federated Learning, only the anonymised model improvements are sent to the central server. The raw, sensitive text logs never leave the ship.
- **Collective Intelligence:** These updates are aggregated, creating a powerful FM-LLM that possesses the collective, nuanced experience of all 80+ vessels.
	- Flower, TensorFlow Federated for maritime context.

An example on the powerful conversational interface–an operator can now simply ask:

> **Operator Query:** "Why is Vessel B's CII rating projected to drop next quarter?"
> 
> **EmpowerAI Response:** "Vessel B's CII is at risk due to a 3% increase in fuel consumption. I have correlated this with repeated log entries from the Chief Engineer mentioning 'intermittent fuel injector alarms under high load'. This pattern is similar to the one observed on Vessel D two months before its injector failure. I recommend scheduling a fuel injector service at its next port of call in Singapore."

### Data Sovereignty and Scale

- **Privacy**: FL allows a global model to be trained on data from all 80+ vessels without the raw data ever leaving the ship. Only anonymised model updates are shared.
- **Robustness**: The model learns from the collective intelligence of the entire fleet. The FM-LLM can identify patterns across vessels that a single human or ship-specific model would miss.
- **Scalability**: The architecture is inherently scalable. Adding a new vessel to the federation is simple and immediately enhances the collective intelligence.

### GreenAI at Core

The system's primary objective is to optimize for environmental and financial performance by providing explainable intelligence.

- **CII-Aware Logic:** The AI's decision-making is directly linked to the vessel's CII rating. The LLM provides the **causal narrative** for *why* the rating is at risk, making the recommendations more <u>trustworthy</u> and <u>actionable</u>.
- **Holistic Fuel Optimization:** It understands the full context, the what from the sensors and the why from the logs, to make smarter fleet-level trade-offs.

### Outcomes and KPIs

- **Directly Improved CII Ratings:** Achieve and maintain higher CII ratings across a larger percentage of the fleet.
- **Reduced Fuel:** Target a 5-8% reduction in overall fleet fuel consumption.
- **Data-Driven Maintenance:** Shift >50% of scheduled maintenance from time-based intervals to condition-and-efficiency-based interventions recommended by the AI, backed by a clear, text-based rationale.
	- *time-based intervals:* This method relies on a fixed, pre-determined schedule based on the manufacturer's recommendations or standard industry practice. "The main engine must be overhauled every 20,000 running hours.".
		- This approach completely ignores the actual condition of the engine.
		- The ship may have had smooth sailing in calm seas with high-quality fuel (wasteful).
		- The ship may have experienced rough weather and used lower-quality fuel, causing accelerated wear and carbon buildup (too late).
	- *condition-and-efficiency-based interventions:* This is a dynamic, data-driven approach that triggers maintenance based on real-time data and its impact on key business objectives (like fuel cost and CII rating).
		- Continuously monitoring Efficiency Delta.
		- At some point the system detects the engine is consuming 4% more fuel to produce the same power output (efficiency-based trigger).
		- Vibration sensors might show a slight increase in a specific frequency (condition-based indicator).
		- The combination of triggers: 
		 > ALERT: Main engine efficiency has degraded by 4%. Projected impact over the next 3 months: +$180,000 in fuel costs and a potential drop in CII rating from C to D. An overhaul at the next port of call in Rotterdam is recommended. Estimated ROI on maintenance cost is 4 months through fuel savings.
- **Enhanced Fleet Reliability:** Retain the benefit of predictive failure warnings, enriched with contextual clues from human observations, from the underlying performance model, reducing unplanned downtime.
- **Enhanced Decision Velocity:** Reduce the time-to-decision for complex operational issues by 30% by enabling rapid, conversational data exploration.
- **Knowledge Capture and Retention:** The FM-LLM acts as a "digital memory" for the fleet, capturing the tacit knowledge of experienced crew members and making it a permanent, queryable asset for the entire organization.


### Tech Outcomes

1. **A Specialized Federated Maritime LLM:**
    - A pre-trained **Foundation Maritime Model** built on comprehensive maritime knowledge.
    - A lightweight, **Edge-Optimized Model** variant designed for efficient, federated fine-tuning on vessel hardware.
2. **A Data Ingestion & Contextualization Engine:**
    - An automated pipeline to parse and digitize unstructured data (logs, reports, circulars).
    - A **Retrieval-Augmented Generation (RAG)** architecture to ensure responses are factually grounded and context-aware.
    - A correlation engine to link textual insights with quantitative sensor data anomalies.
3. **A Conversational Co-pilot Interface:**
    - A Natural Language Query (NLQ) engine enabling operators to ask complex operational questions.
    - A system for generating **explainable AI recommendations**, citing the specific data and log entries used to form its conclusions.
4. **A Federated Learning Orchestration Platform:**
    - A centralized **Federated Orchestrator** to manage the secure aggregation of model updates and the lifecycle of the global FM-LLM.
    - An **On-Vessel MLOps Agent** to manage local model fine-tuning and secure communication with the central orchestrator.

---

## KPIs and 'WHY' in the context of empowerAI

- **KPI 1**: _5–8% reduction in fuel consumption_ fleet-wide (direct impact on CII and cost)
- **KPI 2**: _At least 15% improvement_ in scheduled-vs-evidence-based (predictive) maintenance, reducing unexpected downtimes
- **KPI 3**: _Demonstrated privacy compliance_: Zero raw data leakage (EU Data Spaces alignment)
- **KPI 4**: _Scalability_: Federated learning and orchestration validated across 100+ ships, with seamless onboarding
- **KPI 5**: _Explainability metric_: Over 80% of actionable guidance rated “interpretable/useful” by crew (survey-based)
- **KPI 6**: _Deployment efficiency and responsiveness_: AI recommendations/alerts delivered to crew with under 10s latency (10s as a provisional estimate)

The maritime world is under growing pressure to boost efficiency, cut emissions and costs, and hit tighter regulatory targets (like the EU’s CII). But actually doing this is tough; ships are isolated, bandwidth is limited, and the sensitive operational data they generate tends to stay locked away on board. On top of that, many fleets depend on non-European cloud and AI services, which raises all sorts of issues around data privacy, interoperability, and EU law.

EmpowerAI: The idea is to make it possible for AI to run securely and efficiently across even these kinds of challenging environments; right at the edge, while fully respecting privacy and data sovereignty. Especially for shipping, this means valuable insights can finally be shared across the fleet (without ever sending raw data anywhere), helping everyone benefit while making sure all the rules are followed. Plus, it keeps control with European players, aligns with sustainability goals, and helps future-proof maritime operations.