# 🔐 Android security plan

No Android app or encryption implementation has shipped from this repository yet. This document is a plan, not a security certification.

## Planned controls

- Keep offline capture available without account creation.
- Protect locally stored keys with Android Keystore where the chosen crypto design supports it; provide explicit recovery material for encrypted remote data.
- Encrypt synchronized note and attachment payloads on the client. Do not send vault keys to sync or backup providers.
- Use a least-privilege provider token, store it in Android-protected storage, support disconnect/revocation, and avoid logging secrets or note contents.
- Use Android system document/photo pickers for user-selected files instead of broad storage access.
- Make backup health and sync errors visible; never silently downgrade encryption or discard conflicts.
- Verify app links, network certificates, archive checksums, and native Rust artifact provenance in release pipelines.

## Tailscale option

The first design should work with the official Tailscale Android client already connected to the user's tailnet. Cybernote will connect to a configured private HTTPS endpoint; it should not silently create or control a VPN. The self-hosted server still authenticates Cybernote clients and receives ciphertext only.

## Before encrypted sync release

Document the threat model, cryptographic format and library, key derivation, recovery, device enrollment/revocation, metadata exposure, backup recovery, and migration rules. Test malformed and truncated payloads, wrong keys, token leakage, offline conflicts, process interruption, and restore from a clean install. Obtain independent review of the cryptographic design.
