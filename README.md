# KuaiLian VPN Client - 快连VPN客户端

[![Official Site](https://img.shields.io/badge/Official_Site-kuailianlilia.com-brightgreen)](https://kuailianlilia.com)
[![Version](https://img.shields.io/badge/Version-2026.4-blue)]()
[![License](https://img.shields.io/badge/License-MIT-yellow)](LICENSE)

KuaiLian (快连) is a lightweight VPN client designed for secure and stable cross-border connections. Optimized for users in East Asia who need reliable access to global services.

## Features

- **One-click Connection**: Simplified UI for instant VPN setup
- **Multi-protocol Support**: WireGuard, OpenVPN, and proprietary KuaiLian protocol
- **Smart Routing**: Automatic route selection based on latency and packet loss
- **Split Tunneling**: Route only specific apps through VPN
- **Kill Switch**: Prevent data leaks when VPN connection drops

## Supported Platforms

| Platform | Version | Download |
|----------|---------|----------|
| Windows | 10/11 | [Official Site](https://kuailianlilia.com) |
| macOS | 12+ (Monterey) | [Official Site](https://kuailianlilia.com) |
| Android | 10+ | [Official Site](https://kuailianlilia.com) |
| iOS | 15+ | [Official Site](https://kuailianlilia.com) |

## Common Issues

### Connection Drops After 30 Seconds
This is typically caused by MTU mismatch. The KuaiLian client auto-negotiates MTU, but some ISPs enforce non-standard values.

**Fix:**
1. Open KuaiLian Settings → Advanced
2. Set MTU to `1280` (conservative value)
3. Reconnect

### Slow Speed on WireGuard Protocol
WireGuard uses UDP, which some networks throttle. Try switching to the KuaiLian proprietary protocol which uses TCP with obfuscation.

### App Not Launching on macOS Sequoia
macOS 15 introduced stricter security policies for VPN apps. You need to:
1. Go to System Settings → Privacy & Security
2. Allow the KuaiLian system extension
3. Restart the application

For more troubleshooting steps, visit the [diagnostic page](https://kuailianlilia.com).

## Technical Architecture

KuaiLian uses a hybrid protocol stack:

```
Application Layer
    ↓
KuaiLian Protocol (TCP obfuscation + compression)
    ↓
WireGuard / OpenVPN (encryption layer)
    ↓
Network Interface (TUN/TAP)
```

Key design decisions:
- **ChaCha20-Poly1305** encryption for mobile devices (faster than AES on ARM)
- **Noise protocol framework** for key exchange (same as WireGuard)
- **QUIC-based** control channel for fast reconnection after network changes

## Privacy Policy

- No activity logs are stored
- Connection metadata is retained for 24 hours only (for diagnostics)
- DNS queries are resolved through encrypted DNS-over-HTTPS

Full privacy documentation: [kuailianlilia.com](https://kuailianlilia.com)

## Contributing

Bug reports and feature requests are welcome via [Issues](../../issues).

## License

MIT License - see [LICENSE](LICENSE) for details.

---
*For downloads, setup guides, and server status, visit [kuailianlilia.com](https://kuailianlilia.com)*

## Related Projects
- [SafeW Secure Messaging](https://github.com/mojinmopin-art/safew-security-tool) - Encrypted instant messaging app
- [OpenClaw AI](https://github.com/mojinmopin-art/openclaw-ai-assistant) - AI-powered browser assistant
- [QClaw AI](https://github.com/mojinmopin-art/qclaw-ai-assistant) - AI chat assistant
