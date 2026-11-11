# Security Notes

This repository is an educational prototype. It is not a production-ready or sandboxed agent.

## Tool execution risks

- The shell tool uses subprocess execution and may run arbitrary commands with the permissions of the current runtime.
- File tools may read or modify paths beyond the intended project directory unless path validation is added.
- Model-generated tool calls are untrusted input. Review every command and file change before approval.
- Human confirmation is not a substitute for operating-system isolation.

## Safe usage

1. Run the notebook in a disposable virtual machine or temporary hosted notebook runtime.
2. Do not mount personal folders, cloud drives, SSH keys, or sensitive files.
3. Inspect every shell command before allowing it to run.
4. Restrict file operations to a dedicated working directory and validate resolved paths.
5. Store API credentials in environment variables or the notebook platform's secret manager.
6. Never commit API keys, tokens, passwords, .env files, or credential-bearing outputs.
7. If a credential was ever committed, revoke/rotate it. Removing it from the latest file does not erase it from Git history.

## Tavily configuration

Set the TAVILY_API_KEY environment variable only if you want to enable web search. The notebook can run without this optional integration; internet-search calls will return an unavailable message when the variable is not configured.

## Scope

This project demonstrates tool-calling orchestration with a pretrained Qwen model. It does not fine-tune the base model and should not be used to execute untrusted tasks on a machine containing important data.
