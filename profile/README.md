## [wafer.space](https://wafer.space) bench - open GF180MCU designs, kept as a benchmark suite

This organization collects a copy of every open design that has been taped out on the
[GF180MCU open source PDK](https://gf180mcu-pdk.readthedocs.io/), each pinned to the exact
commit that was manufactured.

**Start at the index: <https://wafer-space-bench.github.io>** - a searchable table of every
repository here, its upstream, its tapeouts and its state. The collection is still being
filled; the index also lists the designs that are planned but not copied yet.

### Why this exists

[wafer.space](https://wafer.space) is evaluating alternative GF180 process configurations.
The only honest way to know what a process change does to density, timing and
DRC/LVS/simulation results is to re-run real designs against it, so the benchmark suite is
*everything that has actually been built*:

| Source | Runs |
|---|---|
| [wafer.space](https://wafer.space) | [`ws-run1`](https://wafer.space/ws-run1/), [`ws-run2`](https://wafer.space/ws-run2/) |
| Google / Efabless Open MPW | `gf180mcu-mpw0`, `gf180mcu-mpw18h1` |
| [Tiny Tapeout](https://tinytapeout.com) | [`ttgf0p2`](https://tinytapeout.com/chips/ttgf0p2/), [`ttgf0p3`](https://tinytapeout.com/chips/ttgf0p3/), [`ttgf26a`](https://tinytapeout.com/chips/ttgf26a/), [`ttgf26b`](https://tinytapeout.com/chips/ttgf26b/), [`ttgf26c`](https://app.tinytapeout.com/shuttles/ttgf26c), [`ttgf26d`](https://app.tinytapeout.com/shuttles/ttgf26d) |

Benchmarking needs three things the original repositories cannot promise, which is why the
designs are copied here rather than just linked:

- **The taped-out commit, findable.** Upstream branches move on after a tapeout. Here every
  manufactured commit has a frozen tag and branch named `<org>/<run>/<slot>`, for example
  `wafer.space/ws-run1/GD03`.
- **Survival.** Designer repositories get renamed, rewritten and deleted. A copy here stays,
  and designs whose upstream is already gone are to be restored from the public shuttle
  archives.
- **One layout for hundreds of repos.** Every repository has the same branches, so tools can
  walk the whole suite without per-design special cases.

### What is in each repository

| Branch | Meaning |
|---|---|
| `about` | Default branch. A generated `README.md` and `bench.yaml`: where the design came from, its licence, and every tapeout of it. |
| `upstream/<branch>` | Exact mirror of the upstream repository's branches, synced daily. |
| `tapeout/<org>/<run>/<slot>` | The commit taped out in that slot. Frozen; identical to the tag of the same name. |
| `dev/repro/<org>/<run>/<slot>` | Reproducing the original result with the originally pinned tools and PDK. |
| `dev/upgrade/<org>/<run>/<slot>` | The same design moved to the latest development LibreLane and gf180mcu PDK. |
| `dev/process/<config>/<org>/<run>/<slot>` | The design adapted to an alternative GF180 process configuration. |

The first three exist in every repository today; the `dev/*` branches are where the
benchmark work lands as it is done.

Repositories are named `<owner>--<repo>` after their upstream. Each carries
topics for its source and runs, so GitHub can list
[all the wafer.space designs](https://github.com/search?q=org%3Awafer-space-bench+topic%3Awafer-space&type=repositories),
[all the Google designs](https://github.com/search?q=org%3Awafer-space-bench+topic%3Agoogle&type=repositories) or
[all the Tiny Tapeout designs](https://github.com/search?q=org%3Awafer-space-bench+topic%3Atinytapeout&type=repositories).

### These are copies, not the projects

The designs belong to their authors, under the licence each author chose; the `about` branch
of every repository links to the original. To use, discuss or contribute to a design, go
upstream. Issues and pull requests are turned off here.

- 🧰 Tooling, catalog and results: [wafer-space/wafer.space-bench](https://github.com/wafer-space/wafer.space-bench) -
  report a wrong commit, a missing design or a design you want removed there.
- 🌐 [wafer.space](https://wafer.space) · 📚 [Documentation](https://docs.wafer.space) · 💬 [Discord](https://wafer.space/discord) · 📧 <info@wafer.space>
