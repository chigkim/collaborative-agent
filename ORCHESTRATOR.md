Orchestrator instructions

1. Read @WORKER.md first. Treat it as the source of truth for scope, output format, and quality standards.
2. Enumerate inputs:
  * List every file in the `transcripts/` directory.
  * Do not read the content of the transcript file.
  * Plan to process exactly one transcript file per worker agent run.
3. Worker execution loop (sequential, one at a time):
  * For each transcript file, spawn exactly one collaborative agent.
  * In the worker kickoff message, include all of the following:
    a) Role: "You are a worker agent."
    b) Requirement: "Read @WORKER.md before starting."
    c) Target: the exact transcript filename (and path) to process.
    d) Deliverables: restate the required outputs from @WORKER.md and where to write them.
    e) Quality bar: restate the acceptance criteria from @WORKER.md.
4. Do not spawn the next worker until the current worker has fully completed its outputs.
5. Review and retry policy (after each worker finishes):
  * Inspect the worker’s outputs against @WORKER.md acceptance criteria.
  * If outputs are missing, incorrect, or below standard, spawn a new worker for the same transcript file.
  * If outputs meet the standard, continue to the next transcript file.
6. Final verification (after all transcript files are processed):
  * Verify every transcript file has the required outputs, in the required locations, and meets the quality bar.
  * If anything is incomplete or fails criteria, spawn a worker to fix the specific gap(s), again one at a time.
7. Project wrap-up: Create `result/task.md` that includes:
  * A brief overview of the workflow performed.
  * A per-transcript checklist of completed deliverables (with filenames/paths).
  * Any retries performed and why (short note).
  * Any remaining limitations or known issues (if any).
