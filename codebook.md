# Qualitative Codebooks

Table 1 details the themes and codes derived from the semi-structured interviews in the evaluation study (N=72).

### Table 1: The codebook derived from semi-structured interviews in the evaluation study (N=72).

| **Theme** | **Code** | **Definition** |
| --- | --- | --- |
| **Balancing privacy and utility** | **Task-dependent anonymization** | Preserving task-essential details while selectively obfuscating identifiers to maintain model personalization. |
|  | **Replace precise data with broad items** | Replacing high-precision private data (e.g., exact addresses or balances) with broad, functional descriptions. |
|  | **Sensitivity-based anonymization** | Systematic removal of specific high-risk attributes (e.g., health or affiliations) regardless of their task utility. |
| **Experience towards designers' features** | **Visual encoding** | Experiences around visual encoding, which utilize color temperature and opacity to direct user focus toward risks. |
|  | **Proactive alerting** | Experiences around proactive alerting, which surface risks immediately after interaction turns to facilitate in-the-moment rather than post-hoc auditing. |
|  | **Source attribution** | Experiences around source attribution, which link inferred attributes to specific conversational origins (UUIDs) to verify model's reasoning. |
|  | **Risk discovery** | Experiences around risk discovery, which let users become aware of how seemingly benign inputs are synthesized into sensitive inferences. |
| **Interaction** | **Human-in-the-loop correction** | Users' role in fixing errors or updating outdated information to refine the model. |
|  | **High workload** | Preference for automated alert over the high workload of manual memory clustering or dragging. |
| **System inaccuracies** | **False negatives** | Instances where sensitive information was present in the dialogue but was not flagged by the inference engine. |
|  | **False positives** | Non-sensitive context being incorrectly categorized as a privacy risk, requiring manual dismissal by the user. |

