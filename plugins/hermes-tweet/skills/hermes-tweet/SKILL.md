---
name: hermes-tweet
description: Install, configure, or document Hermes Tweet, the native Hermes Agent X/Twitter plugin. Use when a Claude Code task needs Hermes Agent social automation guidance, X/Twitter read workflows, or approval-gated action setup.
argument-hint: "[install|configure|audit|docs]"
allowed-tools: Read, Grep, Bash
---

# Hermes Tweet

Hermes Tweet is a native Hermes Agent plugin for X/Twitter automation through
Xquik. It exposes a read-first workflow for tweet search, account reads,
replies, users, followers, monitors, extraction jobs, media, trends, and
approval-gated account actions.

## Install

Use the native Hermes plugin installer when possible:

```bash
hermes plugins install Xquik-dev/hermes-tweet --enable
```

If the Hermes runtime uses a Python virtual environment, install the package
there:

```bash
uv pip install --python ~/.hermes/hermes-agent/venv/bin/python hermes-tweet
hermes plugins enable hermes-tweet
```

## Configure

Set the API key only in the Hermes runtime environment or `~/.hermes/.env`:

```bash
export XQUIK_API_KEY="xq_..."
```

Keep account-changing routes disabled unless the session explicitly needs them:

```bash
export HERMES_TWEET_ENABLE_ACTIONS="false"
```

Only set `HERMES_TWEET_ENABLE_ACTIONS=true` for reviewed sessions that need
posting, DMs, follows, webhooks, monitors, media changes, or other private
actions.

## Tool Routing

- `tweet_explore`: search the bundled endpoint catalog. No network call.
- `tweet_read`: call catalog-listed read endpoints. Requires `XQUIK_API_KEY`.
- `tweet_action`: call write-like or private endpoints. Requires
  `XQUIK_API_KEY` and `HERMES_TWEET_ENABLE_ACTIONS=true`.

Always use `tweet_explore` before a concrete `tweet_read` or `tweet_action`
call. Do not paste API keys into prompts, issue bodies, PR comments, or tool
arguments.

## References

- Repository: <https://github.com/Xquik-dev/hermes-tweet>
- PyPI: <https://pypi.org/project/hermes-tweet/>
- Guide: <https://docs.xquik.com/guides/hermes-tweet>
