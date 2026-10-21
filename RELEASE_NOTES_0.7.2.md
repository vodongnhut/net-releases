Nét 0.7.2 (build 20), arm64, ad-hoc signed preview.

- When Writer pauses because Slack did not confirm a replacement, the status now names the guard that tripped (keyboard or mouse input, another app in front, input source change, Slack not answering Accessibility in time, focus moved, window title changed, or readback mismatch) instead of the single "Focus or input activity changed during verification" message. The checks themselves are unchanged.
- Everything else from 0.7.1: Japanese-language Slack composers and thread replies, optional global shortcut, display-only translation popover, opt-in Slack draft correction and translation.

Not notarized: after `brew install --cask vodongnhut/net/net` or a manual download,
run `xattr -dr com.apple.quarantine "/Applications/Nét.app"` once before the first launch. Accessibility access must be granted again for this build.
