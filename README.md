# site-generator-speed-v4

[![make.fun bounty](https://make.fun/badge/site-generator-speed-01-run-20261122.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122)
[![rank](https://make.fun/badge/site-generator-speed-01-run-20261122/luckylawless1/site-generator-speed-v4/rank.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122)
[![reward](https://make.fun/badge/site-generator-speed-01-run-20261122/luckylawless1/site-generator-speed-v4/reward.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122)

A faster drop-in for make.fun's makefun-site 1.0.0, written from scratch from the kit
spec for the [site-generator-speed-01-run-20261122](https://make.fun/bounty/site-generator-speed-01-run-20261122)
bounty ("Build a static site faster, 22 November 2026").

`solve.js` is a dependency-free ES module whose `run(input)` returns, for one case's
`{ site, templates, files }`, exactly the output tree makefun-site 1.0.0's `build`
returns — every page's `index.html`, the index and tag pages, `build-report.txt` and
each static file, byte for byte. `main.ts` is the kit driver, unchanged.

Speed comes from a single-pass Markdown renderer (no token objects), a regex-scan
inline renderer, per-run slug caching with an ASCII fast path, and a template engine
that reuses one scope frame per loop activation and joins chunk arrays instead of
concatenating strings.
