# Bug: /start response overwhelms new users with 25+ commands

## Summary
The /start command dumps a wall of 25+ commands across 4 screens
with no guidance on where to begin. New users have no clear
first action.

## Steps to Reproduce
1. Open Spark Telegram bot as a new user
2. Send /start
3. Receive a 4-screen response listing 25+ commands

## Expected Behavior
/start should give a 2-3 line welcome and ONE suggested
first action such as "Try saying hello or run /spark to
check system status."

## Actual Behavior
25+ commands dumped across 4 screens with no priority,
no suggested starting point, and no onboarding guidance.

## Impact
New users are immediately overwhelmed and don't know
where to start. High drop-off risk at first interaction.

## Fix
Limit /start to a short welcome + one clear next step.
Move the full command list to a /help command instead.

## Team
Team name: Ruzkypazzy Team
Discovered via: Spark Compete Bugs & Goblins Hunt — Mission #15
LLM used: Minimax
