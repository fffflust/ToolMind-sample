ToolMind: A Large-Scale, Reasoning-Enhanced Tool-Use Dataset
This repository provides a data subset for ToolMind, a large-scale dataset designed to enhance the reasoning and tool-use capabilities of LLM agents.

To comply with the double-blind review policy, we provide this anonymous repository containing a representative sample of our trajectories. The full dataset (368,611 instances) will be officially released on Hugging Face upon acceptance.

📂 Repository Structure
sample.jsonl: 1,000 multi-turn trajectories showcasing under-specified user intents and proactive clarification processes.

dataset_schema.md: Detailed documentation of the data fields and reasoning trace formats.

📊 Data Preview
Each instance in ToolMind captures the dynamic reasoning process of an agent. Below is a simplified example from sample_1000.jsonl (corresponding to the scenario in Figure 1 of our paper):

🌟 Key Data Attributes
Reasoning-Enhanced: Every turn includes a thought field that explains the model's logic for tool selection or clarification.

Proactive Interaction: Unlike existing datasets, ToolMind explicitly includes "Under-specified" scenarios where the agent must ask for more information rather than failing or hallucinating.

High-Quality Annotations: As shown in Table 1 of our paper, all trajectories include turn-level correctness judgments (verified during our synthesis pipeline).

🛡️ Anonymity & Reproducibility
This subset is provided solely for the purpose of the ACL 2026 review process. All personal identifiers and permanent repository links have been removed.
