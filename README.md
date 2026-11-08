# go-embedded-r.github.io

The go-embedded-r landing page (Hugo), served at <https://go-embedded-r.github.io/>.
The documentation is at <https://go-embedded-r.github.io/docs/> (repository
[go-embedded-r/docs](https://github.com/go-embedded-r/docs)).

The organization is **in development**. `go-embedded-r/r` v0.11.0 (2026-11-08)
completes milestones M0 (the oracle harness, against GNU R 4.6.2) and M1 (the
parser and deparse, package `syntax`, identical to R's tree, tokens and deparse
output on 842 of 842 files of R's base packages) and M2 (the evaluator, 175 of 210
primitives and 110 base closures; regex on go-embedded-r/tre, a port of TRE); M3 (base R)
is in progress (26.4 % of base's exports agree with R) and M4 to M8 are planned, and the page says so. It
gives what exists, the milestones, the parity table of the parser and the
clean-room rule (R is an oracle, never a source; BSD-3-Clause). Its statements
come from the README of go-embedded-r/r on main and its `docs/m2-design.md`, and from the plan it links,
`bib/r.md` in [go-scikit/roadmap](https://github.com/go-scikit/roadmap). There is
no playground yet, so there is no playground button.

The layout is the go-* family template: `layouts/index.html` and the shared
design (stylesheet, theme toggle, fork ribbon, icons), imported as the Hugo module
`github.com/go-fleettools/landingkit` pinned in `go.mod`. `[params.brand]`
in `hugo.toml` is read from the logo's gradient:

```sh
go run github.com/go-fleettools/landingkit/cmd/landingkit brand static/img/logo.svg
hugo server
```

| Workflow | What |
| --- | --- |
| `hugo.yml` | builds on pull requests; builds and deploys to Pages on `main` |
| `ci.yml` | the site builds and names every repository; `go mod tidy` keeps the landingkit requirement |
| `links.yml` | every link and image of the built site resolves |

BSD-3-Clause.
