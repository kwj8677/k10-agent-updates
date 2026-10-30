# K10 Independent Android Agent | Signed Updates

This repository is a public distribution channel only. No credentials, ADB private keys, API keys, or device data are stored here. The K10 application checks stable.json over HTTPS and verifies a pinned ECDSA P-256 release signature before offering updates.

A newer Android APK is installed only after user approval through the standard Android installation flow. No Play Protect bypass or silent installation is attempted.

Source basis: charifmahmoudi/Android-ChatGPT-Remote under the Apache License 2.0 license, modified privately for Lenovo K10. Runtime is independent of Windows, WSL, Bridge, and Master Hand.

## Release format

- Stable metadata: stable.json on main branch
- Binary: https://github.com/kwj8677/k10-agent-updates/releases/download/vX.Y.Z/k10-agent-vX.Y.Z.apk
- Manifest fields: versionCode, versionName, apkUrl, sha256, signature
- P-256 signed payload: versionCode + newline + versionName + newline + apkUrl + newline + sha256 + newline, encoded UTF-8
- APK signing certificate must remain identical across versions.
- Neither release signing key nor update manifest signing key is uploaded to GitHub.

Initial testing requires one manual APK installation. Later releases use the in-app "업데이트 확인" control and Android user-approved installation. Experimental: Wireless Debugging and cloud tunnel integration still need physical-device verification.