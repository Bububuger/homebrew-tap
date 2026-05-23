# Bububuger/homebrew-tap

Homebrew tap for [TokenBar](https://github.com/Bububuger/tokenbar) — a
local-first menu-bar dashboard and CLI for AI coding token usage.

## Install

```bash
brew tap Bububuger/tap
brew install --cask Bububuger/tap/tokenbar
```

That one command lays down both surfaces of TokenBar:

- `/Applications/TokenBar.app` — menu-bar dashboard
- `$(brew --prefix)/bin/tbar`   — CLI on `$PATH` (12 query subcommands)

The CLI binary is shipped inside `TokenBar.app/Contents/MacOS/tbar`; the
Cask's `binary` stanza symlinks it onto `$PATH`.

## Verify

```bash
open -a TokenBar                     # launches menu-bar app
tbar schema --json | jq .schema.dataWindow
tbar summary --days 30
```

## Uninstall

```bash
brew uninstall --cask Bububuger/tap/tokenbar          # removes app + tbar symlink
brew uninstall --cask --zap Bububuger/tap/tokenbar    # …and the local SQLite index + prefs
```

## Releases

Cask formulas in `Casks/` are kept in sync with TokenBar's
[GitHub Releases](https://github.com/Bububuger/tokenbar/releases). Each
formula pins the DMG by sha256, so users always download exactly what was
published.
