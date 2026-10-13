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

## License

[MIT](LICENSE)
