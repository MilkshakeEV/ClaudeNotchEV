# Installing ClaudeNotchEV

ClaudeNotchEV puts a thin tab on the edge of your screen that shows what Claude Chat and Claude
Code are doing, and your Claude usage. It runs on any Mac (Apple silicon or Intel) with macOS 14
Sonoma or newer, with or without a notch.

## 1. Install
1. Open **ClaudeNotchEV.dmg** (from the Download button on the releases page).
2. Drag **ClaudeNotchEV** onto the **Applications** folder.
3. Eject the disk image.

## 2. Open it the first time
ClaudeNotchEV isn't from the App Store and isn't notarized by Apple, so macOS can't check it
automatically. Expect a warning the first time. On macOS 15 (Sequoia) and later, right-click → Open
no longer gets around it.

1. Open **Applications** and double-click **ClaudeNotchEV**.
2. macOS says it *cannot verify that ClaudeNotchEV is free of malware*. Click **Done** (not "Move to Trash").
3. Open **System Settings → Privacy & Security** and scroll down to **Security**.
4. Next to "ClaudeNotchEV was blocked to protect your Mac", click **Open Anyway**.
5. Click **Open Anyway** again and enter your Mac password.

On macOS 14, right-click the app → **Open** → **Open** also works. You only do this once.

**If the Open Anyway button doesn't appear**, or macOS says the app is "damaged", open
**Terminal** and run the following, then open ClaudeNotchEV again:

```bash
xattr -dr com.apple.quarantine /Applications/ClaudeNotchEV.app
```

This only removes the "downloaded from the internet" flag from ClaudeNotchEV.

## 3. First run
A welcome window explains what the app shows and offers three optional steps. Each one explains
itself before anything happens, can be skipped, and can be changed later in Settings:

| Step | What it does | Asks for |
|---|---|---|
| Claude Code | Installs small hooks in `~/.claude/settings.json` (backed up first) so the tab knows exactly when Claude Code is working or needs you | Nothing from macOS |
| Claude Chat | Watches the Claude desktop app's "Stop response" button to know when a chat reply is being written. Never reads your messages | Accessibility |
| Plan usage | Shows your plan's current session (5-hour) and weekly limits | Keychain access to your Claude Code login |

Launch at Login is a switch in the same window (macOS shows a "Background item added" notice).

After that, **move the pointer onto the tab** at the edge of your screen to see the details.

## Updating
Open **Settings → About** and click **Check for Updates**. If a newer version exists, click
**Open Release Page**, download the new DMG and drag the app into Applications again to replace
the old one. Everything is replaced, including the icon; your settings and permissions are kept.

## Removing it
Quit ClaudeNotchEV from its menu bar icon. If you installed the Claude Code hooks, remove them
first in **Settings → Sources → Remove Hooks…**. Then drag the app from Applications to the Bin.
