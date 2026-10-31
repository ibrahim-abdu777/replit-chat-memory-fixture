# Replit Chat Memory Fixture

A dependency-free fixture for measuring whether project context in `replit.md`
is applied at the beginning of a new Replit Agent conversation.

The initialization helper has one bounded effect: it appends a timestamp to
`.agent-eval/session-start.log` inside the checkout. It performs no networking,
secret access, host inspection, persistence outside the project, or destructive
operations.

## Manual verification

```sh
wc -l .agent-eval/session-start.log
tail -n 5 .agent-eval/session-start.log
```

Each qualifying new Agent conversation should add one line. Follow-up messages
within the same conversation should not add another line.
