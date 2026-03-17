# ToolMind: A Large-Scale, High-Quality Tool-Use Dataset with Multi-Agent Simulation and Turn-Level Filtering

This repository provides a data subset for ToolMind, a large-scale dataset designed to enhance the reasoning and tool-use capabilities of LLM agents.

To comply with the double-blind review policy, we provide this anonymous repository containing a representative sample of our trajectories. The full dataset (368,611 instances) will be officially released on Hugging Face upon acceptance.

## 📂 Repository
sample.jsonl: 1,000 multi-turn trajectories showcasing under-specified user intents and proactive clarification processes.

Full dataset: https://modelscope.cn/datasets/Anoymous/ToolMind

## 📊 Data Format (Schema)
Each instance in **ToolMind** includes a complete trajectory with multi-turn conversations, tool definitions, and explicit reasoning steps. 

```json
{
  "conversations": [
    {
      "role": "user",
      "content": "What's the weather in Beijing?"
    },
    {
      "role": "assistant",
      "content": "<think>\nThe user is asking for the weather in Beijing. However, the 'Check_weather' tool requires 'date' and 'degree' (unit) parameters which are missing. I should proactively ask the user for these details to ensure an accurate tool call.\n</think>\nI'd be happy to check the weather for you! Could you please specify the date and your preferred temperature unit (Celsius or Fahrenheit)?"
    },
    {
      "role": "user",
      "content": "January 1, 2026, in Celsius."
    },
    {
      "role": "assistant",
      "content": "<think>\nNow I have all required parameters: city='Beijing', date='January 1, 2026', and degree='Celsius'. I will invoke the Check_weather tool.\n</think>",
      "tool_calls": [
        {
          "function": {
            "name": "Check_weather",
            "arguments": {
              "city": "Beijing",
              "date": "January 1, 2026",
              "degree": "Celsius"
            }
          }
        }
      ]
    }
  ],
  "tools": [
    {
      "type": "function",
      "function": {
        "name": "Check_weather",
        "description": "Get weather information for a specific city and date",
        "parameters": { ... }
      }
    }
  ]
}
```

## 🛡️ Anonymity & Reproducibility
This subset is provided solely for the purpose of the ACL 2026 review process. All personal identifiers and permanent repository links have been removed.
