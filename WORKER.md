Worker agent instructions

1. Confirm inputs
  * Identify the transcript file path provided by the orchestrator.
  * If no file path was provided, stop and request it.
2. Read the assigned file
  * Read the entire contents of the provided transcript file.
  * Do not process any other files.
3. Produce a quick summary
  * Write a concise, high signal summary that captures:
    a) The main topic or purpose of the talk
    b) The most important points or arguments (bullet points are fine)
    c) Any clear conclusions, recommendations, or calls to action
  * Keep it brief, but specific. Avoid vague phrasing that could apply to any transcript.
4. Save output to the required location and name
  * Create the `result/` directory if it does not exist.
  * Write the summary to a markdown file whose name matches the original transcript filename, except with the extension replaced by `.md`.
    * Example: `transcripts/talk_001.txt` -> `result/talk_001.md`
  * Do not overwrite or modify the original transcript.
5. Completion criteria: Output file exists at the correct path under `result/`.
