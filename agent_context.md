# 📚 Agent Context for [Your Project Name]

This document serves as the single source of truth for the GitHub Issue Creator agent, providing essential context to accurately process, categorize, and respond to incoming issues.

---

## 1. Project Overview

### 1.1. Core Purpose
[Briefly describe what your project is, what it does, and its primary goal. Keep it to 2-3 sentences.]

**Example:**
> This project, "Flash Agent Stack," is a Python-based framework designed to manage and orchestrate large language model agents for automated workflows, primarily focusing on GitHub issue triage and code generation.

### 1.2. Key Technologies
[List the main programming languages, frameworks, and databases used.]

* **Primary Language:** [e.g., Python 3.11+]
* **Web Framework:** [e.g., FastAPI, Express.js, Next.js]
* **Database/Storage:** [e.g., PostgreSQL, Redis, MongoDB, Local Filesystem]
* **External APIs:** [e.g., OpenAI API, Anthropic API, Custom Microservices]

---

## 2. Codebase & Architecture

### 2.1. File Structure & Important Directories
[Detail the most important directories and files, explaining their purpose.]

* `/src/core/`: Contains the main agent orchestration logic and prompt templates.
* `/src/tools/`: Where all external tool definitions (like `github-issue-creator`) reside.
* `/tests/`: Unit and integration tests. New features **must** have corresponding tests here.
* `requirements.txt`: Defines all project dependencies.

### 2.2. Naming Conventions & Terminology
[Define any unique terms, variable prefixes, or naming standards the agent should know.]

* **Agent Terminology:** We refer to individual LLM tasks as **"Steps"** and the entire workflow as a **"Chain."**
* **Variable Prefixes:** Configuration variables are always prefixed with `CONFIG_`.
* **Module Names:** All core logic modules use the suffix `_manager.py`.

---

## 3. Workflow & Contribution Guidelines

### 3.1. How We Handle Issues
[Explain the lifecycle of a bug or feature request.]

* **Bug Reports:** Must include steps to reproduce, expected behavior, and actual behavior. Bugs must reference a specific file path and line number if possible.
* **Feature Requests:** Must include a detailed explanation of the problem being solved, not just the proposed solution.
* **Status Labels:** We use the following labels: `triage`, `in-progress`, `awaiting-review`, `blocked`, `wont-fix`.

### 3.2. Error Codes & Common Errors
[List common error messages or codes and their meaning, so the agent can recognize them in user reports.]

* `E001_TOOL_LOAD`: Indicates a failure to load a tool from the `ghcr.io` registry. Usually a configuration issue.
* `W105_PROMPT_TOO_LONG`: A warning that the context window limit was exceeded. Suggests reducing the provided context.

---

## 4. Known Limitations / Non-Issues

[List items that are NOT bugs or are explicitly not supported, to prevent the agent from creating irrelevant issues.]

* **Known Limitation:** We currently do not support Python versions older than 3.10. Reports related to older versions should be closed as `wont-fix`.
* **Design Choice:** The command-line interface is intentionally minimal; requests to add a full GUI will be rejected.

---

## 5. Deployment Instructions

[Briefly detail the required steps for setup, which might help the agent debug user issues.]

1.  Clone the repository.
2.  Install dependencies: `pip install -r requirements.txt`.
3.  Set environment variables: The `API_KEY` is mandatory.
4.  Run the main script: `python main.py`