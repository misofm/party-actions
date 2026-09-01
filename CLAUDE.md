# Working on Party Actions

## Sui Development Skills

Install community-maintained skills for Sui development:

```sh
npx skills https://github.com/MystenLabs/skills
```

## Official Resources

When unsure about Move patterns or Sui APIs, consult these sources and the Sui
documentation MCP server at `https://sui.mcp.kapa.ai`. Do not guess or
extrapolate from other blockchains.

- Move Book: https://move-book.com (use https://move-book.com/llms.txt)
- Sui Docs: https://docs.sui.io (use https://docs.sui.io/llms.txt)
- Sui Move examples: https://github.com/MystenLabs/sui/tree/main/examples/move

## Project Structure

- `party_wallet/` — raw-`PartyAdminCap`, custody-agnostic wallet actions.

## Project Rules

- An action is a small `public fun` that accepts the raw capability and returns
  assets; do not transfer to a recipient or add `entry` wrappers.
- Keep Vaults, witnesses, installation, and plugin authorization out of
  production sources. Vault may appear only as a test dependency.
- Use Move 2024 syntax and macros, numeric error codes, `Event` suffixes, and
  full commit SHAs for git dependencies.
- Treat published public signatures and structs as immutable v1 API.
- Run `sui move build`, `sui move test`, and `sui move test --coverage`
  warning-free before handoff.

