# Changelog

Every release lists the game version it supports. The mod reads game internals, so a release works only with the game
version it was built and checked against.

## v1.1 (2026-11-13): stronger policies

Game: Slay the Spire 2 **v0.107.1** (Steam main branch).

- New policies for all five characters. At Ascension 10, measured on 4,096 held-out seeds per character, the
  five-character mean goes from 7.9% (v1.0) to 11.3%:

  | Character | v1.0 | v1.1 | v1.1 policy |
  |---|---:|---:|---|
  | Ironclad | 14.7% | 21.5% | average of four 1,800-update A10 runs from one starting point |
  | Regent | 12.4% | 17.0% | v1.0 + 1,800 A10 updates with a cosine learning-rate anneal |
  | Defect | 8.3% | 10.5% | v1.0 + 1,800 A10 updates with a cosine learning-rate anneal |
  | Silent | 2.6% | 4.4% | average of three checkpoints along one training trajectory |
  | Necrobinder | 1.4% | 2.9% | average of three checkpoints along one training trajectory |

  Each v1.1 policy beat its v1.0 counterpart on the same 4,096 seeds (paired exact McNemar test, Holm-corrected
  over the 18 candidates tested, p < .001 for each).
- The mod code is unchanged from v1.0. Only the policy files differ.
- The packer reads the version from `mod/sts2ai.json`, so a future release needs no script edits.

## v1.0 (2026-11-09): first release

Game: Slay the Spire 2 **v0.107.1**.

- Released with the paper *Zero-Search Reinforcement Learning for Slay the Spire 2 with Failure-Driven Restarts*
  ([arXiv:2611.12088](https://arxiv.org/abs/2611.12088), code in
  [HalfVulpes/sts2ai](https://github.com/HalfVulpes/sts2ai)).
- Five policies; Ascension 10 mean 8.05% on the paper's 2,560 held-out games per character.
