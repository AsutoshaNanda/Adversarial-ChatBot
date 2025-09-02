# Adversarial-ChatBot

## Overview
The **Adversarial-ChatBot** repository contains a Jupyter notebook that demonstrates an adversarial conversation between two large‑language‑model (LLM) agents:

* **GPT‑style model** – configured to be argumentative, sarcastic and deliberately challenging.  
* **Claude‑style model** – configured to be polite, conciliatory and seeking common ground.

The notebook showcases how these contrasting personas interact, how prompts can shape model behavior, and how streaming APIs can be used to display a live back‑and‑forth dialogue.

## Repository Structure
```
.
├── Project 01 LLMs.ipynb   # Main notebook with all code, prompts, and sample outputs
└── README.md              # This documentation file
```

## Key Concepts Demonstrated

| Section | What It Shows | Important Details |
|---------|---------------|-------------------|
| **Environment Setup** | Imports, loading API keys from a `.env` file, and initializing OpenAI, Anthropic, and Google Gemini clients. | Uses `python-dotenv` for secret management. |
| **Prompt Design** | System and user prompts that ask for data‑science jokes. | Highlights the impact of system prompts on model tone. |
| **Single‑Model Queries** | Simple calls to OpenAI, Anthropic, and Gemini to generate jokes. | Demonstrates temperature, `max_tokens`, and model selection. |
| **Streaming Responses** | Real‑time display of token‑by‑token generation using `display` and `update_display`. | Useful for interactive notebooks or UI prototypes. |
| **Adversarial Dialogue** | Two personas (`gpt_system_prompt` and `claude_system_prompt`) are defined, then a loop alternates calls to each model, feeding the other's output back as the next input. | Shows how to build a persistent conversation, handle role‑based messages, and compare responses. |
| **Utility Functions** | `call_gpt()` and `call_claude()` encapsulate the request logic, making the main loop concise. | Includes examples of both `chat.completions.create` (OpenAI) and `messages.create` (Anthropic). |
| **Sample Output** | A full transcript of a 5‑turn exchange is included, illustrating the evolving tone and content. | Provides a concrete reference for expected behavior. |

## How to Run the Notebook

1. **Clone the repo**  
   ```bash
   git clone https://github.com/AsutoshaNanda/Adversarial-ChatBot.git
   cd Adversarial-ChatBot
   ```

2. **Install dependencies** (preferably in a virtual environment)  
   ```bash
   pip install -r requirements.txt   # (Create this file if you need a list of packages)
   # Required packages include:
   # openai, anthropic, google-generativeai, python-dotenv, beautifulsoup4, ipython
   ```

3. **Create a `.env` file** with your API keys:  
   ```
   OPENAI_API_KEY=sk-...
   ANTHROPIC_API_KEY=sk-ant-...
   GOOGLE_API_KEY=AIzaSy...
   ```

4. **Open the notebook** in JupyterLab / VS Code and run cells sequentially.  
   The notebook will automatically print jokes, streaming outputs, and the full adversarial conversation.

## Extending the Project

- **Add new personas**: Define additional system prompts and experiment with different tones (e.g., a neutral moderator).  
- **Swap models**: Replace `gpt-4o-mini` or `claude-3-7-sonnet-latest` with newer or cheaper models to see how behavior changes.  
- **Persist conversation**: Save each turn to a JSON or CSV file for later analysis.  
- **Visualization**: Use `matplotlib` or `plotly` to chart sentiment or token usage across turns.

## License
This repository is provided for educational purposes. Feel free to fork, modify, and share as long as you comply with the terms of the respective LLM providers' APIs.

---

*Happy coding!*
