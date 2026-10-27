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

## What CI checks on your PR

Every pull request and every push to `main` runs GitHub Actions. One check, **`ci-ok`**, sums up the rest, and it is the only one `main` requires. Parts of a repo you did not touch are skipped and count as passed.

| Repo | What runs |
|---|---|
| AnyPS5-ARM | Engine build and `ctest` on Linux (Ubuntu 22.04 build with the glibc 2.35 check, tests on 24.04 with lavapipe), Windows (WinLibs GCC 15.2) and macOS arm64 (x86-64 under Rosetta), only when `core/`, `cmake/`, `3rdparty/` or CMake files change. `swift test` for `tools/macos/launcher`. `flutter analyze`, `flutter test`, an APK and an unsigned iOS build for `mobile/`. |
| AnyLauncher | `swift test` and `swift build -c release` on macOS 26. |
| AnyLauncher-Port | `flutter analyze` and `flutter test` on Linux, the golden tests on macOS (where the goldens are made), `flutter build linux` (Ubuntu 22.04) and `flutter build windows`. |
| AnyMobile | `flutter analyze`, `flutter test`, an APK and an unsigned iOS build. |
| AnyTogether | Lint, typecheck and tests with Postgres and Valkey, and the production builds. |

Tests that fail on `main` for a known reason, or depend on the runner (timing, real network, a GPU it lacks), are left out from one list per repo, each with its reason, such as `.github/anytogether-ci/ctest-known-failures.txt` in AnyPS5-ARM. If your change breaks a test, fix the test or the code; do not add it to the list. Pull requests from forks run with read-only permissions and no secrets.

## Ground rules

- **Never contact Sony's servers** and never fake PSN sign-in. Online play goes through AnyTogether only.
- **No game files, keys or copyrighted assets** in issues, PRs or the repos. Users bring their own dumps.
- **No server details** (IPs, hosts, providers) in public code, docs or commits.
- **Credit others.** If your change follows someone's design or idea, name them in the README's Credits.
- Write user-facing text in **English and Turkish** when the app has both, and keep everything reachable with a controller in the launchers.

## Reporting bugs

Use the issue templates (bug, crash, performance). Include your platform, the version, the game ID if it's about a game, and the log the launcher exports.

By contributing you agree your work is released under the license of the repo you contribute to.
