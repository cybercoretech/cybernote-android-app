# 🗺️ Android roadmap

This app follows the shared-core milestone in the main Cybernote repository.

## A0 — Product and interface foundation

- [x] Document offline-first scope and security expectations
- [x] Create Android project landing page with shared Cybercore theme chooser
- [ ] Select package ID, minimum Android version, signing and release channel
- [ ] Stabilize versioned Rust core API and Kotlin binding plan

## A1 — Offline notebook

- [ ] Native Compose shell, vault picker, notes list and preview
- [ ] Create/edit Markdown notes, tags, backlinks, and local search
- [ ] Share text and links into Cybernote
- [ ] Attachment intake and local recovery history
- [ ] Dynamic color/type scale, TalkBack, and four Cybercore palettes

## A2 — Encrypted sync

- [ ] Device enrollment, local key storage, recovery flow, and revoke device
- [ ] Sync status, offline queue, interruption safety, and conflict review
- [ ] WebDAV and S3-compatible adapters through the shared provider contract
- [ ] Optional self-hosted endpoint reachable via user-installed Tailscale

## A3 — Backup and release

- [ ] Independent encrypted snapshots with retention controls
- [ ] Restore to a clean install and verify note/attachment integrity
- [ ] Crash-free testing, accessibility pass, signing, release notes, and install guide
