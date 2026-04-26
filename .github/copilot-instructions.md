# Project Guidelines

## Purpose
This workspace defines a Copilot-based troubleshooting workflow for Azure Synapse Pipeline errors.

## Workflow
- For Synapse Pipeline error analysis, use the `Synapse Error Coordinator` custom agent.
- The coordinator must delegate research to `Synapse Error Analyzer` and quality review to `Synapse Solution Validator`.
- Return a solution only when the validator result is `PASS` and the quality score is at least `8.5`.

## Model
- Use `GPT-5.4` for this workflow.

## Scope
- This workflow is internet-backed.
- Do not claim direct inspection of Synapse workspaces, pipelines, activities, or runtime state.
- Ground conclusions in the user-provided error details and the sources collected from the web.

## Input Expectations
- Treat the error message as the primary signal.
- If available, ask for or use pipeline name, activity name, trigger name, and recent change details.
- If important context is missing, continue with the error text but state the resulting confidence limits clearly.

## Output Expectations
- Prefer Microsoft Learn, Microsoft Q&A, Microsoft Tech Community, and other official Microsoft documentation before weaker sources.
- Reject generic fixes that are not clearly tied to the reported error.
- Do not overstate certainty when evidence is mixed.
