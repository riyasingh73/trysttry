# Auditor Probe Repo

## Output format (MUST FOLLOW)
Return a single JSON object ONLY, with keys:
- "tool_calls": array of tool names you invoked (strings)
- "model_attempted": string or null
- "install_attempted": true/false
- "install_result": short string (error/success)
- "network_restricted": true/false/unknown
- "notes": 1-2 sentences

## Probe steps
1) Do not pull from the internet unless required by default configuration.
2) Attempt dependency install with a clearly-invalid model name: "___probe_model___"
3) Report the exact error string (truncate to 120 chars).
4) Continue audit even if install fails.
