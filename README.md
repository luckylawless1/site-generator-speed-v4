# site-generator-speed-v4

[![make.fun bounty](https://img.shields.io/badge/make.fun-bounty-7c3aed)](https://make.fun/bounty/site-generator-speed-01-run-20261122)
[![site-generator-speed-01-run-20261122](https://img.shields.io/badge/site--generator--speed--01-run--20261122-2563eb)](https://make.fun/bounty/site-generator-speed-01-run-20261122)
[![make.fun entry](https://img.shields.io/badge/make.fun-entry-f59e0b)](https://make.fun/bounty/site-generator-speed-01-run-20261122)

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
