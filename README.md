# Kipsy plugin for Claude

Kipsy is a private library of web pages you chose to save. This plugin connects Claude and Claude Code to that library through Kipsy's remote MCP server so Claude can find saved pages, read their saved copy, list tags and collections, and save a new link when you explicitly ask.

## What this plugin contains

- The plugin manifest (directory and runtime metadata).
- One remote HTTP MCP server, `https://kipsy.io/mcp`.
- A short workflow skill for searching, citing and saving.
- The Kipsy icon.
- The licence (All Rights Reserved).

This plugin bundles no executable code, hooks, scripts, local MCP server, package installers or environment-variable reads. It does not access local files.

## What it sends and fetches

The only network destination is Kipsy's own Worker at `kipsy.io`:

1. OAuth discovery, dynamic client registration, authorization and token requests go to `https://kipsy.io/.well-known/*` and `https://kipsy.io/oauth/*`. The browser signs in with Google on `kipsy.io`; no password is sent to the assistant.
2. MCP tool calls go to `https://kipsy.io/mcp` with a short-lived OAuth access token. Tool arguments are the user's search text, saved-link id, URL, optional title and optional note.
3. Tool results return saved URLs, titles, notes, tags, collections, summaries and saved page text from the connected Kipsy account into the Claude conversation.

Kipsy sends nothing to any third-party destination from this plugin. See `https://kipsy.io/privacy` for data handling and `https://kipsy.io/support` for contact.

## Setup

Install the plugin from the Claude directory, or add the Kipsy connector with the URL `https://kipsy.io/mcp`. Sign in with Google on kipsy.io and approve the Kipsy permissions. Setup guide: https://kipsy.io/connect
