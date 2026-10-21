# Nét releases

Downloadable builds of Nét, a native macOS menu-bar writing assistant that
corrects and translates Slack drafts through Accessibility and offers a
read-only "Translate with Nét" popover for selected text.

Install with Homebrew:

```sh
brew install --cask --no-quarantine vodongnhut/net/net
```

Or download the ZIP from the latest release, unzip, move `Nét.app` to
`/Applications` and clear quarantine:

```sh
xattr -dr com.apple.quarantine "/Applications/Nét.app"
```

Current builds are ad-hoc signed and not notarized. Apple silicon only.
Each release ships a `SHA256SUMS` file; verify downloads with `shasum -a 256 -c`.

After launching, grant Accessibility access in
System Settings > Privacy & Security > Accessibility. Nét only acts on Slack
drafts when Slack integration and automatic replacement are both enabled
in its Settings.
