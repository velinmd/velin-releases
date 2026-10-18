# Velin releases

Builds of [Velin](https://velin.md): your notes and data, beautifully.

A beautiful home for your local files. A native Mac app for writing, reading and working with plain files in your own folders: Markdown, data, images, PDFs. No lock-in.

Download the latest version from [Releases](https://github.com/velinmd/velin-releases/releases/latest).

## Install

With [Homebrew](https://brew.sh):

```sh
brew install --cask velinmd/tap/velin
```

Update with `brew upgrade velin`. Velin runs on Macs with Apple silicon (M1 or later), macOS 13 or newer.

### First launch

Velin isn't notarized by Apple yet, so the first time it opens, macOS says it can't verify it. Click **Done**, open **System Settings → Privacy & Security**, and click **Open Anyway** next to Velin. After that it opens like any app.

## Uninstall

```sh
brew uninstall --cask velin          # the app
brew uninstall --zap --cask velin    # and Velin's settings and caches
```

Your notes and files are never touched.
