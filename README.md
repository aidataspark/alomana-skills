# Alomana skills

Agent skills for the [Alomana](https://alomana.com) platform API. The `alomana` skill lets a coding agent use Alomana with an API key: it reads the live documentation at [docs.alomana.com](https://docs.alomana.com), sets up your key and base URL, and calls the right endpoint.

## Install

Claude Code, Cursor, Codex and other agents:

```bash
npx skills add aidataspark/alomana-skills
```

Claude Code plugin:

```
/plugin marketplace add aidataspark/alomana-skills
/plugin install alomana@alomana-skills
```

## Use

Ask your agent for something on Alomana, for example "list the agents in my Alomana workspace" or "write a script that streams an Alomana agent's reply". The first time, it walks you through creating an API key; [Get started](https://docs.alomana.com/docs/get-started) has the same steps.

## What the skill sends where

- It reads the documentation from `https://docs.alomana.com`, without credentials.
- It calls your Alomana API host, the base URL in your environment or `.env` (`https://platform.alomana.com` unless you are on an enterprise deployment), with your API key. The key goes to no other host.
- It never prints the key, and it asks you to paste the key into `.env`, not into the chat. Before writing `.env`, it makes sure the file is git-ignored.

## License

[MIT](LICENSE)
