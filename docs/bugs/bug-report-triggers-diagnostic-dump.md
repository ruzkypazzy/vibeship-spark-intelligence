# Bug: Vague bug report triggers raw internal diagnostic dump

## Summary
When a user reports a bug in plain language, Spark responds with
raw internal diagnostic output instead of helping structure a
human-readable bug report.

## Steps to Reproduce
1. Send: "I found a bug: when I ask a question the bot gives me a wrong answer"
2. Spark responds with raw internal diagnostics including:
   - "provider context capsule event"
   - "gateway_trace=checked"
   - "close_turn_recall:fail"
   - "context path was bypassed, failed before compile"

## Expected Behavior
Spark should respond by helping the user structure a proper bug
report with: what happened, what was expected, steps to reproduce,
and proof. A non-coder cannot act on raw diagnostic output.

## Actual Behavior
Spark dumped internal system diagnostics with no explanation,
no next step, and no human-readable summary of what went wrong
or what the user should do.

## Impact
Non-technical users are blocked. The raw output is confusing
and does not help them file a useful bug report.

## Fix
When a user reports a bug in plain language, Spark should ask
clarifying questions and help structure a reviewer-ready bug
packet instead of exposing raw internal diagnostic state.

## Team
Team name: Ruzkypazzy Team
Discovered via: Spark Compete Bugs & Goblins Hunt — Mission #34
LLM used: Minimax
