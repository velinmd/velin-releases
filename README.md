# Velin releases

Builds of [Velin](https://velin.md), a native notes app for macOS. Plain Markdown files, your folders, no lock-in.

Download the latest version from [Releases](https://github.com/velinmd/velin-releases/releases/latest).

## Install

With [Homebrew](https://brew.sh):

```sh
brew install --cask velinmd/tap/velin
```

Update with `brew upgrade velin`. Velin runs on Macs with Apple silicon (M1 or later), macOS 13 or newer.

### First launch

Velin is not notarized by Apple yet, so the first time it opens macOS says it cannot verify it. Click **Done**, open **System Settings → Privacy & Security**, and click **Open Anyway** next to Velin. After that it opens like any app.

## Uninstall

```sh
brew uninstall --cask velin          # the app
brew uninstall --zap --cask velin    # and Velin's settings and caches
```

Your notes are never touched.
