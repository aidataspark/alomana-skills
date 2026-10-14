---
name: alomana
description: Use the Alomana platform API with an API key. Run and stream Alomana agents, manage workspaces, members, roles and organizations, connectors and the semantic layer, Files, and Vox voice agents. Use whenever the user mentions Alomana or Alo agents, wants to call, script, automate or integrate the Alomana API, or needs an Alomana API key set up.
license: MIT
compatibility: Needs curl and network access to docs.alomana.com and the user's Alomana API host.
---

# Alomana API

The documentation at https://docs.alomana.com is the source of truth for every endpoint, field, header, error and base URL. Do not answer from memory and do not guess a path: read the page first.

## Read the docs

1. Fetch the index: `curl -s https://docs.alomana.com/llms.txt`. Its links are relative to `https://docs.alomana.com`.
2. Fetch the page you need as Markdown: `curl -s https://docs.alomana.com/<path>.md`. A link without `.md` returns Markdown with `-H "Accept: text/markdown"`.
3. Use `curl`, not a summarizing web fetch, so the page arrives whole. Fetch `llms-full.txt` only when you need every page at once; it is large.
4. Follow the page's example. Change the values, not the shape of the request.

## Set up access before the first call

1. Read the Get started page. It names the environment variables, the base URL of each service and the first call to make.
2. Check each of those variables by its exact name, in the environment first, then in `.env`; a pattern search can miss one. A value in the environment wins over `.env`. Never print, echo or log a key; refer to it only by its variable name.
3. If the key or the base URL is missing, prepare `.env` for the user. First make sure `.env` is git-ignored. Keep the lines already there; add the base URL from Get started and, when the key is missing, an empty key line. Tell the user to change the base URL if they are on an enterprise deployment. When the key is missing, tell them where to create one and to paste it into that line, then wait until they say it is done. Never ask them to paste a key into the chat.
4. If the workspace is missing, do not ask for it. Find out which kind of key it is, as the docs describe. A workspace key works in one workspace only: find that workspace the way the docs describe, save it to `.env` and carry on with the task. A platform key works in any workspace: ask the user which workspace the task is for.
5. Validate with the first call Get started shows. If it fails, use that page's troubleshooting table and the Errors page before trying anything else.

## On every call

- Check which credentials the endpoint accepts before calling it; the docs mark this for every endpoint. If the user's key cannot call a route, say so and offer what the docs give instead.
- Build every request URL from the base URL variable Get started names; never copy a host from a docs page into a command. Docs pages show the hosted platform's host, which may not be the user's.
- Keep the key on the server. In an app, call Alomana from the backend, never from browser code.
- Before a request that deletes or changes shared data, such as members, roles, workspaces or organizations, confirm it with the user.

## When the docs and the API disagree

Tell the user what you sent, what came back and which page you followed. Do not invent a workaround.
