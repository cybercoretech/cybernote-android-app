# 📐 Cybernote Android product specification

## Purpose

Make the same personal Markdown vault useful on an Android phone: rapid capture, offline reading and editing, and reliable synchronization when a chosen route is available.

## First Android milestone

- Native Kotlin and Jetpack Compose interface with dynamic type, TalkBack labels, and the shared Cybercore palettes.
- Open or create a vault; make the local vault path and current sync state visible.
- Browse notebooks and notes, search title/body/tags, and navigate tags and backlinks.
- Create and edit Markdown offline; show saved state and recoverable local history.
- Android share target for text, URLs, and supported attachments.
- Attach photos and documents through Android's user-mediated document/photo pickers.
- Quick-capture widget or notification action after core editing is stable.
- Background sync only after conflict, key, and interruption behavior has passed tests.

## UX principles

- Opening and capture must work without signing in or enabling a cloud provider.
- Explicitly show unsynced changes, last successful sync, last backup, and conflict count.
- Never imply a note is backed up when the destination is offline or the last job failed.
- Keep security settings understandable: encryption mode, recovery-key status, connected devices, and provider access.
- Theme previews are local and cosmetic; accessibility settings and reduced motion take precedence.

## Platform boundaries

Kotlin handles UI, lifecycle, WorkManager scheduling, Android Keystore integration, content URIs, share intents, and notifications. The shared Rust library handles data format, domain behavior, indexing, sync state, and cryptographic operations after security review. Keep all long-running work cancelable and safe across process death.

## Out of scope for first release

- Public note sharing or a hosted web editor.
- AI processing of note contents.
- Mandatory Cybernote account.
- Silent auto-merge that discards a user's branch of edits.
