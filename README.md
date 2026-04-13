# AI Agent Dashboard

A simple Streamlit dashboard for interacting with an AI agent powered by DeepSeek API.

## System Overview

- **Problem**: Provide a visual interface for users to enter questions, adjust generation parameters, and receive AI-generated answers.
- **Workflow**: The user configures parameters (temperature, max length) in the sidebar, enters a question in the main area, and clicks Submit. The frontend calls the backend agent module, which communicates with the DeepSeek API to generate a response, then displays it in the UI.
- **Key Components**:
  - `app.py`: Streamlit frontend handling UI rendering and user interaction.
  - `agent.py`: Backend module encapsulating DeepSeek API call logic.

## Features Implemented

- Responsive layout with sidebar configuration and main content area.
- Input validation (length checks) and error handling.
- Loading indicator (spinner) during request processing.
- DeepSeek API integration (supports `deepseek-chat` and `deepseek-reasoner` models).
- Clear success/error feedback messages.

## Design Decisions

- Used `st.set_page_config` to set page title and wide layout.
- Sidebar groups all configuration options, keeping the main area focused on input/output.
- `st.spinner` provides immediate user feedback during processing.
- Agent module is decoupled from the UI for easier testing and future changes.
- Sensitive information (API key) managed via `.env` file following security best practices.
- DeepSeek API is compatible with OpenAI SDK, requiring only a `base_url` change.

## How to Run

1. Clone the repository and navigate to the project directory.
2. Create and activate a Python virtual environment (recommended).
3. Install dependencies:
   ```bash
   pip install -r requirements.txt
