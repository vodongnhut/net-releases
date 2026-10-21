# CLAUDE.md

Public release repo for **Nét** (`vodongnhut/net-releases`): GitHub Releases host the downloadable builds; the git tree holds only the README and release notes. Personal project of Nhựt Võ; identities and the `gh auth switch` rule are in `../CLAUDE.md`. Read it first.

## What is here

- `README.md` — install instructions (Homebrew and manual ZIP). Keep consistent with `../homebrew-net/README.md` and the cask caveats.
- `RELEASE_NOTES_<ver>.md` — one file per version, used as `--notes-file` for the GitHub release.
- No binaries in git. Each release `v<ver>` carries `Net-<ver>-arm64-local.zip` and `SHA256SUMS`, built in `../ai-writing-assistant` (`scripts/release_app.py`) under `dist/releases/<ver>/arm64/local/`.

## Release notes format

Follow `RELEASE_NOTES_0.7.1.md`: first line `Nét <ver> (build <n>), arm64, ad-hoc signed preview.`, then a bullet list of user-visible changes, then the fixed paragraph about `xattr -dr com.apple.quarantine` and re-granting Accessibility. Build number comes from `release.json` next to the ZIP. Commit as `Add <ver> release notes`.

## Publishing a version

1. Build and package in `../ai-writing-assistant`; confirm the ZIP, `SHA256SUMS` and `release.json` exist.
2. Add `RELEASE_NOTES_<ver>.md` here and commit.
3. Bump `../homebrew-net/Casks/net.rb` (version + sha256) and commit.
4. Run a `../publish-net-<ver>.sh`-style script: it switches `gh` to `vodongnhut` (trap back to `nhut-revue`), pushes this repo, runs `gh release create v<ver> <zip> <SHA256SUMS> --title "Nét <ver> (<build>), arm64 ad-hoc preview" --notes-file RELEASE_NOTES_<ver>.md`, pushes the tap and the app repo, then audits the cask.
5. Order matters: the release asset must exist before the cask bump is pushed.

## Verify

```sh
gh auth switch -u vodongnhut
gh release view v<ver> -R vodongnhut/net-releases
shasum -a 256 -c SHA256SUMS   # inside the dist folder
gh auth switch -u nhut-revue
```
