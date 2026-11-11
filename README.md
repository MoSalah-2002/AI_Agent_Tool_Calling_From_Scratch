# AI Agent with Tool Calling – From Scratch

An educational AI coding agent built using **Qwen3-4B** and Hugging Face Transformers.

The project demonstrates how to build an AI agent capable of understanding user instructions, deciding when to use external tools, executing tool calls, and continuing through a multi-step reasoning and execution loop.

## Features

- Custom tool-calling implementation.
- Multi-step agent execution loop.
- File reading and directory inspection.
- File creation and editing with user approval.
- Shell command execution with user approval.
- Integration with Qwen3-4B using Hugging Face Transformers.

## Available Tools

| Tool | Description |
|---|---|
| `read_file_content` | Read file contents. |
| `list_directory` | List files and directories. |
| `edit_file` | Create or modify files after approval. |
| `run_command` | Execute shell commands after approval. |

## Architecture

1. Receive a user task.
2. Send the task to the language model.
3. Parse the model's tool calls.
4. Execute the requested tool.
5. Return the tool result to the model.
6. Continue until the task is completed.

## Technologies

- Python
- PyTorch
- Hugging Face Transformers
- Qwen3-4B
- Google Colab

## Installation

```bash
pip install -r requirements.txt
```

Open the notebook in Google Colab or a compatible Jupyter environment.

## Model

The project uses the pretrained `Qwen/Qwen3-4B` model for inference and tool calling. The model is not fine-tuned as part of this project.

## Limitations and Safety

This is an educational prototype, not a production-ready autonomous agent.

- Shell commands can execute powerful operations.
- User approval is a basic confirmation mechanism, not a security sandbox.
- File access should be restricted before using the agent with sensitive data.

See `docs/SAFETY.md` for safety considerations.