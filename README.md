# 📱 Cybernote for Android

**Your notebook in your pocket, built to work offline.** Cybernote Android is planned as a native Kotlin app backed by the same Rust domain core and Markdown vault format as the desktop TUI.

> 🚧 **Planning and foundation stage.** This repository currently contains product, architecture, security, and project-site documentation. The Android application is not implemented or available to install yet. Follow the [Android roadmap](docs/ROADMAP.md) for scope and release gates.

## ✨ Product direction

- 📝 Markdown notes and attachments that remain portable
- 📵 Offline capture, editing, search, and browsing
- 📥 Android share-sheet capture and quick note entry
- 🔗 Tags, links, backlinks, and fast local search
- 🎨 Four Cybercore palettes with native accessible controls
- 🔐 Client-side encrypted sync with user-selected destinations
- 🕸 Optional private connection to a self-hosted service over Tailscale
- 🧯 Versioned backups with a verified restore workflow

## 🧩 Shared architecture

Kotlin and Jetpack Compose own Android screens, app lifecycle, background scheduling, share intents, notifications, and platform integrations. The shared Rust core owns vault rules, Markdown serialization, indexing, links, history, conflict behavior, encryption, and provider contracts. A versioned native library binding will connect the projects after the core API stabilizes; generated binaries and credentials will not be committed as source.

## 🔐 Honest security status

Cybernote Android has no app implementation yet. Encryption, sync, account/device management, and backup are planned only. The desktop TUI milestone currently stores plaintext Markdown. See [Security](docs/SECURITY.md) for release gates. Do not store sensitive notes in an unreleased or unreviewed build.

## 🗺️ Build sequence

1. Stabilize the shared Rust core and TUI in [cybernote](https://github.com/cybercoretech/cybernote).
2. Build an Android offline-first app around that core.
3. Add encrypted sync adapters for WebDAV, S3-compatible storage, and a Tailscale-accessible self-hosted service.
4. Add independent encrypted backups and prove restore works before calling it complete.

Read the [app spec](docs/APP_SPEC.md), [security plan](docs/SECURITY.md), and [roadmap](docs/ROADMAP.md). The themed project site deploys from [`docs/`](docs/index.html) with GitHub Pages.

## 📄 License

MIT. See [LICENSE](LICENSE).
