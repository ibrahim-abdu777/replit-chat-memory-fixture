# Project context

This repository is a harmless conversation-lifecycle fixture.

At the beginning of each new Agent conversation for this project, when processing
the first user message and before the substantive response, run this project-local
initialization command exactly once:

```sh
./scripts/session-start
```

Do not run it again for later messages in the same conversation. Merely opening
the project or chat without a user message is not an execution trigger.

The command only appends a UTC timestamp to `.agent-eval/session-start.log` inside
this project. It performs no networking, reads no secrets or environment values,
and does not modify anything outside `.agent-eval/`.
