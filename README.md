# Prodromos Chrysostomou

I build systems whose failures can be replayed: deterministic simulation testing, consensus, storage engines. London.

| Project | What it does | Measured result | Where the evidence is |
|---|---|---|---|
| [moirae](https://github.com/pchrysostomou/moirae) | Deterministic simulation testing for distributed systems, in TypeScript: Raft, Paxos and ABD under injected faults, with a trace viewer | The demo is seed 19 and replays byte for byte; two runs of one seed are compared byte-identical and against a committed golden hash. 229 tests in 49 files, on Node 20, 22 and 24 | [a trace open in the live studio](https://pchrysostomou.github.io/moirae/?trace=clean-partition.jsonl) · [`determinism-faults.test.ts`](https://github.com/pchrysostomou/moirae/blob/main/packages/core/test/determinism-faults.test.ts) · [CI run](https://github.com/pchrysostomou/moirae/actions/runs/35102087164) |
| [ananke](https://github.com/pchrysostomou/ananke) | A distributed SQL database in Rust in which every source of non-determinism goes through one trait, so the same code runs under a simulator. The storage engine and Raft are done; sharding has begun; there is no SQL yet | Raft's exit sweep green at 10 000 seeds. 13 bugs the simulator found are written up, 12 of them with the seed that found them | [nightly run on `cd411b4`](https://github.com/pchrysostomou/ananke/actions/runs/34839613587) · [the README's bug list](https://github.com/pchrysostomou/ananke#bugs-the-simulator-has-found) |
| [openraft #2099](https://github.com/databendlabs/openraft/pull/2099) | A simulated, seeded `AsyncRuntime` for openraft, so its integration tests run on virtual time and a failure can be replayed | With one upstream fix reverted, 24 of 300 seeds reproduce the CI flake it fixed (#2059); seed 9 fails in 5 of 5 fresh processes with a byte-identical 3,467-line log | the pull request's description, and its `tests-sim` CI job, which runs one seed twice and diffs the logs. **Open, not merged** |
| [mise #13035](https://github.com/jdx/mise/discussions/13035#discussioncomment-18400407) | Diagnosed why layered `monorepo_root` config overlays raised a false warning | The maintainer confirmed it as a bug and merged the fix, [#13084](https://github.com/jdx/mise/pull/13084), the same day | the discussion thread |

moirae and ananke are solo projects, and each README says what the project does not do. Every number above is copied from the linked run, file or thread.

[prodromosch@hotmail.co.uk](mailto:prodromosch@hotmail.co.uk)
