
# Local DNS Resolution

Surge module: static [Host] mappings for DoH servers + ByteDance CDN domains use Volcengine DNS (180.184.1.1) for correct domestic CDN resolution.

## What this fixes

- **Douyin / TikTok CN** — CDN domains fail TLS when resolved via Cloudflare DoH over DIRECT. Using ByteDance's own Volcengine DNS returns correct domestic CDN IPs.
- **DoH circular dependency** — Surge needs DNS to reach the DoH server, but DoH is the DNS server. Static [Host] mappings break this loop.

## Usage

In Surge: Config → Modules → Add Module → paste URL:
```
https://raw.githubusercontent.com/pafekutoburu/local-dns-resolution/refs/heads/main/Local-DNS-Resolution.sgmodule
```
