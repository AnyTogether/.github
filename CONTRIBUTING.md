# Contributing to AnyTogether projects

Thanks for wanting to help! Code, testing, translations, bug reports and game compatibility reports are all welcome.

## Where things live

| Repo | What | Stack | Tests |
|---|---|---|---|
| [AnyPS5-ARM](https://github.com/AnyTogether/AnyPS5-ARM) | The core: engine port for Apple silicon, Windows/Linux engine builds, releases | C/C++, CMake | `ctest` |
| [AnyLauncher](https://github.com/AnyTogether/AnyLauncher) | Mac launcher | Swift, SwiftUI | `swift test` |
| [AnyLauncher-Port](https://github.com/AnyTogether/AnyLauncher-Port) | Windows and Linux launcher | Flutter | `flutter test` |
| [AnyMobile](https://github.com/AnyTogether/AnyMobile) | Phone app | Flutter | `flutter test` |
| [AnyTogether](https://github.com/AnyTogether/AnyTogether) | Online service and website | TypeScript | `pnpm test` |

## How to send a change

1. **Fork** the repo and make a branch: `fix/ds3-handshake`, `feat/german-strings`...
2. Keep the change focused: one fix or feature per pull request.
3. **Add or update tests** and run the repo's suite before you push.
4. Open a **pull request** against `main` and describe what changed, why, and how you tested it. Screenshots for UI changes help a lot.
5. `main` only takes changes through pull requests, so nobody overwrites anyone's work.

Not sure where to start? Open an issue or ask in our Discord first, so two people don't build the same thing.

## Ground rules

- **Never contact Sony's servers** and never fake PSN sign-in. Online play goes through AnyTogether only.
- **No game files, keys or copyrighted assets** in issues, PRs or the repos. Users bring their own dumps.
- **No server details** (IPs, hosts, providers) in public code, docs or commits.
- **Credit others.** If your change follows someone's design or idea, name them in the README's Credits.
- Write user-facing text in **English and Turkish** when the app has both, and keep everything reachable with a controller in the launchers.

## Reporting bugs

Use the issue templates (bug, crash, performance). Include your platform, the version, the game ID if it's about a game, and the log the launcher exports.

By contributing you agree your work is released under the license of the repo you contribute to.
