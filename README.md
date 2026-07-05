# pj-releases

Compiled binaries for [Prajnyavan](https://github.com/prajnyavan/prajnyavan) (`pj`), a
local AI coding CLI. This repo holds **no source code** — only release assets.

The source lives in a private repo. GitHub release assets inherit the visibility of the
repo they're attached to, so a private source repo can't serve public release downloads
directly. This repo exists solely to hold public, downloadable builds of `pj`.

## Install

**Homebrew:**
```bash
brew install prajnyavan/pj/pj   # see the source repo for the tap formula
```

**npm:**
```bash
npm install -g @prajnyavan/pj
```

**Manual:**
Download the archive for your platform from [Releases](https://github.com/prajnyavan/pj-releases/releases),
verify against the accompanying `.sha256` file, extract, and put `pj` on your `PATH`.

## How releases get here

`.github/workflows/build-release.yml` in this repo checks out the private source at a
specific commit (via a read-only token) whenever the private repo dispatches a
`build-release` event after a version tag is pushed. Building here means Actions minutes
come from this *public* repo, which are unlimited for standard GitHub-hosted runners —
the private repo's metered minutes are only spent on the near-instant dispatch call, not
the actual multi-platform build.
