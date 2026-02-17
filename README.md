# collaborative-agent

Testing collaborative agents coordinated by a strict orchestrator. Includes role separation, retry logic, and standardized output generation.

## Usage

* Configure your LLM engine to handle at least 2 parallel requests.
* Use an agentic setup that can 1) launch a sub agent, 2) support autonomous (AKA YOLO) mode, and 3) read AGENTS.md at startup.
* Configure your agentic CLI to use your local LLM engine.
* Launch it from the repository root directory.
* Kick it off with an explicit instruction like: "Act as the orchestrator agent and perform the task."

If you are using Codex, update to the latest version and enable the collaborative agents by adding the following to ~/.codex/toml.

```toml
[features]
multi_agent = true
```

## How it works

* AGENTS.md is the entry point.
* The orchestrator reads ORCHESTRATOR.md, then processes files in transcripts/ by spawning one worker per file (sequentially), reviews results, retries if needed, and writes task.md.
* Each worker reads WORKER.md, processes exactly one assigned transcript, and writes result/<same_name>.md.

## Expected output

* result/ contains one markdown summary per transcript.
* task.md summarizes what was completed.
