# StartupGPT

A Streamlit application that generates and chats about comprehensive startup reports using Groq models via LangChain.

## Features

- Streamlit UI for report viewing and interactive Q&A
- Groq LLM integration (`mixtral-8x7b-32768` by default)
- Conversation memory for multi-turn chat
- Local storage of generated reports (`storage/data.json`)

## Requirements

- Python 3.10+
- Packages: `streamlit`, `python-dotenv`, `langchain`, `langchain-community`, `langchain-groq`, `groq`, `pyyaml`

## Setup

1. Create a `.env` file in the project root with your Groq API key:

	```
	GROQ_API_KEY=grq_xxx_actual_key_here
	```

	You can also set it in the terminal:

	```zsh
	export GROQ_API_KEY=grq_xxx_actual_key_here
	```

2. (Optional) Install dependencies if needed:

	```zsh
	pip install streamlit python-dotenv langchain langchain-community langchain-groq groq pyyaml
	```

## Run

```zsh
cd "/Users/dhruvvadhiya/Desktop/StartupGPT-master 2"
streamlit run app.py
```

Access the app at `http://localhost:8501`.

## Configuration

- App reads `GROQ_API_KEY` from environment or Streamlit secrets.
- Default model: `mixtral-8x7b-32768` (configured in `app.py`).
- Reports are loaded from `storage/data.json` using the `idea_id` you provide.

## Project Structure

```
app.py                       # Streamlit app (UI + chat)
main.py                      # Example workflow script using agents
agents/                      # Domain agents (legal, economics, business structure, generalized)
config/config.yaml           # App/agents configuration
storage/                     # Data storage utilities and JSON store
workflows/startupgpt_workflow.yaml  # Workflow definition
```

## Notes

- If you see a Groq 401 error, confirm your `GROQ_API_KEY` is valid and has not expired/been rotated.
- Deprecation warnings from LangChain are harmless but can be addressed by migrating to the recommended APIs.

## License

Proprietary. All rights reserved.
# DANS-MultiAgent-StartUp-Guidance
