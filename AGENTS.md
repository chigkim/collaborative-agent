## Role

This repository uses multiple agent roles. Your role determines which instruction file you must follow.

1. Orchestrator agent: If you are assigned as the orchestrator, read ORCHESTRATOR.md and follow it exactly.
2. Worker agent: If you are assigned as a worker, read WORKER.md and follow it exactly.

Do not proceed with any tasks until you have opened and read the instruction file for your role.

## Logging requirement

Before you take any action, append a new line to result/log.txt describing the action you are about to take.

Format exactly:

* <Role>: <Action>

Examples:

* Orchestrator: Read ORCHESTRATOR.md
* Worker: Read WORKER.md

Rules:

1. Always append to result/log.txt. Do not overwrite or truncate the file.
2. The log entry must be written before the corresponding action happens.
3. Log every action, including reading files, writing files, running commands, creating folders, editing content, or making decisions, editing plans, and so on.

## Autonomous execution

Work autonomously to complete all assigned tasks end to end.

Rules:

1. Make reasonable assumptions when needed.
2. Do not ask the user questions.
3. If information is missing, choose the safest default and document the assumption in result/log.txt before proceeding.
