Nét 0.7.1 (build 19), arm64, ad-hoc signed preview.

- Slack composers in Japanese-language workspaces are now recognized ("X へのメッセージ", "X のスレッドに返信する"); they were reported as "Unsupported Slack field" before.
- Thread replies in direct and group messages with the "Also send to…" checkbox are no longer rejected as unverified formatting, in English and Japanese Slack.
- Everything else from 0.7.0: optional global shortcut, display-only translation popover, opt-in Slack draft correction and translation.

Not notarized: after `brew install --cask vodongnhut/net/net` or a manual download,
run `xattr -dr com.apple.quarantine "/Applications/Nét.app"` once before the first launch. Accessibility access must be granted again for this build.
