I build systems whose failures can be replayed: deterministic simulation testing, consensus, storage engines. London.

- **[moirae](https://github.com/pchrysostomou/moirae)** — deterministic simulation testing for distributed systems, in TypeScript. Every failure is a seed that replays byte for byte; [open one in the studio](https://pchrysostomou.github.io/moirae/?trace=clean-partition.jsonl).
- **[ananke](https://github.com/pchrysostomou/ananke)** — a distributed SQL database in Rust that runs under its own simulator. Its Raft layer holds its invariants across 10,000 seeded fault runs.
- **[openraft #2099](https://github.com/databendlabs/openraft/pull/2099)** — a seeded, simulated runtime for openraft. It reproduces a real CI flake on 24 of 300 seeds, and seed 9 replays byte for byte. Open PR.
- **[mise #13035](https://github.com/jdx/mise/discussions/13035#discussioncomment-18400407)** — traced a false monorepo warning to its cause; the maintainer merged the fix the same day.

[prodromosch@hotmail.co.uk](mailto:prodromosch@hotmail.co.uk)
