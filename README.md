# Cue CLI

Manage events from your terminal. Create events, respond to invitations, and stay updated — all without leaving the command line.

Cue CLI is the command-line client for [Cue](https://getcue.net), the event coordination platform.

## Install

```
brew install vegardlu/cue/cue-cli
```

Requires [Homebrew](https://brew.sh). macOS (Apple Silicon + Intel) and Linux (amd64 + arm64).

## Quick Start

```bash
# Sign in with Google or email
cue auth login

# See your events
cue events list

# Create an event
cue events create

# Respond to an invitation
cue respond 42

# Watch for live updates
cue watch
```

## Commands

```
cue auth login|logout|status     Sign in, sign out, check session
cue events list|show|create      View and create events
cue events edit|cancel|finalize  Manage your events
cue events invite|reopen|link    Invite people, reopen, share links
cue respond <id>                 Accept or decline an invitation
cue notifications                View and manage notifications
cue users me|search              Profile and user search
cue watch                        Stream real-time updates (SSE)
cue completion zsh|fish|bash     Shell completions
```

## Scripting & AI

Every command supports `--json` for machine-readable output. When stdout is piped, JSON is automatic.

```bash
# JSON output
cue events list --json

# Pipe to jq
cue events list --json | jq '.[].title'

# Non-interactive event creation
cue events create --title "Dinner" --time "2026-04-10T18:00:00+02:00" --invite "friend@example.com"

# Non-interactive respond
cue respond 42 --accept --times 1,2
```

Exit codes: `0` success, `1` error, `2` auth required, `3` not found, `4` validation, `5` server error.

## Shell Completions

Installed automatically with Homebrew. To set up manually:

```bash
# zsh
echo 'source <(cue completion zsh)' >> ~/.zshrc

# fish
cue completion fish > ~/.config/fish/completions/cue.fish
```

## Update

```
brew upgrade cue-cli
```

## Links

- [Install guide](https://getcue.net/cli)
- [Cue web app](https://getcue.net)
- [Releases](https://github.com/vegardlu/cue-cli/releases)
