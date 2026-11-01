# AI Passport Connect

**Founding Beta** · macOS · by [Forkit AI](https://www.forkit-ai.com)

AI Passport Connect finds the AI coding agents on your Mac, gives each one a Passport and keeps a record of what they do: which agent acted, what kind of action, when, and with what result. Open any session and rebuild it step by step, with every step labelled by how well it is backed by evidence.

This repository publishes the signed releases and the update channel (`latest.json`) that installed copies check. The latest release and its notes are on the [Releases page](https://github.com/Forkit-AI/ai-passport-releases/releases/latest).

## Requirements

- A Mac with Apple silicon (M1 or later)
- macOS 13.5 or later
- A supported coding agent: see [What works today](https://www.forkit-ai.com/founding-beta)

## Install

Open **Terminal** and run the two lines from the [latest release notes](https://github.com/Forkit-AI/ai-passport-releases/releases/latest) or from [forkit-ai.com/product#install](https://www.forkit-ai.com/product#install). For 0.1.0-beta.2:

```bash
curl -fsSLo install.sh https://github.com/Forkit-AI/ai-passport-releases/releases/download/v0.1.0-beta.2/install.sh
echo "74be111ce09e65130f923078bb4c221db5af21200a3510a0a98185b83da51685  install.sh" | shasum -a 256 -c && bash install.sh
```

The installer shows what AI Passport Connect records and installs only after you accept. When it finishes, your browser opens **http://127.0.0.1:4351**.

## Verify

- `install.sh` must match the SHA-256 fingerprint in the release notes and on [forkit-ai.com/security](https://www.forkit-ai.com/security); the `shasum` line above checks it.
- Each release description (`latest.json`) is signed with Ed25519 by the release key **`75c549bd609c6910`** (public key in every release as `ai-passport-release-public-key.pem`). The installer and the in-app updater verify that signature, the download's SHA-256 and size, and the bundled Node.js runtime before anything is installed.
- Every release lists the SHA-256 of all its files in `SHA256SUMS` and includes a CycloneDX SBOM (`sbom.cdx.json`).

## Update

In AI Passport Connect, open **Settings → Check for updates**. It reads `latest.json` from this repository, verifies it, and installs a new release only after the same checks. **Settings → Roll back** returns to the previous release.

## Uninstall

```bash
"$HOME/Library/Application Support/AI Passport/bin/ai-passport" uninstall
```

Type `y` and press Return. Your recorded history is kept unless you choose to delete it.

## Privacy

AI Passport Connect runs on your Mac only. There is no account, and nothing is sent to Forkit. It records metadata about what your agents do (which agent, what kind of action, when, the result) and never records prompts, file contents, code, command text or passwords. Your history stays in `~/.ai-passport` on your Mac. Details: [privacy notice](https://www.forkit-ai.com/datenschutz).

## Support

- Questions and feedback: **info@forkit.dev**, or in the app: **Settings → Help and feedback**
- Security reports: [forkit-ai.com/security](https://www.forkit-ai.com/security)

© 2026 Forkit AI UG (haftungsbeschränkt), Heilbronn, Germany
