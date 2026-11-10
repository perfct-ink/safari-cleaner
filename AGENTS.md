# AGENTS.md — Safari Cleaner

Safari Cleaner is a macOS SwiftUI app for reviewing and cleaning up Safari bookmarks, including duplicates. The Xcode project is maintained by hand in Xcode (no XcodeGen). [docs/README.md](docs/README.md) still describes the older Safari extension, which has been removed; check the code before trusting it.

## Commands

- `make dev`: Debug build into `build/`, quit any running copy, and open it.
- `make build`: Release build. `make open`: Release build, then open it.
- `make install` / `make uninstall` / `make reinstall`: manage `~/Applications/Safari Cleaner.app`.
- `make close`: quit the app. `make clean`: remove `build/`.
- `python3 make_icon.py`: regenerate the icons in `AppIcon.appiconset`.

There is no test target yet.

## Layout

- `SafariCleaner/SafariCleaner.xcodeproj`: the project; the scheme is `Safari Cleaner` (with a space).
- `SafariCleaner/Safari Cleaner/`: `AppDelegate.swift`, `ViewController.swift`, assets, Info.plist, and entitlements.

## Conventions

- New source files must be added to `project.pbxproj` (the project doesn't use synchronized folders), or they won't compile.
- Paths contain spaces: quote them in scripts and Makefile rules.
- Keep the keyboard shortcuts consistent between Review All and Duplicates (s / d / r).

## Design principles

Follow the [design principles](docs/rules/design-principles.md) for any UI work.

## After changing code

1. `make dev`

Commit messages are one short, imperative line, like the existing history.
