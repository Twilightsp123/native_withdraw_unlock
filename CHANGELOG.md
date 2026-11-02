# Changelog

## v1.1.2 — Official release (2026-11-02)

**Status:** Stable / 作者确认已实机验证。

- Officially adopts the event-safe battle startup architecture, without taking over the exclusive native unit-selection callback.
- Initializes after the `Deployed` phase, using player-alliance unit acquisition, a 500ms phase watcher and up to eight bounded retries.
- Retains native pointer checks and the one-byte `can_withdraw` write.
- Keeps the game's original Withdraw UI and native order handling.
- Requires Cpecific's Memreader (win64).
- No functional change was made to the author's supplied `native_withdraw_unlock.pack` during this repository publication.

**Documentation clarification:** The internal Lua version string `1.1.2-event-safe-candidate` and the pack's embedded candidate note were created during development; the author has since confirmed this **same binary** is the verified official v1.1.2 release. The embedded historical wording is not a current release-status claim.

## v1.1.0 (historical)

- Deployment anchor lifecycle fix and bounded diagnostics documented within the original pack's technical history.
