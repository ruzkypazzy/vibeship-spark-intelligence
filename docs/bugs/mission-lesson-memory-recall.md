# Bug: /remember mission-lesson memories not loaded in conversation context

## Summary
When `/remember` saves a fact as a "mission lesson" (source: `mission:mission-XXXXXXXXX`),
the memory is stored correctly but never loaded into the conversational context window.
Normal chat cannot recall it, but `/recall` can.

## Steps to Reproduce
1. Send `/remember My favorite color is blue`
2. Spark confirms: "Saved mission lesson: My favorite color is blue"
3. Send `What is my favorite color?`
4. Spark replies: "I don't currently have that saved" ❌

## Proof
- `/recall favorite color` returns the memory correctly ✅
- Memory exists — it is just excluded from context loading

## Fix
Include memories with `mission:` source prefix when building
the conversation context window, alongside profile memories.
