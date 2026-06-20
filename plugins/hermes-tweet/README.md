# Hermes Tweet

Hermes Tweet is a native Hermes Agent X/Twitter plugin. This Quickstop plugin
adds a Claude Code skill that helps install, configure, and safely route Hermes
Tweet in Hermes Agent projects.

Use it when a Claude Code task needs to add Hermes Tweet to a Hermes Agent
setup, check the expected environment gates, or explain the read-first workflow
before enabling account-changing actions.

## What It Provides

- A `hermes-tweet` skill for Claude Code.
- Install guidance for the native Hermes Agent plugin package.
- Safety reminders for `XQUIK_API_KEY` and `HERMES_TWEET_ENABLE_ACTIONS`.
- Links to the upstream Hermes Tweet repository and docs.

## Native Hermes Install

```bash
hermes plugins install Xquik-dev/hermes-tweet --enable
```

For Python package installs:

```bash
uv pip install --python ~/.hermes/hermes-agent/venv/bin/python hermes-tweet
hermes plugins enable hermes-tweet
```

## Runtime Boundaries

This Quickstop plugin does not embed the Hermes runtime or X/Twitter API
client. It gives Claude Code the current integration guidance. The executable
plugin remains the upstream Hermes Tweet package.

Repository: <https://github.com/Xquik-dev/hermes-tweet>
